# Referencias del Capítulo 2

Estado de cada referencia. LEÍDA = se leyó la fuente en esta sesión (9/NOV/2026) y se ubicó el pasaje.

## Agregadas a `references.bib`

| Clave | Respalda | Dónde se sostiene | Estado |
|---|---|---|---|
| `paszke2019pytorch` | Los modelos son programas de Python; diferenciación automática en modo inverso; soporte de GPU | Secciones 4.1 y 4.3 (4.3 en la página 5 del PDF) y abstract | LEÍDA |
| `pedregosa2011scikit` | Biblioteca de aprendizaje automático supervisado y no supervisado; iteradores de validación cruzada con índices de entrenamiento y prueba, incluida la estratificada | Abstract y sección 4 "Code Design" (página 4) | LEÍDA. El paper no trata métricas ni preprocesamiento: para eso usar la documentación oficial |
| `waskom2021seaborn` | Datos bibliográficos de seaborn | Página de JOSS | Solo metadatos (no se leyó el resumen) |
| `kluyver2016jupyter` | Los cuadernos Jupyter combinan código, resultados y explicaciones | Abstract en la página del editor | LEÍDA. Año 2016 a confirmar: la página no lo muestra de forma explícita |
| `oshea2016convolutional` (ya existía) | Generación con GNU Radio; desvanecimiento multicamino, deriva del oscilador y del reloj, ruido gaussiano; dataset público | Secciones "Evaluation Dataset" (p. 3), "Dataset Availability" y "Dataset Parameters" (p. 4), "Generating a dataset" (p. 6) | LEÍDA. Se perdieron los dígitos en la extracción: cifras no citables desde el paper |
| `deepsig2016datasets` | Sintético, 11 modulaciones (8 digitales y 3 analógicas), formato pickle, licencia CC BY-NC-SA 4.0, advertencia de errores conocidos | Página de datasets | LEÍDA |
| `flowers2019rfml` | Autores, licencia BSD-3, cargadores de datasets de DeepSig; no es código oficial de ningún paper | README | LEÍDA. No se confirmó la arquitectura de su CNN |
| `polars2026docs` | Biblioteca de DataFrames con núcleo en Rust, licencia MIT | docs.pola.rs | LEÍDA |
| `python2026about` | Lenguaje de código abierto, administrado por la Python Software Foundation | python.org/about | LEÍDA |
| `microsoft2026directml` | DirectML en vista previa pública para GPU con DirectX 12; instalación con `pip install torch-directml` | Página de Microsoft Learn (fecha 2026-09-08) | LEÍDA. No nombra AMD |
| `microsoft2024torchdirectml` | Versión 0.2.5.dev240914 (septiembre de 2024), instaladores para Python 3.8 a 3.12 | Página de PyPI | LEÍDA. No indica la versión de PyTorch requerida |
| `amd2025pytorchdirectml` | Pide una tarjeta "AMD Radeon RX" o "Radeon PRO" para PyTorch con DirectML | Tutorial de AMD Research | LEÍDA. No nombra la RX 6700 |

### Agregadas el 9/NOV para la justificación de PyTorch y los modelos clásicos

| Clave | Respalda | Dónde se sostiene | Estado |
|---|---|---|---|
| `pytorch2026docs` | `torch.nn` incluye Conv1d, LSTM, GRU, BatchNorm1d, Dropout, Linear y CrossEntropyLoss; `torch.optim` incluye Adam y ReduceLROnPlateau; `torch.utils.data` incluye DataLoader, Dataset y TensorDataset | Páginas nn, optim y data de la documentación 2.15 (actualizadas entre mayo y agosto de 2026) | LEÍDA. La documentación no indica organización responsable ni licencia |
| `paszke2019pytorch` (ya existía) | Las capas son clases de Python y se pueden definir capas propias; DataLoader se ocupa de mezclar, agrupar y paralelizar | Sección 4.1 (p. 3) y sección 4.2 (p. 4) | LEÍDA |
| `sklearn2026docs` | SVC y LinearSVC para clasificación; StandardScaler (media cero, varianza unitaria); Pipeline; GridSearchCV | Páginas svm, preprocessing (8.3.1), compose y grid_search (3.2.1) de la documentación 1.9.1 | LEÍDA en su mayor parte (parte resumida por límite de lectura). train_test_split y confusion_matrix: solo resumen, no se citan |
| `pedregosa2011scikit` (ya existía) | Pipeline combina transformadores y un estimador; GridSearchCV selecciona parámetros por validación cruzada | Sección 4, subsección "Model selection" (p. 4) | LEÍDA |

### Sección 2.2 (redactada el 9/NOV)

- Generación del dataset (modulación de datos reales de voz y texto, aleatorización por bloques en digitales, canal con multicamino, deriva de oscilador y de reloj, ruido gaussiano, ventanas rectangulares; efectos de rotación y giro): `oshea2016convolutional`, secciones "Evaluation Dataset" (p. 3), "Dataset Parameters", "Generating a dataset" (p. 6) y la descripción de efectos de canal (p. 5). LEÍDA.
- Que el paper describe RadioML 2016.04C y no 2016.10A: se apoya en que la página de DeepSig lista ese paper bajo 2016.04C y presenta 2016.10A como versión más limpia que lo reemplaza. Es una inferencia entre dos fuentes leídas, no una afirmación literal de ninguna: revisar.
- "El entrenamiento con datos reales es importante y valioso, trabajo futuro": `oshea2016convolutional`, sección "Evaluation Dataset" (p. 3 a 4). LEÍDA.
- Errores conocidos, no usado en productos, licencia, 11 modulaciones (8 digitales y 3 analógicas), GNU Radio: `deepsig2016datasets`. LEÍDA.
- Cifras propias, sin cita (calculadas de `radioml_metadata_digital.parquet`, `radioml_metadata.parquet` y los `.npy`): 220.000 ejemplos, 160.000 en el subconjunto, 1.000 por modulación y SNR, 20 niveles de -20 a 18 dB en pasos de 2 dB, 2x128 por ejemplo, lista de clases.
- Figuras 2.1 y 2.2: propias, generadas con un script a partir de los `.npy` (primer ejemplo de cada modulación a 18 dB; QPSK a 18, 0, -10 y -20 dB), amplitudes normalizadas por el máximo de cada ejemplo.

## Pendientes (NO verificadas, no usar)

- Harris et al. 2020, Array programming with NumPy, Nature 585:357-362, DOI 10.1038/s41586-020-2649-2: datos bibliográficos vistos en buscador, texto no leído (PMC bloqueó la lectura).
- Virtanen et al. 2020, SciPy 1.0, Nature Methods 17:261-272, DOI 10.1038/s41592-019-0686-2: igual que la anterior.
- Hunter 2007, Matplotlib: A 2D Graphics Environment, Computing in Science & Engineering 9(3):90-95: IEEE devolvió la página vacía.
- Hojas de datos de AMD (Ryzen 5 7600 y Radeon RX 6700): la página agotó el tiempo de espera. El hardware se describe con la medición propia del sistema.
- Documentación oficial de scikit-learn y de PyTorch (para métricas, preprocesamiento y el motivo de la documentación disponible): sin leer.

## Datos propios (sin cita externa)

- Equipo: AMD Ryzen 5 7600 (6 núcleos, 12 hilos), 15,7 GB de RAM, AMD Radeon RX 6700, Windows 11.
- Cantidad de ejemplos, 128 muestras, rango de SNR y lista de clases: calcular de la metadata propia (el paper lista BFSK, el dataset tiene GFSK).
- Versiones de las bibliotecas: `D:\CEIA\Proyecto_AMC\requirements.txt`.
