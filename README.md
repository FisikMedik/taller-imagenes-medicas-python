# Imágenes médicas con Python desde cero

**Guía visual y cuaderno paso a paso para aprender a mirar, medir y transformar una imagen médica.**

[![Abrir en Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/FisikMedik/taller-imagenes-medicas-python/blob/main/Taller_imagenes_medicas.ipynb)

[Leer la guía visual en PDF](Guia_visual_imagenes_medicas.pdf) · [Aprender a usar GitHub y Colab](Guia_GitHub_paso_a_paso.pdf) · [Ver el cuaderno](Taller_imagenes_medicas.ipynb)

![Tres cortes de la misma plantilla cerebral: axial, coronal y sagital](imagenes/mri_intensity.png)

*Una plantilla cerebral, tres planos. Las imágenes proceden de una referencia pública MNI152; no son estudios privados de pacientes.*

Material de **Juan Calderón** para el taller introductorio de imágenes médicas de la [escuela de Machine Learning y Data Science en Honduras](https://machine-learning-honduras.org/).

## Empieza aquí

Si nunca has programado, abre primero la **guía visual**. Explica qué es un píxel, cómo leer una matriz y qué significan las instrucciones de Python antes de pasar a histogramas, curvas de nivel, filtros y bordes. Cada tema incluye ejemplos y una pregunta con su solución.

El **cuaderno** permite reproducir las figuras y cambiar parámetros. Contiene 24 lecciones: las primeras 22 construyen el recorrido principal; las lecciones 23 y 24 amplían el cálculo de media y mediana y la comparación de filtros ante ruido de impulsos.

Las figuras y respuestas están guardadas en el cuaderno para que puedas observarlas antes de ejecutar el código.

Puedes estudiar el material en varias sesiones y detenerte en cada imagen. La ruta de una hora que aparece más abajo utiliza salidas preparadas y una variación breve por bloque; no exige comprender cada línea de código durante la sesión. Para estudiar el libro y el cuaderno con calma, reserva de dos a tres horas o más, según tu experiencia y las prácticas que repitas.

## Qué aprenderás

- Relacionar una matriz de números con píxeles, vóxeles y tonos de gris.
- Explorar cortes axial, coronal y sagital y distinguir índices de milímetros.
- Cambiar el contraste y explicar qué cambia en la presentación y qué permanece en los datos.
- Construir un histograma contando valores, elegir intervalos y reconocer el efecto del fondo.
- Distinguir percentiles, umbrales, máscaras y curvas de nivel.
- Comparar media, filtro gaussiano y mediana con la misma entrada.
- Observar perfiles de intensidad y medir cambios con Sobel.
- Documentar una secuencia de procesamiento y comprender por qué una evaluación de ML debe separar pacientes.

El taller introduce la **visualización y el procesamiento previo al aprendizaje automático**. No entrena un modelo ni presenta una evaluación diagnóstica.

## Abrir el cuaderno en Google Colab

Necesitas una computadora con navegador e internet. No necesitas instalar Python, disponer de GPU ni conectar tu Google Drive al cuaderno.

1. Pulsa **Abrir en Google Colab** en la parte superior de esta página.
2. Inicia sesión en Google si Colab lo solicita. Para conservar tus cambios, elige **Archivo → Guardar una copia en Drive**. Esto guarda tu cuaderno; no monta tus archivos de Drive en la sesión.
3. Pulsa el botón triangular de la primera celda o usa **Mayús + Enter**. Una celda es un bloque de código; su resultado aparece debajo. Espera a que termine antes de continuar.
4. Ejecuta las siguientes celdas en orden. La primera prepara las bibliotecas y carga la plantilla; las demás utilizan los datos creados antes.
5. Cuando llegues a una indicación **Cambia**, modifica sólo el parámetro propuesto, ejecuta de nuevo y compara la imagen. Luego consulta la respuesta explicada.

La primera ejecución puede tardar mientras se instalan las bibliotecas que falten. Usa el entorno normal de **CPU**. La plantilla se carga desde `datos/mni152_2mm.nii.gz` si ese archivo está disponible; al abrir sólo el cuaderno en Colab, se obtiene mediante Nilearn.

Si aparece un mensaje como `NameError`, probablemente falta ejecutar una celda anterior. Vuelve a la primera y continúa en orden. Si reinicias la sesión, también debes volver a crear sus variables. Para una explicación ilustrada de archivos, enlaces y botones, consulta la [guía de GitHub y Colab](Guia_GitHub_paso_a_paso.pdf).

## Ruta preparada para una sesión de una hora

Antes del taller, abre el cuaderno, prepara las bibliotecas y ejecuta las celdas para comprobar que las figuras están disponibles. Durante la sesión, utiliza esas salidas y realiza una variación breve por bloque. Los tiempos siguientes suponen que la preparación ya terminó; el objetivo es comprender las comparaciones, sin explicar todas las líneas de código en una hora.

- **0–8 minutos — Qué contiene una imagen.** Lecciones 1–3: mirar la plantilla, leer la matriz de 6 × 6 y cambiar un píxel.
- **8–18 minutos — Explorar y representar.** Lecciones 4–7: forma, milímetros, tres planos, movimiento de un corte y contraste.
- **18–30 minutos — Contar y seleccionar.** Lecciones 8–11: histogramas, intervalos, percentiles y máscara por umbral.
- **30–38 minutos — Leer curvas de nivel.** Lecciones 12–14: igualdad de intensidad y diferencia entre una línea y una región seleccionada.
- **38–48 minutos — Comparar filtros.** Lecciones 15–18: una misma realización del ruido y los efectos de media, filtro gaussiano y mediana.
- **48–56 minutos — Observar cambios y bordes.** Lecciones 19–21: perfiles, Sobel y comparación antes y después del suavizado.
- **56–60 minutos — Explicar el recorrido.** Lección 22 y tres preguntas: ¿cambió la imagen o sólo su visualización?, ¿qué representa cada eje del histograma?, ¿qué detalle se pierde al suavizar más?

Las ampliaciones 23 y 24 quedan para después del taller. Retoma las explicaciones línea por línea y repite los ejercicios durante el estudio autónomo de dos a tres horas o más.

## Trabajar en tu computadora con Windows

Esta opción utiliza JupyterLab, una aplicación que abre el cuaderno en el navegador y ejecuta Python en tu computadora. La instalación inicial necesita internet. Después podrás utilizar la plantilla incluida sin descargarla de nuevo.

1. Instala **Python 3.12** desde [python.org](https://www.python.org/downloads/windows/), incluido el lanzador de Python para Windows.
2. En este repositorio, pulsa **Code → Download ZIP** y extrae el archivo. Conserva juntas la carpeta `datos`, el cuaderno y los demás archivos.
3. Abre la carpeta extraída en el Explorador de archivos. Escribe `powershell` en su barra de dirección y pulsa Enter. La terminal se abrirá en esa carpeta.
4. Ejecuta las siguientes líneas, una por una:

```powershell
py -3.12 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m jupyterlab
```

La primera línea crea un entorno separado para las bibliotecas del taller; la segunda las instala; la tercera abre JupyterLab. No hace falta activar el entorno ni cambiar la política de ejecución de PowerShell.

En JupyterLab, abre `Taller_imagenes_medicas.ipynb` y ejecuta las celdas en orden. Mantén abierta la terminal mientras trabajas. Para volver otro día, abre una terminal en la misma carpeta y ejecuta sólo la última línea. Si usas otra instalación compatible de Python, adapta la primera línea a su versión.

### Comprobación de esta edición

Las 24 celdas se ejecutaron localmente utilizando la plantilla incluida. El entorno de comprobación utilizó Python 3.12.14, Nilearn 0.12.1, NumPy 2.5.4, Matplotlib 3.11.2, NiBabel 5.4.2 y SciPy 1.18.1. El cuaderno conserva las salidas de esa ejecución. La ejecución completa en Google Colab y la carga alternativa de la plantilla mediante Nilearn no se probaron en esta revisión.

`requirements.txt` mantiene intervalos de versiones compatibles; no es una copia congelada de todas las dependencias del entorno de comprobación.

## Archivos del repositorio

- [`Guia_visual_imagenes_medicas.pdf`](Guia_visual_imagenes_medicas.pdf): explicaciones, imágenes, ejemplos numéricos y ejercicios resueltos.
- [`Guia_GitHub_paso_a_paso.pdf`](Guia_GitHub_paso_a_paso.pdf): instrucciones para acceder al material y utilizar el cuaderno.
- [`Taller_imagenes_medicas.ipynb`](Taller_imagenes_medicas.ipynb): las 24 lecciones de Python.
- [`datos/mni152_2mm.nii.gz`](datos/mni152_2mm.nii.gz): plantilla cerebral utilizada en los ejemplos locales.
- [`imagenes/`](imagenes/): figuras de apoyo.
- [`requirements.txt`](requirements.txt): bibliotecas para ejecutar el cuaderno localmente.
- [`FUENTES_Y_LICENCIAS.txt`](FUENTES_Y_LICENCIAS.txt): procedencia de datos, aviso íntegro del atlas y referencias.

## Datos fuentes y licencias

La plantilla es una versión T1 MNI152 derivada de **ICBM152 2009 asimétrica, versión a**, distribuida por Nilearn y remuestreada a 2 mm para esta práctica. Es una referencia anatómica agregada, no una colección de pacientes independientes. La matriz pequeña, las superficies matemáticas y el ruido se generan con código. El repositorio no incorpora archivos clínicos privados del facilitador.

El atlas conserva el permiso de uso y distribución de McGill, reproducido íntegramente en [FUENTES_Y_LICENCIAS.txt](FUENTES_Y_LICENCIAS.txt), junto con las referencias solicitadas por su proveedor. Las bibliotecas conservan sus propias licencias. Esas condiciones deben distinguirse de la autoría del texto y del código docente.

Para datos clínicos reales, la guía explica qué debe revisarse antes de compartir: autorización de uso, metadatos, identificadores impresos en píxeles, rasgos faciales y archivos acompañantes. Cambiar un nombre de archivo o convertir DICOM a NIfTI no constituye por sí solo una anonimización.

Referencias principales:

- [Plantilla MNI152 de Nilearn](https://nilearn.github.io/0.12.1/modules/generated/nilearn.datasets.load_mni152_template.html) y [fuente del atlas ICBM152](https://www.bic.mni.mcgill.ca/ServicesAtlases/ICBM152NLin2009).
- [NumPy para principiantes](https://numpy.org/doc/stable/user/absolute_beginners.html) y [coordenadas de imágenes con NiBabel](https://nipy.org/nibabel/coordinate_systems.html).
- [Visualización con Matplotlib](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.imshow.html) y [procesamiento de imágenes con SciPy](https://docs.scipy.org/doc/scipy/reference/ndimage.html).
- [Perfiles de confidencialidad DICOM](https://dicom.nema.org/medical/dicom/current/output/chtml/part15/chapter_E.html).
- [Prevención de fuga de información en aprendizaje automático](https://scikit-learn.org/stable/common_pitfalls.html#data-leakage).

**Autor del material docente:** Juan Calderón · **Revisión:** 16 de noviembre de 2026.
