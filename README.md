# 🎵 Análisis Completo de Tendencias y Letras en la Música Popular de Spotify (2000-2022)

## 📌 Introducción

Este proyecto aborda un análisis exhaustivo de la evolución de la música popular desde el año 2000 hasta 2022, utilizando datos de Spotify y letras de canciones recopiladas.

**Objetivos Principales:**

* Explorar la **evolución de características musicales**, popularidad por géneros y atributos de audio.
* Analizar a fondo el **contenido lírico** de las canciones, incluyendo lenguaje, tópicos, frecuencia de palabras y su relación con el contexto social.
* Aplicar **técnicas de Machine Learning** (clustering K-Means, modelos predictivos, redes neuronales) para agrupar canciones, predecir popularidad y extraer insights.
* Utilizar **tecnologías de Big Data** (Docker Compose con Hadoop, Cassandra, NiFi y BigQuery) para gestionar y analizar grandes volúmenes de datos eficientemente.

**Contenido del Proyecto:**

* Análisis de datos y visualizaciones sobre tendencias de popularidad y audio.
* Implementación de algoritmos de clustering y asignación de estado de ánimo.
* Desarrollo y evaluación de modelos de regresión y clasificación para predicción.
* Construcción de una red neuronal para predecir la popularidad de las pistas.
* Código y scripts para la infraestructura de datos distribuida con Docker Compose.
* Consultas y análisis avanzados en BigQuery.
* Scripts para la obtención automatizada de letras de canciones (API y Web Scraping).
* Análisis de NLP sobre letras: estudio lingüístico, modelado de tópicos (LDA), frecuencia, similitud y tendencias contextuales.

---
## 🚀 Contenido del Repositorio

El repositorio sigue una estructura básica para organizar el código, los datos y la documentación:

```text
spotify-popular-music-trends/ # (o el nombre de tu carpeta raíz)
├── data/              # <-- Directorio para los datos utilizados (ver sección "Datos")
├── src/               # <-- Directorio para el código fuente y notebooks
│   └── memroia_v2.ipynb # <-- El cuaderno principal con el análisis
├── .gitignore         # <-- Archivo para especificar qué ignorar por Git (datos grandes, resultados, etc.)
├── README.md          # <-- Este archivo con la descripción del proyecto
└── requirements.txt   # <-- Archivo con las dependencias necesarias
```


* **`data/`**: Contiene los archivos de datos necesarios para el análisis. (Nota: Si los datos no están incluidos en GitHub debido a su tamaño o naturaleza, este directorio puede estar vacío o contener archivos pequeños de ejemplo, y la sección "Datos" explicará cómo obtenerlos).
* **`src/`**: Directorio para el código fuente del proyecto. Aquí se encuentran los scripts de Python y los cuadernos de Jupyter, como `memroia_v2.ipynb`.
* **`.gitignore`**: Define qué archivos y directorios deben ser ignorados por Git (como datos grandes, archivos de resultados generados, entornos virtuales, credenciales, etc.) para no ser incluidos en el repositorio.
* **`README.md`**: El archivo que estás leyendo, proporcionando una visión general del proyecto, su configuración y cómo ejecutarlo.
* **`requirements.txt`**: Lista de las librerías de Python necesarias y sus versiones para replicar el entorno de ejecución.

---

# Clonar Repositorio de GitHub

Sigue estos pasos rápidos para obtener una copia local de un repositorio de GitHub:

1.  **Abre tu terminal.**
2.  **Navega** a la carpeta donde quieras guardar el proyecto:
    ```bash
    cd ruta/a/tu/carpeta
    ```
3.  En GitHub, ve al repositorio, haz clic en el botón "<> Code" y **copia la URL HTTPS**.
4.  En la terminal, usa `git clone` seguido de la URL copiada:
    ```bash
    git clone [URL_del_repositorio]
    ```

¡Listo! El proyecto se descargará en una nueva carpeta en tu ubicación actual.

## 🛠️ Requisitos

Para ejecutar este cuaderno, necesitarás tener instalado Python y las siguientes librerías. Las dependencias exactas se listan en `requirements.txt`.

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn (si se utiliza para algún tipo de modelo o procesamiento)
- Cualquier otra librería específica que se use en el cuaderno (revisar las importaciones en el notebook).

Puedes instalar las dependencias usando pip con el archivo `requirements.txt`:

```bash
pip install -r requirements.txt
```
-----

## 📂 Datos

Los datos utilizados en este análisis **están ubicados en el directorio `data/`** de este repositorio.

dataset principal ```text playlist_2010to2022 ```origen de kaggle https://www.kaggle.com/code/ryanlingo/spotify-hits-quick-analysis/notebook?select=playlist_2010to2022.csv 

-----

------
## 📧 Contacto

* [Joan Izquierdo Balaciart] - <joanizquierdo07@gmail.com>
* [Raúl Rodríguez Villalonga] - <rrv.2846@gmail.com>

```

This README provides a clear overview of the project, its objectives, how to run it, and what to expect. Remember to fill in the optional sections if you want to include that information.
```
