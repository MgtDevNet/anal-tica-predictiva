# Train, validación y test: cómo usar cada conjunto de datos

> **Idea clave:** el conjunto de test solo se usa para **medir**, nunca para **decidir**.

---

## 1. Los tres roles de los datos

| Conjunto | ¿Qué hace? | ¿Qué decide? |
|---|---|---|
| **Train** | Ajusta los **parámetros** del modelo (pesos, coeficientes, splits) | Cómo aprende el modelo |
| **Validación** (o validación cruzada) | Compara **hiperparámetros** y elige el mejor | Qué configuración usar |
| **Test** | Mide la **generalización** final | Nada. Solo mide |

### Parámetros vs. hiperparámetros

- **Parámetros:** los aprende el modelo durante el entrenamiento (pesos de una red, coeficientes de una regresión).
- **Hiperparámetros:** los fijas tú antes de entrenar (`learning_rate`, `max_depth`, `C`, número de capas, etc.).

---

## 2. La analogía del examen

- **Train** = tus libros y ejercicios de práctica.
- **Validación** = los simulacros con los que decides cómo estudiar.
- **Test** = el examen real, que haces **una sola vez**.

Si haces el examen, ves la nota, y vuelves a estudiar para repetirlo hasta sacar buena nota, esa nota ya no refleja lo que sabes. Solo refleja que te adaptaste a ese examen. Con el test pasa exactamente lo mismo.

---

## 3. Por qué no se puede evaluar hiperparámetros con el mismo train

Un modelo siempre se ve bien en los datos con los que se entrenó. Por eso, para comparar hiperparámetros necesitas datos que el modelo **no haya visto durante el ajuste**. Esos datos son la **validación** (normalmente obtenida con validación cruzada dentro del train), **no el test**.

---

## 4. Flujo correcto paso a paso

1. **Partir los datos:** separa un conjunto de test (por ejemplo 20%) y guárdalo sin tocarlo.
2. **Buscar hiperparámetros con validación cruzada, solo dentro de train:**
   - Divide el train en *k* partes (por ejemplo 5).
   - Entrena con *k−1* partes y valida con la restante, rotando.
   - Promedia el error de cada configuración.
   - Elige **un único** conjunto de hiperparámetros ganador.
3. **Entrenar** el modelo con esos hiperparámetros usando todo el train.
4. **Evaluar en test una sola vez.** Ese número es tu estimación honesta de cómo se comportará con datos nuevos.
5. **(Opcional) Reentrenar con todos los datos** (train + test) usando los hiperparámetros ya fijos, para obtener el modelo final de producción.

| Paso | Datos | Propósito |
|---|---|---|
| 1. Partir | Todos → train + test | Guardar el test |
| 2. Buscar hiperparámetros | Train con CV | Elegir **un** ganador |
| 3. Entrenar con el ganador | Train | Obtener el modelo |
| 4. Evaluar | Test (una vez) | Medir generalización |
| 5. Reentrenar (opcional) | Todos, hiperparámetros fijos | Modelo final de producción |

---

## 5. La parte más importante: el rol del test en la construcción del modelo

### El test NO participa en la construcción del modelo

- No se usa para ajustar parámetros.
- No se usa para elegir hiperparámetros.
- No se usa para elegir entre modelos, features o preprocesamiento.

### El test es un termómetro, no un selector

El test te dice **qué tan bien está el modelo que ya elegiste**. No debe ayudarte a elegir entre candidatos.

### El error típico (contaminación del test)

1. Entrenas y evalúas en test: error = 12%.
2. Cambias un hiperparámetro y vuelves a evaluar en test: error = 10%.
3. Repites hasta llegar a 8%.

Aunque el modelo nunca "entrenó" con el test, **tus decisiones sí se ajustaron a él**. Estás eligiendo lo que casualmente funciona mejor en esos datos específicos. Con datos realmente nuevos, el error probablemente será mayor que 8%.

### Cuidado con el plural

Usar el test para mirar **varios** modelos o configuraciones y quedarte con el mejor es usarlo para decidir, y eso lo contamina. La forma correcta:

1. La validación cruzada elige **un único** ganador.
2. Ese único modelo se evalúa en test.
3. Reportas el resultado, sea bueno o malo, sin volver atrás a cambiar cosas.

### ¿Y si el resultado en test decepciona?

Repórtalo tal cual, o replantea el problema (más datos, otras features, otro tipo de modelo) asumiendo que ese test ya quedó parcialmente "usado". Idealmente, para la nueva iteración conviene tener datos de test frescos.

---

## 6. Reentrenar con todos los datos: ¿cuándo sí?

Al reentrenar con train + test:

- Los **hiperparámetros quedan fijos** (los que ya encontraste).
- Los **parámetros del modelo** se recalculan desde cero con todos los datos.

**¿Por qué es válido?** Porque el test ya cumplió su función: midió la generalización y ya reportaste ese número. No queda ninguna decisión pendiente que se pueda contaminar.

**Limitación:** el modelo final ya no tiene datos "no vistos", así que no puedes medir su rendimiento. Se asume que se comportará igual o un poco mejor que el modelo evaluado.

**Es opcional:** si tienes muchísimos datos, la mejora de añadir el 20% puede ser mínima, y hay quien prefiere quedarse exactamente con el modelo que se evaluó.

### Regla de oro

> Usa todos los datos solo cuando ya no vayas a tomar ninguna decisión ni a medir nada con ellos.

| Momento | ¿Qué datos usas? |
|---|---|
| Buscar hiperparámetros | Solo train (con validación o CV) |
| Medir generalización | Solo test, una vez |
| Modelo final para producción | Todos (train + test), hiperparámetros fijos |

---

## 7. Ejemplo en código (scikit-learn)

```python
from sklearn.model_selection import train_test_split, GridSearchCV
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score

# 1. Partir: guardar el test
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

# 2. Buscar hiperparámetros con CV, SOLO con train
param_grid = {"max_depth": [3, 5, 10], "n_estimators": [100, 200]}
grid = GridSearchCV(RandomForestClassifier(random_state=42),
                    param_grid, cv=5)
grid.fit(X_train, y_train)

print("Mejores hiperparámetros:", grid.best_params_)

# 3. El mejor modelo ya viene reentrenado con todo el train (refit=True)
best_model = grid.best_estimator_

# 4. Evaluar en test UNA sola vez
y_pred = best_model.predict(X_test)
print("Accuracy en test:", accuracy_score(y_test, y_pred))

# 5. (Opcional) Modelo final con todos los datos, hiperparámetros fijos
final_model = RandomForestClassifier(**grid.best_params_, random_state=42)
final_model.fit(X, y)
```

---

## 8. Detalle extra: el preprocesamiento también cuenta

Escaladores, imputadores, selección de variables, etc. deben ajustarse **solo con train** (o dentro de cada fold de la CV). Si calculas la media y la desviación con todos los datos antes de partir, el test ya "se filtró" en tu modelo (*data leakage*). La solución más limpia es usar un `Pipeline` de scikit-learn junto con la validación cruzada.

---

## Resumen en una frase

> **Train para aprender, validación para decidir, test para juzgar (una sola vez), y al final, si quieres, entrena con todo.**
