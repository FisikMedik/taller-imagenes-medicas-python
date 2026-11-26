# Imágenes médicas con Python

**Juan Calderón · UNAH · Escuela de Machine Learning y Data Science en Honduras 2026**

[Todos los materiales](https://fisikmedik.github.io/taller-imagenes-medicas-python/) · [Programa](https://machine-learning-honduras.org/programa/)

**Abrir los visores en el navegador:** [Explorador cerebral](https://fisikmedik.github.io/taller-imagenes-medicas-python/explorador.html) · [Presentación principal](https://fisikmedik.github.io/taller-imagenes-medicas-python/presentacion.html) · [Presentación de ML](https://fisikmedik.github.io/taller-imagenes-medicas-python/presentacion_ml.html) · [Tutorial interactivo de ML](https://fisikmedik.github.io/taller-imagenes-medicas-python/modulo_ml.html)

Estos enlaces abren los controles listos para usar, sin instalar Python ni iniciar sesión en Colab. En la lista de archivos de GitHub, pulsar un archivo `.html` muestra su código; para usarlo, elige uno de los enlaces anteriores.

![Tres cortes de la plantilla cerebral pública MNI152](imagenes/mri_intensity.png)

Aprende a leer imágenes como matrices, cambiar su visualización y aplicar histogramas, máscaras, curvas de nivel, filtros y bordes. El módulo opcional usa radiografías públicas para entrenar y evaluar un clasificador sencillo.

## Elige tu cuaderno

| Ruta | Contenido | Abrir |
|---|---|---|
| Principal · 60 minutos | 8 bloques y 28 pasos; seis gráficos con controles. | [Colab](https://colab.research.google.com/github/FisikMedik/taller-imagenes-medicas-python/blob/main/Taller_en_vivo_60min.ipynb) · [Notebook](Taller_en_vivo_60min.ipynb) |
| ML opcional · 45–60 minutos adicionales | 12 bloques y 58 pasos; regresión logística, validación, métricas y errores. | [Colab](https://colab.research.google.com/github/FisikMedik/taller-imagenes-medicas-python/blob/main/Modulo_ML_radiografias.ipynb) · [Notebook](Modulo_ML_radiografias.ipynb) |
| Ampliación | 24 lecciones detalladas con numeración independiente. | [Colab](https://colab.research.google.com/github/FisikMedik/taller-imagenes-medicas-python/blob/main/Taller_imagenes_medicas.ipynb) |

## Cómo trabajar

1. Abre Colab con CPU y ejecuta las celdas en orden. Las imágenes guardadas permiten mirar antes de ejecutar. Para conservar cambios, usa **Archivo → Guardar una copia en Drive**.
2. Lee la explicación breve encima del código: describe los comandos y sus argumentos. Los identificadores **1A, 1B…** coinciden con los manuales y las presentaciones.
3. Ejecuta la celda de un gráfico para activar sus controles. **Mueve un deslizador y suéltalo:** la figura se recalcula. No necesitas buscar otras celdas para actualizar esa vista.
4. También puedes editar el valor inicial del control en el código, junto al gráfico. Si reinicias la sesión, vuelve a ejecutar desde el comienzo.

En GitHub y en los PDF se ven imágenes de referencia. **Los controles del notebook funcionan al ejecutar Python en Colab o Jupyter.** No requieren GPU ni acceso a tus archivos de Drive.

## Qué puedes cambiar

| Gráfico principal | Controles |
|---|---|
| **2C · Corte y contraste** | `z_mm` solicita una posición; `ventana` ajusta negro y blanco. |
| **3B · Histograma** | Posición y número de intervalos. |
| **4C · Percentil y máscara** | Posición y percentil; se recalculan umbral, selección y porcentaje. |
| **5B · Curva y región** | Posición y nivel de intensidad. |
| **6E · Filtros** | Posición, anchura de Gauss y cantidad de ruido. |
| **7D · Bordes** | Posición, Gauss, ruido y umbral de respuesta Sobel. |

La plantilla tiene planos separados por **2 mm**. Si solicitas **25 mm**, el gráfico muestra el plano nativo más cercano y señala su posición real en el título.

En ML puedes explorar una imagen y sus características, la sigmoide, candidatos ya entrenados, predicciones de **validación**, el umbral de validación y las casillas de errores ya calculadas. Estos controles no cambian el modelo ni el umbral fijados para el informe de prueba.

## Presentaciones y manuales

| Material | Principal | ML opcional |
|---|---|---|
| Presentación interactiva | [Abrir](https://fisikmedik.github.io/taller-imagenes-medicas-python/presentacion.html) | [Abrir](https://fisikmedik.github.io/taller-imagenes-medicas-python/presentacion_ml.html) |
| PowerPoint editable | [Descargar](Presentacion_taller.pptx) | [Descargar](Presentacion_modulo_ML.pptx) |
| Diapositivas en PDF | [Leer](Presentacion_taller.pdf) | [Leer](Presentacion_modulo_ML.pdf) |
| Manual ilustrado | [Leer](Guia_visual_imagenes_medicas.pdf) | [Leer](Guia_modulo_ML.pdf) |
| Fuente LaTeX completa | [Descargar](Fuente_LaTeX_manual.zip) | [Descargar](Fuente_LaTeX_modulo_ML.zip) |

Las presentaciones web incluyen ejemplos manipulables y un panel con el código y la salida guardada de cada paso. **Abrir esta celda en Colab** localiza la celda correspondiente. Los PDF y PowerPoint son estáticos; las notas de PowerPoint incluyen código y explicaciones.

También tienes un [explorador cerebral sin Python](https://fisikmedik.github.io/taller-imagenes-medicas-python/explorador.html), el [tutorial de ML con resultados](https://fisikmedik.github.io/taller-imagenes-medicas-python/modulo_ml.html) y la [guía de GitHub y Colab](Guia_GitHub_paso_a_paso.pdf). El manual principal separa lectura introductoria, ruta de 60 minutos y ampliación.

## Usarlo en tu computadora

Descarga **Code → Download ZIP**, extrae el contenido y abre una terminal en esa carpeta. Con Python instalado, en Windows:

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt -r requisitos_ml.txt
.\.venv\Scripts\python.exe -m jupyterlab
```

La primera línea crea un entorno; la segunda instala las bibliotecas y los controles; la tercera abre JupyterLab. Mantén la terminal abierta. En una sesión posterior basta ejecutar la tercera línea.

## Datos y resultados

El taller usa una **plantilla pública MNI152 de Nilearn**, con vóxeles de 2 mm. ML usa **PneumoniaMNIST**, imágenes de 28 × 28 píxeles con sus etiquetas publicadas. Las licencias, procedencia y modificaciones están en [FUENTES_Y_LICENCIAS.txt](FUENTES_Y_LICENCIAS.txt) y [la ficha de PneumoniaMNIST](datos/FUENTES_PneumoniaMNIST.txt). La portada del manual es una ilustración conceptual generada con IA.

La ejecución local de ML eligió `C=0.1` con validación y fijó el umbral en `0.5`; las cifras y versiones están en [resultados_modulo_ml.json](resultados_modulo_ml.json). Una ejecución documentada de Colab con otras versiones eligió `C=1`. Conserva tus propios resultados: no ajustes el modelo después de mirar prueba para imitar una cifra del manual. Comprobar duplicados exactos no demuestra independencia entre pacientes. El material es educativo y no constituye una herramienta diagnóstica.

Referencias docentes: materiales de [Daniela Pinto](https://dapivei.github.io/escuela-machine-learning-honduras-2026/), [Carlos Soto](https://carlossoto362.github.io/pwf_honduras_slides/main.html) y [Natalia Villegas](https://edithvillegas.github.io/introduccion-ml-redes-neuronales/). Este repositorio contiene los materiales del taller de Juan Calderón.

