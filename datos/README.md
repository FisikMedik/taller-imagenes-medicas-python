# Datos públicos del taller

## Plantilla cerebral de la sesión base

`mni152_2mm.nii.gz` contiene la plantilla pública T1 MNI152 distribuida por Nilearn 0.12.1, preparada a 2 mm para el cuaderno. Es una referencia anatómica agregada. La documentación de la función y el nombre interno del archivo discrepan sobre su simetría; la nota completa y la huella SHA-256 de esta copia están en [FUENTES_Y_LICENCIAS.txt](../FUENTES_Y_LICENCIAS.txt). No se atribuye una variante de simetría sin confirmación independiente.

Conserva esta carpeta junto a `Taller_imagenes_medicas.ipynb` para utilizar la copia local. La plantilla no contiene un estudio clínico privado del facilitador.

La procedencia, las referencias y el aviso íntegro de McGill están en [FUENTES_Y_LICENCIAS.txt](../FUENTES_Y_LICENCIAS.txt). Ese aviso debe acompañar a los datos cuando los distribuyas.

## Radiografías del módulo de machine learning

`pneumoniamnist.npz` es la copia original de PneumoniaMNIST de 28 × 28 píxeles, distribuida por MedMNIST en Zenodo (registro 10519652). Contiene radiografías pediátricas con etiquetas y particiones oficiales de entrenamiento, validación y prueba. Su licencia es CC BY 4.0; conserva la atribución a MedMNIST y a la fuente de Kermany y colaboradores.

El cuaderno [Modulo_ML_radiografias.ipynb](../Modulo_ML_radiografias.ipynb) utiliza una preparación docente explícita: conserva 4.690 imágenes únicas de entrenamiento, excluye de validación 8 imágenes idénticas a entrenamiento y mantiene las 624 imágenes oficiales de prueba. El archivo aquí distribuido permanece intacto. Prueba contiene tres copias exactas adicionales internas; no se equipara el número de imágenes al de pacientes independientes.

Consulta [FUENTES_PneumoniaMNIST.txt](FUENTES_PneumoniaMNIST.txt) para autores, enlaces, licencia, huellas de integridad, auditoría y límites. El archivo no aporta identificadores para certificar separación por paciente. Estos datos sirven para educación, no para uso clínico.
