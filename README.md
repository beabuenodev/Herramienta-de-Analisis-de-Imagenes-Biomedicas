# Herramienta de Análisis de Imágenes Biomédicas

Herramienta de análisis y segmentación de imágenes biomédicas utilizando redes neuronales profundas y técnicas de inteligencia artificial explicable (XAI).

## Descripción General

Este proyecto implementa un sistema de análisis de imágenes médicas con capacidades de segmentación automática para diferentes estructuras cerebrales basado en arquitecturas de redes neuronales convolucionales. El sistema incluye modelos entrenados y técnicas de interpretabilidad para explicar las predicciones del modelo.

## Características

- Segmentación automática de estructuras cerebrales utilizando UNET con backbone RadImageNet
- Análisis de isquemia cerebral
- Técnicas de explicabilidad (XAI) para interpretación de resultados
- Generación de reportes y visualizaciones
- Interfaz modular para análisis flexible

## Requisitos

- Python 3.8+
- TensorFlow 2.x
- NumPy
- Pandas
- Scikit-learn
- OpenCV
- Matplotlib

## Estructura del repositorio

```text
.
├── dataset/
├── explainability/
│   ├──XAI/
│   ├──XAI_Cerebro_Explainability.ipynb
│   └──XAI_Isquemia_Explainability.ipynb
├── test_dataset/
├── models/
├── graphs/
├── Tools/
│   ├── GraphTester.ipynb
│   └── RoiConverter.ipynb
├── Trainer.ipynb
├── Tester.ipynb
├── Segmentation_Interface_Notebook.ipynb
└── Training_Interface_Notebook.ipynb
```

## Descripción de carpetas y archivos

### `dataset/`

Contiene el dataset utilizado durante la fase de entrenamiento de los modelos.

Esta carpeta incluye las imágenes y sus correspondientes máscaras o anotaciones empleadas para ajustar los modelos de segmentación. Su contenido constituye la base principal del proceso de aprendizaje.

### `test_dataset/`

Contiene el dataset de testeo.

A diferencia del conjunto de entrenamiento, este dataset está formado por sujetos externos al entrenamiento. Esto permite evaluar la capacidad de generalización de los modelos sobre datos no vistos previamente.

### `models/`

Contiene los modelos entrenados en formato `.h5`.

En esta carpeta se almacenan los modelos finales utilizados para la segmentación:

- Modelo de segmentación de cerebro.
- Modelo de segmentación de isquemia.
- Modelo transfer learning RadImageNet.

> **Nota:** el modelo de transfer learning basado en RadImageNet no se incluye en este repositorio por restricciones de licencia.  
> Debe descargarse manualmente desde el repositorio oficial de RadImageNet:
>
> https://github.com/BMEII-AI/RadImageNet
>
> En el README oficial se enlazan los pesos preentrenados de TensorFlow. Una vez descargado, el archivo debe colocarse en esta carpeta con el  nombre: RadImageNet-ResNet50_notop.h5

### `graphs/`

Contiene las gráficas generadas durante la evaluación de los modelos.

Estas gráficas permiten analizar visualmente el rendimiento obtenido, facilitando la comparación de resultados y la interpretación del comportamiento de los modelos.

### `Tools/`

Carpeta que contiene herramientas auxiliares utilizadas durante el desarrollo y la evaluación del proyecto.

#### `GraphTester.ipynb`

Notebook utilizado para evaluar los modelos entrenados.

Permite comprobar los resultados obtenidos por los modelos sobre el conjunto de testeo, generar métricas de evaluación y producir gráficas comparativas para analizar el rendimiento de la segmentación.

#### `RoiConverter.ipynb`

Notebook encargado de convertir archivos `.ROI` a formato `.PNG`.

Esta conversión permite transformar anotaciones o regiones de interés en máscaras compatibles con el flujo de trabajo del proyecto.

### `Trainer.ipynb`

Notebook principal de entrenamiento.

Contiene el proceso necesario para preparar los datos, definir la arquitectura del modelo, entrenarlo y guardar los pesos resultantes en formato `.h5`.

### `Segmentation_Interface_Notebook.ipynb`

Notebook diseñado para el uso final de los modelos de segmentación.

Este notebook permite al usuario cargar una imagen y obtener la segmentación generada por los modelos entrenados. Está preparado para ejecutarse en línea desde **Google Colab** y cuenta con una interfaz limpia y sencilla, pensada para que el usuario final pueda utilizarlo sin necesidad de conocimientos de informática o programación.

### `Training_Interface_Notebook.ipynb`

Notebook funcional orientado al entrenamiento de nuevos modelos por parte del usuario.

Actualmente se encuentra en desarrollo y se plantea como trabajo futuro. Su objetivo es permitir que un usuario pueda entrenar un modelo para una patología nueva mediante una interfaz accesible, también ejecutable desde **Google Colab**.

Al igual que el notebook de segmentación, está diseñado para ofrecer una experiencia clara y guiada, evitando que el usuario final necesite interactuar directamente con el código.

## Uso mediante Google Colab

Los notebooks:

- `Segmentation_Interface_Notebook.ipynb`
- `Training_Interface_Notebook.ipynb`

están pensados para ejecutarse en línea mediante **Google Colab**.

Esto permite que el usuario final pueda utilizar las funcionalidades principales del proyecto sin instalar dependencias localmente y sin requerir conocimientos técnicos avanzados. La interfaz está diseñada para ser simple, directa y orientada al flujo de trabajo real del usuario.