# Análisis de Deserción en la Formación Profesional Integral

Análisis exploratorio de datos sobre deserción estudiantil en programas de formación profesional, usando Python (pandas, seaborn, scipy).

## Objetivo

Identificar qué centros de formación, modalidades y niveles educativos presentan mayor deserción, para aportar puntos de partida a estrategias de retención.

## Preguntas de investigación

1. ¿Qué centros de formación tienen mayor deserción (en número absoluto y en porcentaje)?
2. ¿La modalidad de estudio (presencial, virtual, a distancia) influye en la deserción?
3. ¿Hay niveles de formación con mayor deserción que otros?
4. ¿Qué tan asociados están el nivel de formación y la modalidad?
5. ¿Existe relación entre el tamaño de una ficha (matriculados) y su tasa de deserción?

## Datos

- **Fuente:** `DESERCION_DE_LA_FORMACIÓN_PROFESIONAL_INTEGRAL_20260807.csv` (42.080 filas, 15 columnas)
- **Sin valores nulos ni filas duplicadas.**
- **Limitación conocida:** la columna `PERIODO` tiene un único valor en todo el dataset, por lo que no permite comparar deserción entre periodos académicos con este extracto.

## Metodología

- Limpieza de comillas incrustadas en columnas de texto (defecto del export de origen).
- Estadística descriptiva y tasas de deserción por grupo (centro, modalidad, nivel).
- Prueba Chi-cuadrado y V de Cramer para asociación entre variables categóricas (nivel de formación vs. modalidad).
- Correlación de Pearson entre tamaño de ficha y deserción, calculada tanto en conteos absolutos como en tasa (para evitar el sesgo de que grupos más grandes tengan más desertores solo por su tamaño).

## Hallazgos principales

- La modalidad **VIRTUAL** tiene la tasa de deserción más alta (6.24%), frente a 2.40% (a distancia) y 1.60% (presencial).
- El nivel de formación **EVENTO** tiene la tasa más alta (10.44%).
- Existe una asociación moderada (V de Cramer = 0.31) entre nivel de formación y modalidad.
- El centro con más desertores en número absoluto no es el mismo que el de mayor porcentaje de deserción — el tamaño del centro importa.

