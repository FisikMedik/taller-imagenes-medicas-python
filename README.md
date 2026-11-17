# Imágenes médicas con Python desde cero

**Manual ilustrado por capítulos y cuaderno paso a paso para aprender a mirar, medir y transformar una imagen médica.**

[![Abrir en Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/FisikMedik/taller-imagenes-medicas-python/blob/main/Taller_imagenes_medicas.ipynb)

[Leer el manual ilustrado en PDF](Guia_visual_imagenes_medicas.pdf) · [Aprender a usar GitHub y Colab](Guia_GitHub_paso_a_paso.pdf) · [Ver el cuaderno](Taller_imagenes_medicas.ipynb)

[Descargar la fuente LaTeX](Guia_visual_imagenes_medicas.tex) · [Descargar el proyecto LaTeX completo](Fuente_LaTeX_manual.zip)

<a href="Guia_visual_imagenes_medicas.pdf"><img src="Portada_manual.png" alt="Portada del manual Imágenes médicas con Python" width="300"></a>

**95 páginas · 8 capítulos y 3 anexos · 15 tutoriales · 31 figuras diferentes**

![Tres cortes de la misma plantilla cerebral: axial, coronal y sagital](imagenes/mri_intensity.png)

*Una plantilla cerebral, tres planos. Las imágenes proceden de una referencia pública MNI152; no son estudios privados de pacientes.*

Material de **Juan Calderón** para el taller introductorio de imágenes médicas de la [escuela de Machine Learning y Data Science en Honduras](https://machine-learning-honduras.org/).

## Empieza aquí

Si nunca has programado, abre primero el **manual ilustrado**. Está organizado como un libro por capítulos: presenta la procedencia de MNI152 e ICBM152, explica qué hace Nilearn y distingue una imagen individual, una plantilla, un atlas y un espacio de referencia. Después enseña qué es un píxel, cómo leer una matriz y qué significan las instrucciones de Python antes de pasar a histogramas, curvas de nivel, filtros y bordes.

El manual contiene **31 figuras diferentes**, incluidas **20 ilustraciones nuevas**: esquemas de registro y geometría, ejemplos numéricos, comparaciones de procesamiento y curvas de igual intensidad trazadas sobre la imagen de la plantilla cerebral. Las figuras conceptuales ficticias se distinguen de las derivadas de la resonancia. Los 15 tutoriales combinan explicaciones, preguntas resueltas y **código completo, salida e interpretación**, con explicación de cada línea de las celdas seleccionadas. La portada es una ilustración conceptual generada con IA; las figuras científicas del interior son cálculos y visualizaciones documentados.

El **cuaderno** permite reproducir las figuras y cambiar parámetros. Contiene 24 lecciones: las primeras 22 construyen el recorrido principal; las lecciones 23 y 24 amplían el cálculo de media y mediana y la comparación de filtros ante ruido de impulsos.

Las figuras y respuestas están guardadas en el cuaderno para que puedas observarlas antes de ejecutar el código.

Puedes estudiar el material en varias sesiones y detenerte en cada imagen. La ruta de una hora que aparece más abajo utiliza salidas preparadas y una variación breve por bloque; no exige comprender cada línea de código durante la sesión. Para estudiar el libro y el cuaderno con calma, reserva de dos a tres horas o más, según tu experiencia y las prácticas que repitas.

## Qué aprenderás

- Comprender de dónde procede la plantilla MNI152 y distinguir datos, bibliotecas, atlas y espacio de referencia.
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

Las 24 celdas se ejecutaron localmente utilizando la plantilla incluida. El entorno de comprobación utilizó Python 3.12.14, Nilearn 0.12.1, NumPy 2.5.4, Matplotlib 3.11.2, NiBabel 5.4.2 y SciPy 1.18.1. El cuaderno conserva las salidas de esa ejecución. También se ejecutaron las 24 celdas desde el enlace público en Google Colab el 16 de noviembre de 2026, con un entorno de CPU y la carga alternativa de la plantilla mediante Nilearn. Se comprobó que la última celda terminó y mostró 232 posiciones sustituidas de un corte de 11 583 píxeles.

`requirements.txt` mantiene intervalos de versiones compatibles; no es una copia congelada de todas las dependencias del entorno de comprobación.

El manual se compiló con XeLaTeX y se revisaron visualmente sus 95 páginas. También se extrajo el ZIP de la fuente en una carpeta independiente y se recompiló: conserva las 95 páginas y el mismo contenido textual. El generador portátil reprodujo las 20 figuras nuevas con huellas SHA-256 idénticas. El paquete incluye las imágenes ya preparadas, los datos públicos, las fuentes de código con su licencia y las instrucciones de compilación; Python solo se necesita si deseas regenerar las figuras.

## Archivos del repositorio

- [`Guia_visual_imagenes_medicas.pdf`](Guia_visual_imagenes_medicas.pdf): manual ilustrado por capítulos, con explicaciones, ejemplos, código, salidas interpretadas y ejercicios resueltos.
- [`Guia_visual_imagenes_medicas.tex`](Guia_visual_imagenes_medicas.tex): fuente principal del manual en LaTeX; para recompilarla se necesitan los recursos del paquete completo.
- [`Fuente_LaTeX_manual.zip`](Fuente_LaTeX_manual.zip): proyecto completo con fuente, figuras, portada, estilo e instrucciones para XeLaTeX y Overleaf.
- [`Guia_GitHub_paso_a_paso.pdf`](Guia_GitHub_paso_a_paso.pdf): instrucciones para acceder al material y utilizar el cuaderno.
- [`Taller_imagenes_medicas.ipynb`](Taller_imagenes_medicas.ipynb): las 24 lecciones de Python.
- [`datos/mni152_2mm.nii.gz`](datos/mni152_2mm.nii.gz): plantilla cerebral utilizada en los ejemplos locales.
- [`imagenes/`](imagenes/): figuras de apoyo.
- [`requirements.txt`](requirements.txt): bibliotecas para ejecutar el cuaderno localmente.
- [`FUENTES_Y_LICENCIAS.txt`](FUENTES_Y_LICENCIAS.txt): procedencia de datos, aviso íntegro del atlas y referencias.

## Editar y compilar el manual

Para modificar el libro, descarga [el proyecto LaTeX completo](Fuente_LaTeX_manual.zip). El archivo `.tex` por separado sirve para leer el texto fuente; el ZIP reúne también las imágenes y los demás recursos necesarios para producir el PDF. Consulta primero el **README incluido dentro del ZIP**, que indica la organización del proyecto y los pasos de compilación.

En [Overleaf](https://www.overleaf.com/), crea un proyecto mediante **New Project → Upload Project** y sube el ZIP. Conserva su estructura de carpetas, selecciona el documento principal indicado en su README y elige **XeLaTeX** como compilador antes de recompilar. Las instrucciones oficiales explican cómo [subir un proyecto completo](https://www.overleaf.com/learn/Uploading_a_project) y [seleccionar el compilador](https://docs.overleaf.com/getting-started/recompiling-your-project/selecting-a-tex-live-version-and-latex-compiler).

También puedes compilar localmente con XeLaTeX siguiendo las instrucciones del paquete. Editar el manual y ejecutar el cuaderno son tareas independientes: no necesitas LaTeX ni Overleaf para leer el PDF o practicar con Python.

## Datos fuentes y licencias

Utilizamos la **plantilla T1 MNI152 distribuida con Nilearn 0.12.1**, remuestreada a 2 mm para esta práctica. Es una referencia anatómica agregada, no una colección de pacientes independientes. La matriz pequeña, las superficies matemáticas y el ruido se generan con código. El repositorio no incorpora archivos clínicos privados del facilitador.

**Nota de procedencia:** la documentación de `load_mni152_template` en Nilearn 0.12.1 describe la plantilla como ICBM152 2009a asimétrica, mientras que el código de esa versión carga el archivo interno `mni_icbm152_t1_tal_nlin_sym_09a_converted.nii.gz`. Conservamos ambas evidencias sin resolver la discrepancia por el nombre del archivo ni afirmar una variante de simetría no confirmada. La fuente, la versión, la derivación y la huella SHA-256 de la copia utilizada están documentadas en [FUENTES_Y_LICENCIAS.txt](FUENTES_Y_LICENCIAS.txt).

El atlas conserva el permiso de uso y distribución de McGill, reproducido íntegramente en [FUENTES_Y_LICENCIAS.txt](FUENTES_Y_LICENCIAS.txt), junto con las referencias solicitadas por su proveedor. Las bibliotecas conservan sus propias licencias. Esas condiciones deben distinguirse de la autoría del texto y del código docente.

Para datos clínicos reales, la guía explica qué debe revisarse antes de compartir: autorización de uso, metadatos, identificadores impresos en píxeles, rasgos faciales y archivos acompañantes. Cambiar un nombre de archivo o convertir DICOM a NIfTI no constituye por sí solo una anonimización.

Referencias principales:

- [MNI152 lineal](https://www.bic.mni.mcgill.ca/ServicesAtlases/ICBM152Lin), [ICBM152 no lineal de 2009](https://www.bic.mni.mcgill.ca/ServicesAtlases/ICBM152NLin2009) y [métodos y cohorte descritos por Fonov y colaboradores](https://pmc.ncbi.nlm.nih.gov/articles/PMC2962759/).
- [Introducción a Nilearn](https://nilearn.github.io/0.12.1/introduction.html), [función de carga MNI152](https://nilearn.github.io/0.12.1/modules/generated/nilearn.datasets.load_mni152_template.html) y [código fuente de Nilearn 0.12.1](https://github.com/nilearn/nilearn/blob/0.12.1/nilearn/datasets/struct.py).
- [Formato NIfTI](https://nifti.nimh.nih.gov/nifti-1/documentation/faq/), [objetos de imagen en NiBabel](https://nipy.org/nibabel/nibabel_images.html), [coordenadas](https://nipy.org/nibabel/coordinate_systems.html) y [orientación de los vóxeles](https://nipy.org/nibabel/image_orientation.html).
- [Python](https://docs.python.org/3/tutorial/) y [NumPy para principiantes](https://numpy.org/doc/stable/user/absolute_beginners.html).
- [Visualización con Matplotlib](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.imshow.html) y [procesamiento de imágenes con SciPy](https://docs.scipy.org/doc/scipy/reference/ndimage.html).
- [Ejemplo de atlas de etiquetas y probabilístico](https://nilearn.github.io/stable/modules/generated/nilearn.datasets.fetch_atlas_harvard_oxford.html) e [identificadores y metadatos de plantillas en TemplateFlow](https://www.templateflow.org/python-client/master/notebooks/01_quickstart.html).
- [Perfiles de confidencialidad DICOM](https://dicom.nema.org/medical/dicom/current/output/chtml/part15/chapter_E.html).
- [Prevención de fuga de información en aprendizaje automático](https://scikit-learn.org/stable/common_pitfalls.html#data-leakage).

**Autor del material docente:** Juan Calderón · **Revisión:** 16 de noviembre de 2026.
