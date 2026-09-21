# Rendimiento_Estudiantes
Análisis exploratorio, limpieza y visualización del desempeño de estudiantes en
matemáticas, lectura y escritura, incluyendo la creación de un promedio general
(`average_score`) y una clasificación del rendimiento en niveles **Bajo**, **Medio**
y **Alto**.

## Dataset

- **Nombre:** Students Performance in Exams
- **Fuente:** [Kaggle — Students Performance in Exams](https://www.kaggle.com/datasets/spscientist/students-performance-in-exams)
- **Descripción:** contiene 1,000 registros de estudiantes con su género, grupo
  étnico, nivel educativo de los padres, tipo de comida (estándar o
  gratuita/reducida), si completaron un curso de preparación para el examen, y sus
  calificaciones en matemáticas, lectura y escritura (escala 0–100).

## Objetivo

Explorar qué factores (curso de preparación, nivel educativo de los padres, tipo de
comida, género, grupo étnico) se relacionan con el rendimiento académico de los
estudiantes, y construir una clasificación simple de su desempeño general.

## Requisitos

- Python 3.10 o superior
- Las dependencias listadas en `requirements.txt`

## Instalación

Clonar el repositorio:

```bash
git clone URL_DEL_REPOSITORIO
```

Entrar al proyecto:

```bash
cd analisis-rendimiento-estudiantes
```

Crear el entorno virtual:

```bash
python -m venv .venv
```

Activarlo:

```bash
# Windows
.venv\Scripts\activate

# macOS/Linux
source .venv/bin/activate
```

Instalar las dependencias:

```bash
pip install -r requirements.txt
```

## Ejecución

Desde la raíz del proyecto (con el entorno virtual activado):

```bash
python src/analysis.py
```

El script imprime en consola cada paso del análisis y guarda todos los resultados
en `outputs/resultados/`:

- `dataset_limpio.csv` — dataset ya limpio, con `average_score` y `performance_level`
- `resumen_analisis.txt` — resumen en texto de toda la exploración y los análisis
- `01_promedio_por_area.png`, `02_curso_preparacion.png`,
  `03_escolaridad_padres.png`, `04_distribucion_niveles.png` — visualizaciones

## Análisis realizados

1. **Exploración inicial:** número de registros/columnas, tipos de datos, valores
   faltantes, duplicados y estadísticas descriptivas.
2. **Limpieza:** estandarización de nombres de columnas y texto, validación de
   rangos (0–100), tipado correcto de variables categóricas y orden ordinal del
   nivel educativo de los padres.
3. **`average_score`:** promedio de las tres calificaciones.
4. **`performance_level`:** clasificación en Bajo (<60), Medio (60–79.9) y Alto
   (≥80), usando cortes fijos con significado pedagógico en lugar de percentiles.
5. **Promedio por área** — cuál de las tres materias tiene mejor desempeño general.
6. **Efecto del curso de preparación** — comparación de promedios y prueba
   estadística (t de Student) entre quienes lo completaron y quienes no.
7. **Nivel educativo de los padres** — relación entre la escolaridad de los padres
   y el promedio del estudiante.
8. **Comparación por grupos** — diferencias de promedio según grupo étnico, género
   y tipo de comida (`lunch`).
9. **Porcentaje de estudiantes por umbral de promedio** (≥50, ≥60, ≥70, ≥80, ≥90).
10. **Correlación entre las tres áreas.**

## Estructura del proyecto

```
analisis-rendimiento-estudiantes/
│
├── data/
│   └── dataset.csv
├── src/
│   └── analysis.py
├── outputs/
│   └── resultados/
├── README.md
├── requirements.txt
└── .gitignore
```
