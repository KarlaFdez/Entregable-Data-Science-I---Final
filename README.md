## US Análisis y Clasificación de Presidentes de EE. UU. en Google Colab

Este notebook ha sido adaptado para ejecutarse fácilmente en Google Colab, permitiéndote analizar datos históricos sobre los presidentes de Estados Unidos y aplicar técnicas de Machine Learning para clasificar la duración de sus mandatos.

## 🔍 1. ¿Qué incluye el notebook?

- Limpieza y preparación del dataset `us_presidents 2.csv`
- Cálculo de la duración de cada mandato presidencial
- Creación de una variable categórica `mandate_class`
- Codificación de variables categóricas
- Feature Selection con `SelectKBest`
- Modelo de clasificación con `RandomForestClassifier`
- Evaluación del modelo con métricas y matriz de confusión

Se detectaron valores especiales como `"--"` para fechas abiertas (por ejemplo, el presidente actual), y se manejaron adecuadamente como valores nulos (`NaT`) para evitar errores en la conversión de fechas.
También se realizaron limpiezas textuales para eliminar dobles espacios y referencias de tipo `[13]` en los nombres de partidos.

### 2. Cálculo de duración de mandatos

Se calculó la duración de cada mandato presidencial en años, lo cual permite realizar análisis comparativos entre distintos presidentes o periodos históricos.

### 3. Visualizaciones

Se generan gráficos que ilustran aspectos relevantes como:
- Distribución de duración de los mandatos
- Agrupación por partidos políticos
- Evolución histórica del poder en Estados Unidos

Estas visualizaciones permiten observar patrones históricos, tendencias y anomalías a lo largo de más de 200 años de historia política en EE. UU.

### 4. Análisis descriptivo

Además de los gráficos, se presentan resúmenes estadísticos básicos que describen la centralidad y dispersión de las variables cuantitativas.

## 🚀 Cómo usar este notebook en Google Colab

Haz clic en la siguiente liga para abrir y ejecutar el notebook en Google Colab:

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)]
([https://colab.research.google.com/github/KarlaFdez/Entregable-Data-Science-I/blob/main/ProyectoDS_Parte_l_Fernandez_final.ipynb])

## 📁 Archivos incluidos

- `ProyectoDS_Parte_l_Fernandez_final.ipynb`: Notebook con el análisis completo
- `us_presidents 2.csv`: Datos de entrada en formato tabular
- `README.md`: Descripción del proyecto


### 5. Clasificación de duración del mandato

Se creó una variable categórica (`mandate_class`) que clasifica a los presidentes según la duración de su mandato:

- `short`: menos de 4 años
- `medium`: entre 4 y 6 años
- `long`: más de 6 años

Se entrenó un modelo de clasificación usando `RandomForestClassifier` con las variables `party`, `prior` y `vice`. El modelo obtuvo una precisión global del 55.6% en un conjunto de prueba. A pesar de su simplicidad, ilustra cómo aplicar técnicas de Machine Learning a datos históricos.

Se usaron herramientas como:

- `LabelEncoder` para codificar variables categóricas.
- `SelectKBest` para selección de características.
- `classification_report` y `confusion_matrix` para evaluación del modelo.

Este análisis puede ampliarse incluyendo más variables que representen el contexto político o social de cada mandato.

### 🧠 Interpretación detallada de resultados del modelo

Se utilizó un modelo `RandomForestClassifier` para predecir la clase de duración del mandato (`short`, `medium`, `long`) a partir de las variables `party`, `prior` y `vice`.

#### 📈 Métricas obtenidas

| Clase   | Precisión | Recall | F1-score |
|---------|-----------|--------|----------|
| **long**    | 1.00      | 0.33   | 0.50     |
| **medium**  | 0.33      | 1.00   | 0.50     |
| **short**   | 1.00      | 0.50   | 0.67     |
| **Accuracy**|          |        | **55.6%** |

#### 📌 Interpretaciones clave

1. **Mandatos largos:** el modelo identifica correctamente muy pocos (bajo recall), pero cuando lo hace, acierta (alta precisión).
2. **Mandatos medios:** detecta todos los reales, pero predice incorrectamente varios que no lo son (precisión baja).
3. **Mandatos cortos:** balance entre precisión y recall, pero aún hay errores.
4. **Desequilibrio de clases:** el modelo tiende a sobrepredecir la clase "medium" debido a la distribución del dataset.

#### 🧠 Conclusión del modelo

Aunque el modelo tiene una precisión moderada, revela que las variables actuales tienen poder predictivo limitado. Factores externos como el contexto político, histórico y social tienen gran influencia en la duración del mandato y no están presentes en los datos. El ejercicio sigue siendo valioso como introducción al uso de Machine Learning en datos históricos reales.

## 🧠 Conclusión

Este proyecto demuestra cómo aplicar técnicas de análisis exploratorio de datos (EDA) para estudiar figuras históricas y extraer información relevante a partir de datos estructurados. Puede ser extendido con más variables (como políticas públicas, desempeño económico o popularidad) para generar estudios más profundos sobre el liderazgo en Estados Unidos.


Elaborado por: **Karla Fernández**
