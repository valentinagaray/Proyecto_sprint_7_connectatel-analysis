# Proyecto_sprint_7_connectatel-analysis
 Este proyecto analiza el comportamiento de uso de llamadas y mensajes de clientes de **ConnectaTel**, empresa de telecomunicaciones con operaciones en México y Colombia. El objetivo es identificar patrones de consumo, detectar valores atípicos y segmentar clientes para generar recomendaciones comerciales basadas en datos.

## Objetivos

- Explorar e integrar información de clientes, planes y actividad móvil.
- Identificar y tratar problemas de calidad de datos.
- Describir estadísticamente el consumo de llamadas y mensajes por usuario.
- Detectar valores atípicos mediante el método IQR y visualizaciones.
- Segmentar clientes por edad y nivel de uso.
- Presentar hallazgos y oportunidades de mejora para la oferta comercial.

## Datasets

| Archivo | Contenido |
|---|---|
| `plans.csv` | Catálogo de planes, precios, beneficios y cargos por consumo adicional. |
| `users_latam.csv` | Información de usuarios, edad, ciudad, registro, plan y fecha de cancelación. |
| `usage.csv` | Registros de llamadas y mensajes, fechas, duración y longitud. |

Los datos originales se proporcionaron como parte del proyecto académico. Para reproducir el análisis, descarga los archivos desde los enlaces del curso y colócalos en la carpeta `datasets/`.

## Herramientas

- Python
- pandas y NumPy
- seaborn y Matplotlib
- Jupyter Notebook (o Google Colab)
- GitHub para control de versiones y publicación

## Metodología

1. **Carga y exploración:** revisión de dimensiones, columnas, tipos de datos y registros iniciales.
2. **Diagnóstico de calidad:** identificación de nulos, valores sentinels y fechas fuera de rango.
3. **Limpieza:** tratamiento de edades inválidas, ciudades desconocidas y fechas inconsistentes; conservación de nulos estructurales en los eventos de uso.
4. **Estadística descriptiva:** agregación de mensajes, llamadas y minutos por usuario; cálculo de medidas de tendencia central y dispersión.
5. **Visualización y outliers:** histogramas, boxplots y detección de valores extremos mediante IQR.
6. **Segmentación:** clasificación por nivel de uso y grupo de edad.
7. **Análisis ejecutivo:** interpretación de resultados y recomendaciones comerciales.

## Hallazgos principales

- El **uso medio** fue el segmento de consumo predominante.
- El grupo de **adultos de 30 a 59 años** fue el más numeroso.
- Se detectaron **46** valores atípicos en cantidad de mensajes, **30** en cantidad de llamadas y **109** en minutos acumulados de llamadas, sobre 3,999 perfiles con métricas de uso disponibles.
- En los datos originales, `city` presentó **469 nulos (11.725%)** y **96 valores `?` (2.4%)**. También se detectaron edades con el sentinel `-999` y **40 registros de fecha en 2026**, fuera del periodo de referencia hasta 2024.
- En `usage`, los nulos de `duration` y `length` dependían del tipo de evento (mensaje o llamada), por lo que se trataron como nulos estructurales.

**Interpretación:** los usuarios de consumo medio ofrecen una oportunidad de optimización de planes por su tamaño; los usuarios de alto consumo podrían justificar paquetes especializados. La rentabilidad de cada segmento requiere información adicional de ingresos y costos.

## Recomendaciones

- Evaluar planes equilibrados para clientes de consumo medio.
- Considerar paquetes ampliados para usuarios intensivos y alternativas flexibles para usuarios de bajo consumo.
- Monitorear consumos atípicos sin asumir automáticamente que constituyen errores o fraude.
- Fortalecer la validación de edades, ciudades y fechas en el proceso de captura de datos.
- Incorporar ingresos, costos y churn en análisis posteriores para priorizar oportunidades comerciales.

## Estructura sugerida del repositorio

```text
connectatel-analysis/
├── README.md
├── notebooks/
│   └── connectatel_analysis.ipynb
└── datasets/
    ├── plans.csv
    ├── users_latam.csv
    └── usage.csv
```

## Cómo ejecutar el proyecto

1. Descarga o clona este repositorio.
2. Instala Python y Jupyter Notebook, o abre el archivo `.ipynb` en Google Colab.
3. Instala las dependencias necesarias:
4. Descarga los tres CSV desde el material del curso y ubícalos en `datasets/`.
5. Revisa las rutas de lectura en el notebook. Si trabajas desde la raíz del repositorio, utiliza `datasets/plans.csv`, `datasets/users_latam.csv` y `datasets/usage.csv`. Si ejecutas el notebook en otro entorno, ajusta las rutas a esa ubicación.
6. Reinicia el kernel y ejecuta todas las celdas **en orden**, desde la carga hasta el análisis ejecutivo.
7. Comprueba que se generen las tablas agregadas, histogramas, boxplots y segmentos de clientes.

## Reproducibilidad y limitaciones

- El análisis corresponde a los archivos facilitados en el curso y al periodo de referencia indicado en el proyecto.
- Los valores atípicos se detectan estadísticamente, pero no implican por sí mismos errores o fraude.
- La segmentación describe el comportamiento observado; no demuestra causalidad ni rentabilidad.
- Para reproducir exactamente las cifras, utiliza los mismos archivos originales y reglas de limpieza del notebook.

## Autoría

Proyecto académico de análisis de datos — Sprint 7, ConnectaTel.
