# Proyecto: Clasificación de planes móviles para Megaline

## Descripción del proyecto
La compañía móvil **Megaline** busca un modelo que analice el comportamiento de sus clientes y recomiende uno de los nuevos planes: **Smart** o **Ultra**. Para ello, se trabajará con datos de suscriptores que ya han cambiado a los planes nuevos. El objetivo principal es desarrollar un modelo de clasificación con una exactitud mínima del 75%.

Como el preprocesamiento ya está hecho, el enfoque se centra en la construcción y evaluación del modelo.

---

## Descripción de los datos
Cada observación del dataset contiene información mensual sobre el comportamiento de un usuario, con las siguientes características:

- **calls**: Número de llamadas.
- **minutes**: Duración total de las llamadas en minutos.
- **messages**: Número de mensajes de texto enviados.
- **mb_used**: Tráfico de Internet en MB utilizado.
- **is_ultra**: Plan actual del mes (Ultra = 1, Smart = 0).

---

## Proceso de modelado
### Evaluación de modelos: Random Forest con validación cruzada

Se utilizó el **Random Forest Classifier** debido a su capacidad para obtener una alta exactitud, independientemente del costo computacional. Los pasos realizados incluyen:

1. **Optimización de hiperparámetros**:
   - Se probó con diferentes valores de `n_estimators` (número de árboles en el bosque) en el rango de 1 a 50.
   - Para cada valor, se entrenó el modelo y se calculó:
     - La exactitud sobre los datos de validación.
     - El puntaje promedio usando **validación cruzada por k-fold** con 10 particiones.

2. **Visualización de resultados**:
   - Se graficaron las métricas de exactitud y puntajes promedio de validación cruzada en función de los valores de `n_estimators`.

---

## Resultados obtenidos

### Rendimiento del modelo:
- El modelo alcanzó una exactitud máxima del **80%**.
- Los valores óptimos de hiperparámetros se determinaron mediante validación cruzada, lo que asegura la estabilidad del rendimiento.

### Gráfico: Desempeño vs `n_estimators`
![Rendimiento Random Forest](https://github.com/DSRoCCO/clasificacion_planes_moviles_TPT/blob/main/attachment.png)  
El gráfico muestra cómo la exactitud de validación y el promedio de puntajes de validación cruzada aumentan con el número de árboles hasta estabilizarse en valores óptimos.

---

## Conclusiones

1. **Selección del modelo**:
   - El modelo de **Random Forest** fue elegido debido a su capacidad de alcanzar la mayor exactitud posible. En este proyecto, el costo computacional no era una limitante.

2. **Exactitud alcanzada**:
   - Se logró una exactitud del **80%**, superando el umbral mínimo requerido de 75%.

3. **Validación cruzada**:
   - La técnica de validación cruzada garantizó que los resultados no estuvieran sesgados y fueran representativos.

4. **Recomendación**:
   - Este modelo es confiable para predecir el plan óptimo de los usuarios basándose en su comportamiento mensual.

---
