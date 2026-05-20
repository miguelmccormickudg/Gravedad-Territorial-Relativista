# Modelo de Gravedad Territorial Relativista

Este repositorio contiene un notebook en Python desarrollado en Google Colab para calcular un **Modelo de Gravedad Territorial Relativista**, aplicado al análisis espacial de alojamientos tipo Airbnb en Ajijic, Jalisco.

El modelo permite estimar la fuerza territorial de cada nodo a partir de la relación entre masa territorial, distancia espacial, entropía y estabilidad.

## Notebook principal

```text
modelo_gravedad_territorial.ipynb
Objetivo

Calcular indicadores de fuerza territorial para identificar nodos con mayor peso relativo dentro de una estructura espacial de alojamientos.

El modelo genera dos salidas principales:

Una matriz de interacción territorial entre nodos, F_ij.
Un indicador agregado por nodo, F_i.

Estas salidas pueden utilizarse posteriormente en QGIS, Google Earth u otras plataformas de análisis geoespacial.

Fórmula general

El cálculo agregado por nodo se expresa como:

F_i = (M / D_i^β) * E_i * S_i

Donde:

Variable	Descripción
F_i	Fuerza territorial del nodo
M	Masa total territorial del sistema
D_i	Distancia promedio del nodo respecto al sistema
β	Exponente de fricción espacial
E_i	Peso entrópico del nodo
S_i	Estabilidad del nodo

Para la matriz de interacción entre nodos, el cálculo se expresa como:

F_ij = (M / D_ij^β) * E_i * S_i

Donde D_ij corresponde a la distancia entre cada par de nodos.

Archivos de entrada requeridos

Para ejecutar el notebook en Google Colab, se deben cargar los siguientes archivos en /content/:

Archivo	Descripción
masa_total_ajijic.csv	Contiene la masa total territorial del sistema
distance_matrix.csv	Matriz de distancias entre nodos
listings_with_entropy.csv	Base de alojamientos con peso entrópico
E_i_resultado.csv	Archivo con el indicador de estabilidad
Archivos de salida

El notebook genera los siguientes archivos:

Archivo	Descripción
F_ij_matrix.csv	Matriz de fuerza territorial entre nodos
F_i_resultado.csv	Tabla final con fuerza territorial agregada por nodo
F_i_resultado.kml	Archivo geoespacial para visualización en Google Earth o QGIS
Dependencias

El notebook utiliza las siguientes librerías:

pandas
numpy
simplekml

En Google Colab, simplekml se instala mediante:

!pip install -q simplekml
Flujo de trabajo
Cargar la masa total territorial de Ajijic.
Leer la matriz de distancias entre nodos.
Corregir valores de distancia igual a cero para evitar divisiones inválidas.
Cargar la base de alojamientos con entropía.
Cargar el indicador de estabilidad.
Construir una base maestra mediante node_id.
Calcular la matriz F_ij.
Calcular la distancia promedio D_i.
Estimar la fuerza territorial agregada F_i.
Exportar resultados en CSV.
Generar un archivo KML para análisis cartográfico.
Uso
Abrir el notebook en Google Colab.
Cargar los archivos de entrada en el entorno /content/.
Ejecutar las celdas en orden.
Descargar los archivos generados:
F_ij_matrix.csv
F_i_resultado.csv
F_i_resultado.kml
Abrir el archivo KML en QGIS o Google Earth para visualizar los resultados.
Interpretación territorial

El indicador F_i representa una medida relacional de intensidad territorial. Un valor alto puede indicar que un nodo combina:

mayor peso dentro del sistema,
menor fricción espacial promedio,
mayor peso entrópico,
mayor estabilidad relativa.

Este indicador no debe interpretarse como una medida causal directa, sino como una aproximación exploratoria para identificar patrones de concentración, persistencia e influencia territorial asociados a plataformas digitales de alojamiento.

Advertencias metodológicas

Este modelo se encuentra en fase experimental. Se recomienda revisar cuidadosamente:

la consistencia de los identificadores node_id,
la presencia de valores nulos después de la unión de bases,
la sensibilidad del resultado frente al parámetro β,
la definición conceptual de entropía,
la definición conceptual de estabilidad,
la calidad de las coordenadas geográficas,
la escala territorial del análisis.
Posibles aplicaciones

Este notebook puede servir como base para:

análisis espacial de alojamientos Airbnb,
estudios de geografía digital,
análisis de plataformas digitales y territorio,
identificación de nodos de alta intensidad territorial,
visualización geoespacial en QGIS,
experimentación con modelos gravitacionales adaptados,
investigación doctoral sobre plataformas digitales y reconfiguración espacial.
Estructura sugerida del repositorio
Gravedad-Territorial-Relativista/
│
├── modelo_gravedad_territorial.ipynb
├── README.md
├── data/
│   ├── masa_total_ajijic.csv
│   ├── distance_matrix.csv
│   ├── listings_with_entropy.csv
│   └── E_i_resultado.csv
│
├── outputs/
│   ├── F_ij_matrix.csv
│   ├── F_i_resultado.csv
│   └── F_i_resultado.kml
│
└── docs/
    └── metodologia.md
Autor

Miguel Ángel Iñiguez McCormick
Doctorante en Geografía y Ordenación Territorial
Especialista en geografía digital, inteligencia territorial, smart cities y análisis espacial de plataformas digitales.

Estado del proyecto

Proyecto en desarrollo, asociado a investigación doctoral sobre plataformas digitales, Airbnb y reconfiguración territorial.

Licencia

Creative Commons.

Cómo citar

Referencia sugerida:

Iñiguez McCormick, M. A. (2026). Modelo de Gravedad Territorial Relativista: notebook para el análisis espacial de alojamie
