# Ejercicio de práctica: Exploración de datos desde JSON (Vehículos eléctricos)

## ¿Qué encontrarás?
En este ejercicio vas a practicar un flujo muy común en Ciencia de Datos:

- Consumir datos desde una URL en formato **JSON**
- Convertirlos a un **DataFrame** con `pandas`
- Hacer un **análisis exploratorio (EDA)** básico
- Construir al menos **una visualización** (recomendada: serie de tiempo o evolución por año)

> Fuente de datos: *Electric Vehicle Population Data (State of Washington)*.  
> JSON directo: https://data.wa.gov/api/views/f6w7-q2d2/rows.json?accessType=DOWNLOAD

---

## Objetivos del ejercicio
Al finalizar, deberías poder:

1. Leer un JSON “real” desde internet y transformarlo en un DataFrame.
2. Identificar variables relevantes (categorías, fechas, ubicaciones).
3. Proponer y construir un gráfico que cuente una historia (no solo “graficar por graficar”).
4. Extraer 3 hallazgos claros y sustentarlos con evidencia (tablas o gráficos).

---

## Recomendaciones
1. Trabaja por pasos: **carga → limpieza → EDA → visualización → conclusiones**.
2. Si algo no sale a la primera, no pasa nada: depura el problema (tipos de datos, nulos, columnas raras).
3. Tu objetivo no es “hacerlo perfecto”, sino **hacerlo entendible y reproducible**.

---

## Actividades

### 1) Carga del JSON
- Descarga el JSON desde la URL.
- Inspecciona su estructura (llaves principales, dónde están los “registros”).
- Construye un DataFrame.

**Pistas técnicas (opcional):**
- Puedes usar `requests.get(url).json()` o `pd.read_json(url)`.
- A veces el JSON viene “anidado”: puede requerir ubicar la lista de filas y construir el DataFrame manualmente.

---

### 2) Limpieza mínima
Realiza, como mínimo:

- Estandarizar nombres de columnas (por ejemplo, minúsculas y guiones bajos).
- Revisar nulos y decidir qué hacer con ellos (eliminar, imputar, o dejarlos explícitos).
- Identificar columnas con tipo “numérico” que hayan quedado como texto.

---

### 3) EDA (Exploratory Data Analysis)
Incluye, como mínimo:

- Dimensión del dataset (`n_filas`, `n_columnas`)
- Conteo de nulos por columna (top 10)
- Distribución de 2 variables categóricas relevantes (por ejemplo: `make`, `model`, `county`, `electric_vehicle_type`)
- Una tabla resumen “Top 10” (por ejemplo: marcas con más registros)

---

### 4) Visualización obligatoria
Construye **al menos un gráfico**.

**Opción recomendada (línea / serie de tiempo):**
- Convertir una variable de año/fecha (si existe) y graficar:
  - cantidad de registros por año, o
  - cantidad por año y tipo de vehículo (comparación)

**Opción alternativa (si no usas línea):**
- Barras: Top 10 marcas / condados
- Heatmap simple: conteos por (año × tipo) si aplica

---

## Producto final
Tu entrega “ideal” (dentro del notebook o página) debe incluir:

1. Código reproducible (que corra de inicio a fin).
2. 1+ visualizaciones con título y ejes claros.
3. Un bloque final: **Conclusiones (3 bullets)**  
   - “Hallazgo 1 … (evidencia: tabla/gráfico X)”
   - “Hallazgo 2 …”
   - “Hallazgo 3 …”

---

¿Listo? ¡A programar se dijo!