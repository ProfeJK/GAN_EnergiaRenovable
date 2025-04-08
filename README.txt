GAN ENERGÍA RENOVABLE - PROYECTO DE GENERACIÓN DE DATOS SINTÉTICOS

===============================================
Descripción:
-----------------------------------------------
Este proyecto permite generar datos sintéticos de energías renovables (solar y eólica) utilizando Redes Generativas Antagónicas (GAN) y ecuaciones diferenciales estocásticas (SDE).

Los modelos se entrenan para aprender patrones de series temporales, generando resultados realistas basados en datos reales.

===============================================
Requisitos:
-----------------------------------------------
- Cuenta de Google Drive
- Google Colab
- Archivo 'requirements.txt' en tu carpeta del proyecto
- Código fuente organizado en Drive de la siguiente forma:

/Mi unidad/
└── GAN_EnergiaRenovable/
    ├── models/
    ├── dataloaders/
    ├── training/
    ├── utils/
    ├── sde_gan.py
    ├── requirements.txt
    └── README.txt

===============================================
Instrucciones para ejecutar en Google Colab:
-----------------------------------------------

1. Accede a Google Drive y asegúrate que la carpeta GAN_EnergiaRenovable esté organizada como se indica.

2. Abre Google Colab: https://colab.research.google.com/

3. Monta tu Google Drive:

```python
from google.colab import drive
drive.mount('/content/drive')

4. Ejecuta el archivo de Colab preparado (SDE_GAN_Colab.ipynb) o, manualmente:

project_path = '/content/drive/MyDrive/GAN_EnergiaRenovable'
!pip install -r {project_path}/requirements.txt
!python {project_path}/sde_gan.py

5. Revisa los resultados en tu carpeta:

GAN_EnergiaRenovable/saved_models/sde/

Allí encontrarás:

    Modelos entrenados .pt

    Visualizaciones del proceso en .gif y .png


=============================================== 
Personalizar tus propios datos:

1. Ubica el archivo: dataloaders/sde_dataloader.py

2. Modifica la función get_sde_dataloader() para cargar tu propio dataset. Ejemplo:

import pandas as pd

def get_sde_dataloader(...):
    df = pd.read_csv('/content/drive/MyDrive/GAN_EnergiaRenovable/mis_datos.csv')
    # Asegúrate que las columnas correspondan con las variables que usas.
    ...

3. En el script principal sde_gan.py, cambia las variables:

variables = ["MI_VARIABLE"]
time_features = ["MI_FEATURE_TEMPORAL"]


=============================================== 
Notas adicionales:

✔️ Si se reinicia el entorno de Colab, vuelve a montar Drive y reinstalar dependencias antes de correr el script.

✔️ No necesitas GPU, el código está preparado para CPU.

✔️ Los modelos .pt pueden cargarse luego para generación de nuevos datos o para análisis adicional.
=============================================== Contacto:

Desarrollado por ProfeJK 

