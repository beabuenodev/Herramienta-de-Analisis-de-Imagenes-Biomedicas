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

## Estructura del Proyecto

```
.
├── src/                 # Código fuente
├── models/              # Modelos entrenados (.h5)
├── data/                # Datos (raw y procesados)
├── results/             # Resultados y salidas
├── docs/                # Documentación
├── tests/               # Tests unitarios
├── XAI/                 # Análisis de explicabilidad
└── *.ipynb              # Notebooks de análisis
```

## Requisitos

- Python 3.8+
- TensorFlow 2.x
- NumPy
- Pandas
- Scikit-learn
- OpenCV
- Matplotlib

Consulta [INSTALL.md](docs/INSTALL.md) para instrucciones detalladas de instalación.

## Uso

Para ejecutar análisis sobre imágenes:

```python
from src.segmentation import SegmentationModel

model = SegmentationModel('models/brain_segmentatio_model_RadImageNET.h5')
results = model.predict(image_path)
```

Ver [USAGE.md](docs/USAGE.md) para casos de uso detallados.

## Documentación

- [Instalación](docs/INSTALL.md) - Configuración del entorno
- [Uso](docs/USAGE.md) - Guía de uso
- [Arquitectura](docs/ARCHITECTURE.md) - Descripción técnica

## Resultados

Los resultados del análisis se almacenan en la carpeta `results/` y incluyen:
- Máscaras de segmentación
- Métricas de evaluación
- Visualizaciones
- Análisis XAI

## Licencia

Este proyecto es parte de un Trabajo Fin de Grado.

## Autor

Autores: [Tu nombre]
Universidad: [Tu Universidad]
Año: 2026
