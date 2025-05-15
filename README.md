
# 🎵 Spotify Popular Music Trends Analysis (2000–2022)

## 📌 Introducción

Este proyecto explora **tendencias en la música popular** desde el año 2000 hasta 2022. Utilizando datos extraídos de listas de reproducción de Spotify, buscamos comprender cómo han evolucionado las características musicales, la popularidad por géneros y los atributos de audio a lo largo de más de dos décadas.

### 🔍 Objetivos del análisis:

- ¿Qué géneros han dominado distintas épocas?
- ¿Han cambiado los atributos de audio (como *danceability* o *energy*) con el tiempo?
- ¿Qué relación hay entre la popularidad de un artista y la de sus canciones?

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



## 🛠️ Requisitos

Para ejecutar este cuaderno, necesitarás tener instalado Python y las siguientes librerías:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn (si se utiliza para algún tipo de modelo o procesamiento)
- Cualquier otra librería específica que se use en el cuaderno (revisar las importaciones en el notebook).

Puedes instalar las dependencias usando pip:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn # Agrega las que falten
````

-----

## 🏃 Cómo ejecutar el análisis

1.  Clona este repositorio o descarga los archivos.
2.  Asegúrate de tener los requisitos instalados.
3.  Abre el cuaderno `memroia_v2.ipynb` usando Jupyter Notebook, JupyterLab o Google Colab.
4.  Ejecuta las celdas secuencialmente para reproducir el análisis.

-----

## 📂 Datos

El análisis se basa en datos de listas de reproducción de Spotify. (Nota: Si los datos no están incluidos en el repositorio, se debería añadir una sección explicando cómo obtenerlos o si se generan durante la ejecución).

-----

## ✨ Resultados

El cuaderno contiene visualizaciones y explicaciones detalladas de los hallazgos relacionados con los objetivos planteados, incluyendo la evolución de géneros, cambios en atributos de audio y la relación entre popularidad de artistas y canciones.

-----

## 🤝 Contribuciones

(Sección opcional: Si deseas permitir contribuciones, añade información aquí).

-----

## 📄 Licencia

(Sección opcional: Indica la licencia bajo la cual se distribuye el proyecto).

-----

## 📧 Contacto

(Sección opcional: Información de contacto del autor o mantenedor).

```

This README provides a clear overview of the project, its objectives, how to run it, and what to expect. Remember to fill in the optional sections if you want to include that information.
```
