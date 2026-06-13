# AlmerIA Viajes - Proyecto IABD 2026

[![AWS RDS](https://img.shields.io/badge/Infrastructure-AWS%20RDS-orange?style=flat-square&logo=amazon-aws)](https://aws.amazon.com/)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat-square&logo=python)](https://www.python.org/)
[![Framework-Gradio](https://img.shields.io/badge/UI%20Framework-Gradio-animation?style=flat-square&logo=gradio)](https://gradio.app/)
[![NLP-BERT](https://img.shields.io/badge/NLP-Transformers%20BERT-green?style=flat-square&logo=huggingface)](https://huggingface.co/)

**AlmerIA Viajes** es una plataforma integral de Ingeniería de Datos e Inteligencia Artificial diseñada para la monitorización reputacional, demográfica y geoespacial del sector turístico en la provincia de Almería. El sistema unifica registros oficiales del catastro hotelero con flujos de opiniones subjetivas de la web, enriqueciéndolos mediante modelos de Deep Learning (*Transformers*) para la toma de decisiones proactivas en la gestión de destinos.

---

## 📊 Presentación Ejecutiva del Proyecto

Para conocer en profundidad la arquitectura del negocio, los desafíos técnicos superados y las líneas de innovación tecnológica de una manera visual y atractiva, accede a nuestra documentación interactiva:

[![Ver Presentación en Gamma](https://img.shields.io/badge/💻_VER_PRESENTACIÓN-GAMMA_APP-darkviolet?style=for-the-badge&logo=gamma&logoColor=white)](https://gamma.app/docs/JJJM-Proyecto-IABD-2026-1va996d2c8m1o0z)

---

## 🛠️ Arquitectura del Stack Tecnológico

El ecosistema se ha diseñado bajo una arquitectura modular por capas funcionales de producción:

* **Ingesta y Core ETL:** `Python`, `Pandas`, `NumPy`. Saneamiento de encodings (Latin-1 a UTF-8) y normalización de esquemas.
* **Procesamiento de Lenguaje Natural (NLP):** `PySentimiento` (Redes neuronales *Transformer* BERT entrenadas para análisis de polaridad y psicología emocional en español) y `SpaCy` (*Part-of-Speech Tagging* para aislamiento de sustantivos y adjetivos clave).
* **Sistemas de Información Geográfica (GIS):** `PyProj` (Algoritmo para la reproyección matemática de coordenadas planas UTM EPSG:25830 a esféricas GPS WGS84 EPSG:4326) y `Folium`.
* **Infraestructura Cloud y Persistencia:** `Amazon Web Services (AWS RDS)` mediante servidor relacional MySQL, gestionado con orquestación de `SQLAlchemy` y `PyMySQL`.
* **Interfaz de Usuario (UX):** `Gradio UI` para la simulación y auditoría de inferencia en tiempo real.

---

## 📁 Estructura del Repositorio

El proyecto sigue estándares de la industria organizando los recursos según su ciclo de vida dentro del pipeline:

```text
sentialmeria-ai/
│
├── .gitignore                      # Exclusión de entornos locales y credenciales secretas de AWS
├── README.md                       # Documentación principal del sistema
├── requirements.txt                # Dependencias del entorno congeladas para producción
│
├── data/
│   └── raw/                        # Datasets primarios fuentes (OpenRTA y reseñas subjetivas)
│       ├── dataset-openrta.csv
│       └── reseñas_subjetivas_almeria.csv
│
├── notebooks/
│   └── PROYECTO_AlmerIA_Viajes2026.ipynb  # Pipeline unificado desarrollado en Google Colab
│
├── src/
│   └── .gitkeep                    # Espacio reservado para futura modularización en scripts puros
│
├── reports/                         
│   └── SentiAlmeria_Dashboard.pbix # Cuadro de mando corporativo de Inteligencia de Negocio
│
├── output/
│   └── SentiAlmeria_Mapa_Clientes.html # Entregable cartográfico autónomo a pantalla completa
│
└── docs/                           # Memorias técnicas, evolución de problemas y retos
    ├── ANTEPROYECTO - AlmerIA Viajes (Idea).pdf
    └── Problemas y soluciones_AlmerIA Viajes.pdf