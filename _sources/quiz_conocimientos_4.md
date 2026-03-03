# Ejercicio de práctica: Exploración de datos desde Parquet (Hábitat en cuerpos de agua)

## ¿Qué encontrarás?
En este ejercicio vas a practicar un flujo típico cuando trabajamos con datos “pesados” y eficientes:

- Descargar/abrir datos en formato **Parquet**
- Leerlos con `pandas` (engine `pyarrow`)
- Hacer un EDA enfocado en:
  - tipos de variables
  - nulos
  - consistencia de categorías
  - agregaciones y tendencias
- Construir al menos **una visualización** (recomendada: tendencias por año)

> Fuente: *Surface Water – Habitat Results (CEDEN, California)*.  
> El portal ofrece el dataset por años y también una descarga masiva en Parquet (ZIP).

---

## Objetivos del ejercicio
Al finalizar, deberías poder:

1. Explicar por qué Parquet suele ser mejor que CSV para análisis (tamaño, lectura, tipos).
2. Cargar Parquet correctamente en Python y validar que los tipos de datos sean coherentes.
3. Diseñar agregaciones (groupby) para responder preguntas reales.
4. Construir una visualización informativa y concluir con hallazgos claros.

---

## Recomendaciones
1. Si el ZIP es grande: trabaja con una **muestra** (por ejemplo, un año).
2. No intentes “ver todo”: define 2–3 preguntas y orienta el EDA a responderlas.
3. Documenta supuestos: qué columnas usaste, qué filtraste y por qué.

---

## Actividades

### 1) Lectura del archivo Parquet
- Descarga el ZIP en Parquet (o usa un archivo ya disponible localmente).
- Extrae el contenido y ubica el/los `.parquet`.
- Lee el/los archivos en `pandas`.

**Pistas técnicas (opcional):**
- Instala dependencias: `pip install pyarrow`
- Lectura base: `pd.read_parquet("archivo.parquet")`
- Si hay múltiples parquet, puedes concatenar:
  - leer una lista de archivos y hacer `pd.concat(...)`

---

### 2) Limpieza mínima
Como mínimo:

- Identificar columnas con alta proporción de nulos.
- Revisar columnas categóricas: número de categorías y categorías “raras”.
- Revisar columnas numéricas: rangos y posibles valores extremos.

---

### 3) EDA guiado por preguntas
Elige **2 preguntas** (o define las tuyas). Ejemplos:

- ¿Cómo varía el número de mediciones/registros por **año**?
- ¿Qué categorías (por ejemplo: tipo de hábitat / indicador / calidad) aparecen más?
- ¿Existen diferencias por zonas/estaciones/sitios (si hay variables geográficas o de estación)?

Incluye:
- tablas resumen (Top 10)
- conteos por grupo
- métricas simples (promedios/medianas si aplica)

---

### 4) Visualización obligatoria
Construye **al menos un gráfico**.

**Opción recomendada (línea):**
- Conteo de registros por año (serie de tiempo).

**Opción alternativa:**
- Barras para Top categorías.
- Boxplot/histograma para una variable numérica clave (si existe).

---

## Producto final
Tu entrega “ideal” debe incluir:

1. Código reproducible.
2. 1+ visualizaciones con ejes/títulos claros.
3. Un bloque final: **Conclusiones (3 bullets)** con evidencia.

---

¿Listo? ¡A programar se dijo!