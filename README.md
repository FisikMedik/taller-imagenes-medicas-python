# Análisis de datos médicos · ML Honduras 2026

## Imágenes médicas con Python

**Juan Calderón · UNAH**  
**Viernes 27 de noviembre de 2026 · 13:30–14:30 · Honduras (UTC−6)**

Taller introductorio de la [Escuela de Machine Learning y Data Science en Honduras](https://machine-learning-honduras.org/). Fecha y título según el [programa público](https://machine-learning-honduras.org/programa/), consultado el 23 de noviembre de 2026. Revisa esa página por si la organización comunica cambios.

**[Página del taller: todos los accesos](https://FisikMedik.github.io/taller-imagenes-medicas-python/)**

[![Abrir el cuaderno de la sesión en Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/FisikMedik/taller-imagenes-medicas-python/blob/main/Taller_en_vivo_60min.ipynb)

[Diapositivas web](https://FisikMedik.github.io/taller-imagenes-medicas-python/presentacion.html) · [Presentación PDF](Presentacion_taller.pdf) · [PowerPoint editable](Presentacion_taller.pptx) · [Explorador visual](https://FisikMedik.github.io/taller-imagenes-medicas-python/explorador.html)

**Ampliación opcional:** [De radiografías a predicciones: un primer modelo de ML](https://fisikmedik.github.io/taller-imagenes-medicas-python/modulo_ml.html) · [Abrir el módulo en Colab](https://colab.research.google.com/github/FisikMedik/taller-imagenes-medicas-python/blob/main/Modulo_ML_radiografias.ipynb)

![Tres cortes de la misma plantilla cerebral: axial, coronal y sagital](imagenes/mri_intensity.png)

*Una plantilla cerebral, tres planos. Las imágenes proceden de una referencia pública MNI152; no son estudios privados de pacientes.*

## Empieza aquí

1. Abre el **[cuaderno en vivo de 60 minutos](https://colab.research.google.com/github/FisikMedik/taller-imagenes-medicas-python/blob/main/Taller_en_vivo_60min.ipynb)**. Inicia sesión en Google y guarda una copia si deseas conservar tus cambios.
2. La galería inicial ya muestra tres cortes del cerebro. Ejecuta los pasos **1A–1E** para preparar la sesión y **1F–1G** para volver a dibujarlos, pulsando el triángulo de cada celda o **Mayús + Enter**. Usa CPU; no necesitas GPU ni conectar tus archivos de Drive al cuaderno.
3. Sigue las celdas en orden. Predice qué cambiará, modifica un parámetro y compara. Cada ejercicio ofrece una pista y una solución explicada.

El **[explorador visual](https://FisikMedik.github.io/taller-imagenes-medicas-python/explorador.html)** permite empezar sin programar y sirve de alternativa si Colab no está disponible. Descarga `explorador.html` para abrirlo sin internet: sus datos están incluidos en el propio archivo.

No necesitas leer todo el libro antes de asistir. Como lectura previa opcional, observa las figuras y la introducción a MNI152 y Nilearn del **[manual ilustrado en PDF](Guia_visual_imagenes_medicas.pdf)**. Si nunca has usado GitHub o Colab, consulta la **[guía de acceso](Guia_GitHub_paso_a_paso.pdf)**.

## Dos ritmos de aprendizaje

| Recurso | Cuándo usarlo | Qué incluye |
|---|---|---|
| [Cuaderno en vivo](Taller_en_vivo_60min.ipynb) | Durante la hora del taller | 8 bloques temáticos repartidos en 28 celdas de código breves, galería inicial, resultados intermedios y ejercicios resueltos. |
| [Presentación](https://FisikMedik.github.io/taller-imagenes-medicas-python/presentacion.html) | Para seguir la explicación o facilitarla | 16 diapositivas, con seis demostraciones web que enlazan controles, código y resultados. PDF y PowerPoint con vistas estáticas y notas. |
| [Explorador](https://FisikMedik.github.io/taller-imagenes-medicas-python/explorador.html) | Antes, durante o sin Python | Tres cortes, ventana de contraste, histograma y máscara por percentil; sin dependencias web. |
| [Cuaderno completo](https://colab.research.google.com/github/FisikMedik/taller-imagenes-medicas-python/blob/main/Taller_imagenes_medicas.ipynb) | Estudio posterior, en varias sesiones | 24 lecciones detalladas, salidas guardadas, matrices, filtros y ampliaciones. |
| [Manual ilustrado](Guia_visual_imagenes_medicas.pdf) | Consulta y lectura autónoma | 97 páginas, 8 capítulos, 3 anexos, 15 tutoriales y 31 figuras diferentes. |
| [Módulo opcional de ML](modulo_ml.html) | 45–60 minutos adicionales o estudio posterior | 12 celdas explicadas: radiografías públicas, regresión logística, validación, predicciones y errores. |

El manual explica qué es un píxel, cómo leer una matriz, de dónde procede ICBM152 y qué hace Nilearn. Distingue imagen individual, plantilla, atlas y espacio de referencia. Sus tutoriales combinan código, salida e interpretación. El **[proyecto LaTeX completo](Fuente_LaTeX_manual.zip)** contiene los recursos necesarios para editarlo y recompilarlo; también puedes leer la [fuente principal](Guia_visual_imagenes_medicas.tex).

<a href="Guia_visual_imagenes_medicas.pdf"><img src="Portada_manual.png" alt="Portada del manual Imágenes médicas con Python" width="230"></a>

Las figuras científicas se obtienen de datos y cálculos documentados. La portada del libro es una ilustración conceptual generada con IA.

## Presentación interactiva: sigue el código y su resultado

Abre la **[presentación web](https://fisikmedik.github.io/taller-imagenes-medicas-python/presentacion.html#7)**. En las diapositivas 7–12, pulsa **Siguiente paso**: se resalta una instrucción, se explica su efecto y aparece la salida. Los controles permiten cambiar un valor y comparar. **Restaurar ejemplo** devuelve los parámetros de referencia.

| Demostración | Qué puedes probar |
|---|---|
| [Contraste](https://fisikmedik.github.io/taller-imagenes-medicas-python/presentacion.html#7) | Cambiar corte y ventana; comprobar que los valores originales se conservan. |
| [Histograma](https://fisikmedik.github.io/taller-imagenes-medicas-python/presentacion.html#8) | Reordenar 36 valores, cambiar intervalos y comprobar la suma de los conteos; después pasar al cerebro. |
| [Percentil y máscara](https://fisikmedik.github.io/taller-imagenes-medicas-python/presentacion.html#9) | Relacionar un percentil con su umbral, selección y denominador. |
| [Curva y región](https://fisikmedik.github.io/taller-imagenes-medicas-python/presentacion.html#10) | Comparar igualdad y desigualdad sobre el mismo corte cerebral. |
| [Ventana de filtro 3×3](https://fisikmedik.github.io/taller-imagenes-medicas-python/presentacion.html#11) | Ver los nueve vecinos, calcular media/mediana/pesos y guardar cada valor en una matriz nueva. |
| [Cambios y bordes](https://fisikmedik.github.io/taller-imagenes-medicas-python/presentacion.html#12) | Comparar una fila uniforme, una rampa y un salto; seguir cada resta antes de ver Sobel. |

La web muestra **Python equivalente** y calcula estas demostraciones en JavaScript; no instala ni ejecuta un intérprete de Python. En el cuaderno de Colab se ejecuta Python. Las curvas de los seis niveles se calcularon previamente con Matplotlib. La presentación lleva sus datos y funciona sin conexión al descargarla; Colab y los enlaces externos necesitan internet.

Las copias **PDF y PowerPoint son estáticas**. Para mover los controles utiliza la presentación web. Las notas del instructor mantienen tiempos, preguntas y soluciones.

El [explorador](explorador.html) también enlaza controles, instrucciones y cifras. Los cuadernos comienzan con imágenes visibles y dejan las respuestas en apartados desplegables para intentar resolver las preguntas primero.

## Módulo opcional: de radiografías a predicciones

Esta ampliación permite **entrenar y evaluar un primer modelo de aprendizaje automático** con imágenes médicas. Reserva **45–60 minutos adicionales**; la sesión principal del programa sigue durando una hora. Si sólo se solicita una demostración de 15 minutos, utiliza las **salidas guardadas de las celdas 1, 6, 9 y 11**. Para ejecutar el cuaderno, comienza en la primera celda y sigue las doce en orden.

**[Leer el tutorial visual sin ejecutar código](modulo_ml.html)** · **[Practicar en Google Colab](https://colab.research.google.com/github/FisikMedik/taller-imagenes-medicas-python/blob/main/Modulo_ML_radiografias.ipynb)** · [Descargar el cuaderno](Modulo_ML_radiografias.ipynb) · [Guía ilustrada en PDF](Guia_modulo_ML.pdf)

El recorrido comienza con radiografías y explica qué son una muestra, una característica y una etiqueta. Después transforma cada imagen de 28 × 28 píxeles en 784 valores, compara con una regla que siempre predice la clase mayoritaria y entrena una **regresión logística**. Es un clasificador supervisado que funciona con CPU; no es una red neuronal convolucional. Las explicaciones acompañan al código, a las figuras y a los ejercicios resueltos.

Entrenamiento ajusta los pesos; validación elige entre tres valores de `C`; prueba se utiliza al final, después de fijar el modelo y el umbral. Los experimentos de umbral utilizan sólo validación. Se interpretan la matriz de confusión, sensibilidad, especificidad y exactitud equilibrada, y se muestran aciertos y errores con un criterio de selección declarado.

**Datos:** [PneumoniaMNIST](https://medmnist.com/), una colección pública de radiografías pediátricas reducidas y etiquetadas. El archivo original de [Zenodo](https://zenodo.org/records/10519652) se distribuye intacto bajo **CC BY 4.0**. Para esta adaptación docente se retiran 18 copias exactas adicionales del entrenamiento y 8 imágenes de validación idénticas a entrenamiento: se utilizan **4690 / 516 / 624 imágenes**. La prueba oficial permanece completa, incluidas tres copias adicionales documentadas. El NPZ no contiene identificadores para comprobar separación por pacientes; eliminar copias exactas no certifica esa independencia. Consulta la [procedencia, licencia y auditoría](datos/FUENTES_PneumoniaMNIST.txt).

La preparación inicial descarga el archivo público si no está disponible y verifica su huella. No se necesitan GPU, acceso a Drive ni estudios propios. Para uso local, conserva la carpeta `datos` e instala [requisitos_ml.txt](requisitos_ml.txt) en tu entorno de Python. Si ya creaste el entorno de Windows descrito más abajo, ejecuta:

```powershell
.\.venv\Scripts\python.exe -m pip install -r requisitos_ml.txt
.\.venv\Scripts\python.exe -m jupyterlab
```

Abre `Modulo_ML_radiografias.ipynb`. Las salidas están guardadas y la [lectura web](modulo_ml.html) incluye sus imágenes para consultar el tutorial sin ejecutar. La guía complementaria tiene **20 páginas**. El [proyecto LaTeX completo](Fuente_LaTeX_modulo_ML.zip), la [fuente principal](Guia_modulo_ML.tex) y los [resultados de referencia](resultados_modulo_ml.json) permiten revisar y reutilizar el material.

**Alcance:** ejercicio educativo sobre etiquetas de un conjunto público. Las imágenes reducidas no sirven para aprender diagnóstico visual, y la puntuación del modelo no es un riesgo clínico calibrado. Estos resultados no demuestran rendimiento en otras personas, edades u hospitales.

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

La **sesión principal de 60 minutos** introduce la visualización y el procesamiento previo al aprendizaje automático. El **módulo opcional adicional** sí entrena un clasificador con radiografías públicas. Ambos son recursos educativos; ninguno constituye una evaluación diagnóstica validada.

## Abrir el cuaderno en Google Colab

Necesitas una computadora con navegador e internet. No necesitas instalar Python, disponer de GPU ni conectar tu Google Drive al cuaderno.

1. Pulsa **Abrir en Google Colab** en la parte superior de esta página.
2. Inicia sesión en Google si Colab lo solicita. Para conservar tus cambios, elige **Archivo → Guardar una copia en Drive**. Esto guarda tu cuaderno; no monta tus archivos de Drive en la sesión.
3. Pulsa el botón triangular de la primera celda o usa **Mayús + Enter**. Una celda es un bloque de código; su resultado aparece debajo. Espera a que termine antes de continuar.
4. Ejecuta las siguientes celdas en orden. 1A prepara las bibliotecas, 1B las importa y 1C carga la plantilla; 1D–1E comprueban su geometría y 1F–1G preparan y dibujan los planos. Cada paso indica qué observar y qué volver a ejecutar.
5. Cuando llegues a una indicación **Cambia**, modifica sólo el parámetro propuesto, ejecuta de nuevo y compara la imagen. Luego consulta la respuesta explicada.

La primera ejecución puede tardar mientras se instalan las bibliotecas que falten. Usa el entorno normal de **CPU**. La plantilla se carga desde `datos/mni152_2mm.nii.gz` si ese archivo está disponible; al abrir sólo el cuaderno en Colab, se obtiene mediante Nilearn.

Si aparece un mensaje como `NameError`, probablemente falta ejecutar una celda anterior. Vuelve a la primera y continúa en orden. Si reinicias la sesión, también debes volver a crear sus variables. Para una explicación ilustrada de archivos, enlaces y botones, consulta la [guía de GitHub y Colab](Guia_GitHub_paso_a_paso.pdf).

## Ruta preparada para una sesión de una hora

Utiliza **Taller_en_vivo_60min.ipynb** en la sesión. Prepara los pasos 1A–1E antes de comenzar; las salidas guardadas también permiten seguir el razonamiento si la conexión tarda. La presentación incluye notas para explicar cada imagen y repartir el tiempo.

| Minutos | Actividad | Qué debe poder explicar el participante |
|---|---|---|
| 0–10 | Primera imagen y tres planos | Una imagen contiene valores en una rejilla; la plantilla no es un paciente nuevo. |
| 10–20 | Geometría y contraste | Un índice no es una distancia; cambiar la ventana no cambia la matriz. |
| 20–35 | Histograma, percentil y máscara | Qué cuenta cada barra, por qué se excluye el fondo y qué selecciona el umbral. |
| 35–43 | Curvas de nivel sobre el cerebro | Una curva une posiciones de igual intensidad; una máscara selecciona una región. |
| 43–55 | Filtros y Sobel | Suavizar reduce variaciones y también puede borrar detalles; Sobel mide cambios. |
| 55–60 | Tres preguntas resueltas | Explicar visualización, significado de una máscara y separación por pacientes. |

El cuaderno completo de 24 lecciones es material de profundización. No se pretende ejecutar y explicar todo ese recorrido durante la hora asignada.

## Para quien facilita el taller

1. Abre la [presentación web](https://FisikMedik.github.io/taller-imagenes-medicas-python/presentacion.html), su sección de notas y el cuaderno en vivo en dos pestañas. Descarga también el PDF y `explorador.html` como respaldo.
2. Ejecuta el cuaderno en orden antes de la sesión. Comprueba la imagen inicial, el histograma, las curvas del cerebro y la comparación de bordes.
3. Pide una predicción antes de cada variación. Mantén una sola modificación por vez y utiliza las pistas antes de mostrar la solución.
4. Si la instalación se retrasa, continúa con las salidas guardadas y el explorador. Reserva los últimos cinco minutos para las tres preguntas, aunque debas dejar una variación como tarea.
5. Al cerrar, enlaza con ML: los filtros de este taller se especifican manualmente; una red convolucional aprende filtros a partir de datos y un objetivo. Entrenar y evaluar exige datos independientes, etiquetas pertinentes y separación adecuada por pacientes. Esta plantilla no constituye un conjunto de entrenamiento clínico.
6. Si se solicita profundizar en aprendizaje automático, abre el [módulo opcional de radiografías](modulo_ml.html). Usa sus salidas guardadas para la demostración breve y acuerda tiempo adicional para la práctica completa; no intentes añadir sus doce celdas a la hora ya programada.

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

En JupyterLab, abre `Taller_en_vivo_60min.ipynb` para la ruta breve o `Taller_imagenes_medicas.ipynb` para el recorrido completo y ejecuta las celdas en orden. Mantén abierta la terminal mientras trabajas. Para volver otro día, abre una terminal en la misma carpeta y ejecuta sólo la última línea. Si usas otra instalación compatible de Python, adapta la primera línea a su versión.

### Comprobación de esta edición

La revisión del 23 de noviembre de 2026 incorpora una ruta breve, una presentación y una página pública de acceso. En la versión anterior de ocho celdas, el cuaderno en vivo se ejecutó completo con el archivo local y con la carga de Nilearn; ambas rutas produjeron matrices idénticas. Esa versión de ocho celdas también se ejecutó desde el enlace público en Google Colab con CPU el 23 de noviembre: percentil 90 de 0.878431, 523 de 4 859 posiciones seleccionadas y conteos Sobel de 2 471/1 495 antes/después del suavizado. El entorno Colab utilizó NumPy 2.4.6, Matplotlib 3.10.0, NiBabel 5.4.2, SciPy 1.16.3 y Nilearn 0.12.1.

El explorador se comprobó en pantalla de escritorio y teléfono, incluidos sus controles de teclado, cambios de corte, ventana y máscara. Sus números e histogramas coinciden con los cálculos NumPy sobre el archivo distribuido. El manual y el cuaderno completo conservan la validación de la edición anterior descrita a continuación.

Las 24 celdas se ejecutaron localmente utilizando la plantilla incluida. El entorno de comprobación utilizó Python 3.12.14, Nilearn 0.12.1, NumPy 2.5.4, Matplotlib 3.11.2, NiBabel 5.4.2 y SciPy 1.18.1. El cuaderno conserva las salidas de esa ejecución. También se ejecutaron las 24 celdas desde el enlace público en Google Colab el 16 de noviembre de 2026, con un entorno de CPU y la carga alternativa de la plantilla mediante Nilearn. Se comprobó que la última celda terminó y mostró 232 posiciones sustituidas de un corte de 11 583 píxeles.

`requirements.txt` mantiene intervalos de versiones compatibles; no es una copia congelada de todas las dependencias del entorno de comprobación.

Las **12 celdas del módulo opcional de radiografías** se ejecutaron localmente en CPU, con 12 salidas gráficas y sin advertencias. Se utilizó Python 3.12.14, NumPy 2.5.4, Matplotlib 3.11.2 y scikit-learn 1.9.1. El modelo eligió `C=0.1` mediante validación; el umbral de prueba se fijó previamente en `0.5`. Las figuras y las salidas guardadas corresponden a esa ejecución local documentada. Los conteos, métricas, exclusiones y versiones están en [resultados_modulo_ml.json](resultados_modulo_ml.json).

También se ejecutaron correctamente las doce celdas en **Google Colab con CPU el 23 de noviembre de 2026**, con NumPy 2.4.6, Matplotlib 3.10.0 y scikit-learn 1.6.1. En ese entorno, validación eligió `C=1`: obtuvo una exactitud equilibrada de 95.28 %, frente a 95.05 % para `C=0.1`. La prueba produjo `[[162,72],[11,379]]` (filas = referencia, columnas = predicción), con 86.70 % de exactitud y 83.21 % de exactitud equilibrada. La ejecución local produjo `[[158,76],[14,376]]` con `C=0.1`.

Los intervalos de [requisitos_ml.txt](requisitos_ml.txt) no congelan un entorno idéntico. Las diferencias entre versiones pueden modificar el ajuste numérico, los resultados y la opción seleccionada cuando sus valores de validación son cercanos. **No cambies el modelo después de mirar prueba para reproducir los números del PDF**: conserva la selección hecha con validación y registra tus versiones y resultados. Estas comprobaciones de ejecución no equivalen a validación clínica ni demuestran independencia entre pacientes.

El manual se compiló con XeLaTeX y se revisaron visualmente sus 97 páginas. También se extrajo el ZIP de la fuente en una carpeta independiente y se recompiló: conserva las 97 páginas y el mismo contenido textual. El generador portátil reprodujo las 20 figuras nuevas con huellas SHA-256 idénticas. El paquete incluye las imágenes ya preparadas, los datos públicos, las fuentes de código con su licencia y las instrucciones de compilación; Python solo se necesita si deseas regenerar las figuras.

## Archivos del repositorio

- [`index.html`](index.html) y [`estilo_web.css`](estilo_web.css): página pública del taller, publicada mediante GitHub Pages.
- [`Taller_en_vivo_60min.ipynb`](Taller_en_vivo_60min.ipynb): ruta breve de la sesión, con salidas guardadas.
- [`presentacion.html`](presentacion.html), [`Presentacion_taller.pdf`](Presentacion_taller.pdf) y [`Presentacion_taller.pptx`](Presentacion_taller.pptx): diapositivas web, copia para lectura y versión editable.
- [`explorador.html`](explorador.html): herramienta autónoma con datos incorporados; puede abrirse sin conexión.
- [`Modulo_ML_radiografias.ipynb`](Modulo_ML_radiografias.ipynb) y [`modulo_ml.html`](modulo_ml.html): práctica opcional de aprendizaje automático y lectura completa con código, explicaciones y salidas.
- [`Guia_modulo_ML.pdf`](Guia_modulo_ML.pdf), [`Guia_modulo_ML.tex`](Guia_modulo_ML.tex) y [`Fuente_LaTeX_modulo_ML.zip`](Fuente_LaTeX_modulo_ML.zip): guía adicional y fuentes para editarla.
- [`requisitos_ml.txt`](requisitos_ml.txt) y [`resultados_modulo_ml.json`](resultados_modulo_ml.json): bibliotecas y ficha de la ejecución del módulo.
- [`datos/pneumoniamnist.npz`](datos/pneumoniamnist.npz) y [`datos/FUENTES_PneumoniaMNIST.txt`](datos/FUENTES_PneumoniaMNIST.txt): archivo público original y atribución con auditoría documentada.

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

La sesión principal utiliza la **plantilla T1 MNI152 distribuida con Nilearn 0.12.1**, remuestreada a 2 mm para esta práctica. Es una referencia anatómica agregada, no una colección de pacientes independientes. La matriz pequeña, las superficies matemáticas y el ruido se generan con código. El repositorio no incorpora archivos clínicos privados del facilitador.

El módulo opcional utiliza **PneumoniaMNIST 28 × 28**, de Yang y colaboradores, derivado de radiografías de Kermany y colaboradores. Se conserva su licencia **CC BY 4.0**, su atribución y el archivo original. Las transformaciones del conjunto, las exclusiones de la adaptación docente y las limitaciones de privacidad e independencia se describen en [datos/FUENTES_PneumoniaMNIST.txt](datos/FUENTES_PneumoniaMNIST.txt). MedMNIST declara que estos datos no están destinados a uso clínico.

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

## Relación con los materiales de la escuela

La organización de esta edición —acceso web, diapositivas, Colab, ejercicios con pistas y soluciones, repositorio y fuentes— toma como referencia los [materiales publicados por la escuela](https://machine-learning-honduras.org/materiales/), los de [Edith Natalia Villegas](https://edithvillegas.github.io/introduccion-ml-redes-neuronales/) y los de [Daniela Pinto Veizaga](https://dapivei.github.io/escuela-machine-learning-honduras-2026/) y las [presentaciones de Carlos Enmanuel Soto Lopez](https://carlossoto362.github.io/pwf_honduras_slides/main.html). Son prácticas docentes observadas, no una rúbrica oficial ni una aprobación formal de este material por la organización.

El sitio es el recurso del expositor y se mantiene en su repositorio personal. La información institucional y posibles cambios de horario corresponden a la [web oficial](https://machine-learning-honduras.org/).

**Autor del material docente:** Juan Calderón · **Revisión de materiales, acceso y sesión:** 25 de noviembre de 2026 · **Edición del manual:** 25 de noviembre de 2026.

### Revisión didáctica del 25 de noviembre de 2026

Se adaptó la relación entre controles, código y resultados observada en los materiales de Daniela y Carlos, y la explicación por ventanas de las convoluciones de Natalia. Las demostraciones, figuras y ejemplos de esta revisión son propios del taller. Los dos manuales conservan sus fuentes LaTeX. La ruta de una hora conserva ocho bloques temáticos, ahora repartidos en 28 celdas breves; las 24 lecciones completas y el módulo de ML quedan como ampliaciones. Los ejemplos de ML introducen la suma ponderada y una matriz de confusión con cuatro casos ficticios antes de evaluar radiografías.


### Cuaderno breve reorganizado en pasos pequeños

La revisión del 25 de noviembre conserva los ocho temas y la duración prevista, repartidos en **28 celdas de código**. Los pasos llevan identificadores estables, de **1A** a **8B**, para distinguirlos de los contadores de ejecución de Colab. El código más largo tiene 13 líneas; los textos se reparten en unidades cortas, con explicaciones por línea desplegables, resultados intermedios y una pregunta final por celda. Cada variación indica qué pasos recalcular y cómo restaurar la referencia.

Se ejecutaron las 28 celdas localmente, tanto con el NIfTI incluido como con la carga de Nilearn. Las ocho figuras finales son idénticas a las de la versión anterior y se conservan las matrices y resultados numéricos. También se probaron las variaciones de corte, intervalos, percentil, nivel, sigma y umbral de Sobel, junto con sus recorridos de restauración. Las comprobaciones históricas de Colab descritas arriba corresponden a la versión de ocho celdas.
