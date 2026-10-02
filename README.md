# Análisis de Viga - Proyecto Reproducible

## Descripción del Proyecto
El proyecto aplica un flujo de análisis reproducible para evaluar el comportamiento estructural de una viga simplemente apoyada sometida a una carga puntual centrada.  A partir de un conjunto de datos de carga-deflexión y de propiedades geométricas y mecánicas del elemento, se compara entre las mediciones y la predicción teórica. Los resultados y hallazgos principales se comunican de manera formal a través de una nota técnica realizada en LaTeX.

## Herramientas necesarias
- Microsoft Excel: Hoja de cálculo para procesar y visualizar los archivos (.xlsx y .cvs)
- Entorno LaTeX: Un editor como lo es Overleaf/VS code con extensión LaTeX par así compilar el archivo report/main.tex

## Pasos para Reproducir los Resultados

1. **Entradas**
   - Revisar el archivo dentro de `data/parametros_viga.xlsx` los cuales son: largo ($L$), altura ($h$), ancho ($b$) y módulo de elasticidad ($E$).
   - Abrir el archivo dentro de `data/datos_viga.csv` para observar los pares de valores medidos de Carga ($\text{kN}$) y Deflexión ($\text{mm}$) (de $0\text{ kN}$ a $40\text{ kN}$).

2. **Análisis y Cálculo de Resultados (`analysis/`)**
   - Abrir `analysis/analisis_viga.xlsx`.
   - En la hoja `Parametros_viga` se resumen las propiedades geométricas y mecánicas del caso.
   - En la hoja `Datos_viga` se tabula la relación entre el incremento de carga (de $5$ en $5\text{ kN}$) y la deflexión resultante (desde $0.00\text{ mm}$ hasta $2.05\text{ mm}$).

3. **Generar el gráfico de Carga - Deformación:**
   - Seleccionar los datos en Excel (columnas Carga, Deflexión medida y Deflexión teórica).
   - Inserta un gráfico de tipo Dispersión con líneas rectas y marcadores.
   - Configura el eje horizontal X como Carga ($\text{kN}$) y el eje vertical Y como Deflexión ($\text{mm}$).
   - Guarda/exporta la imagen obtenida como `carga_deflexion.png` dentro de la carpeta `figures/`.

4. **Compilación del Informe PDF (`report/`) en Overleaf:**
   - Crea un "Nuevo Proyecto en Blanco" en Overleaf.
   - Sube los archivos de la carpeta `report/` (`main.tex` y `borrador_informe.tex`) y la imagen `figures/carga_deflexion.png` manteniendo la estructura de carpetas.
   - Haz clic en el botón verde **Recompilar** (*Recompile*).
   - Descarga el archivo PDF generado (`nota_tecnica.pdf`).

5. **Declarar el uso de IA:**
   - Si es el caso de uso de alguna herramienta de IA, al final de la nota técnica declarar en dónde se utilizó.

## Estructura del repositorio
```text
.
├── README.md                  # Este archivo (guía de reproducción)
├── USO_IA.md                  # Declaración y registro del uso de herramientas de IA
├── data/                      # Entradas y datos brutos
│   ├── datos_viga.csv         # Datos de entrada en formato CSV
│   └── parametros_viga.xlsx   # Parámetros mecánicos y de diseño
├── analysis/                  # Procesamiento y cálculos
│   └── analisis_viga.xlsx     # Hoja de cálculo con el análisis
├── figures/                   # Gráfico generado
│   └── carga_deflexion.png    # Gráfico de resultados (carga vs. deflexión)
└── report/                    # Archivos fuente del informe
    ├── main.tex               # Código fuente principal en LaTeX
    └── nota_tecnica.pdf       # Documento final compilado
