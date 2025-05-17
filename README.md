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
## 🐋Docker
### 1. Requisitos Previos (Docker y Docker compose)

- Docker: [Instalar Docker Engine](https://docs.docker.com/engine/install/)
- Docker Compose: [Instalar Docker Compose](https://docs.docker.com/compose/install/)
  
### 🧩 2. Creación de Entorno Docker (Con Devbox)
Se adopta un nuevo archivo docker-compose.yml que incluye una imagen de Hadoop más reciente y un contenedor devbox basado en ubuntu:latest para las herramientas.

*📝 Archivo docker-compose.yml*
```text
version: '3.9'

services:
  hadoop:
    image: ghcr.io/apache/hadoop:3.3.6 # Nueva imagen de Hadoop
    container_name: hadoop
    ports:
      - "9870:9870" # WebHDFS
      - "9000:9000" # Default HDFS port
    networks:
      - my_network

  cassandra:
    image: cassandra:latest
    container_name: cassandra
    ports:
      - "9042:9042" # CQL port
    networks:
      - my_network

  nifi:
    image: apache/nifi:latest
    container_name: nifi
    ports:
      - "8080:8080" # NiFi UI
    environment:
      - NIFI_WEB_HTTP_PORT=8080
    networks:
      - my_network

  devbox: # Nuevo contenedor dedicado para herramientas
    image: ubuntu:latest # Una imagen base limpia y moderna
    container_name: devbox
    networks:
      - my_network
    stdin_open: true # Permite interactividad
    tty: true      # Asigna una TTY para una terminal interactiva

networks:
  my_network:
    driver: bridge
```
### 🧩 3. Verificación del Nuevo Entorno
Para ello tendremos que utlizar el siguiente comando;
```text
docker ps -a
````
###  🧩 4. Acceder y Usar Herramientas Cliente en el Contenedor devbox
El contenedor devbox, basado en ``ubuntu:latest``, se usará para instalar y ejecutar herramientas cliente.

#### 4.1  Entrar en el contenedor devbox   
    docker exec -it devbox bash

#### 4.2 Actualizar listas de paquetes e instalar netcat y pip para Python 3
    apt install -y python3-pip netcat
*(Nota:Con el comando ``dkpg-l | grep python3-pip`` y ``dkpg-l | grep python3-netcat``podremos ver si se ha instalado correctamente tanto la lista de paquetes pip *``(dkpg-l | grep python3-pip)``*, como el netcat *``(dkpg-l | grep python3-netcat)``*)*

#### 4.3 Instalar un entorno virtual (`venv`).
*       apt install -y python3-venv

#### 4.4 Crear y Activar el Entorno Virtual
* Crear el entorno virtual llamado 'myvenv'

        python3 -m venv myvenv
* Activar el entorno virtual

        source myvenv/bin/activate
#### 4.5 Instalar `cqlsh` dentro del entorno virtual activo
*       pip install cqlsh

*(Nota: Si encontraras errores de compilación aquí, necesitarías instalar antes `apt install -y build-essential python3-dev` fuera del `venv`, luego reactivar el `venv` e intentar `pip install cqlsh` de nuevo. En `ubuntu:latest`, las dependencias comunes de compilación para `cqlsh` suelen estar cubiertas o no son necesarias en el `venv`.)*

#### 4.6 Conectar a Cassandra desde el entorno virtual activo en devbox
*       cqlsh cassandra 9042

*(Nota: Si la conexión es exitosa, verás el prompt `cqlsh>`. El nombre del host `cassandra` es reconocido porque ambos contenedores están en la misma red de Docker (`my_network`).*

------
## 📧 Contacto

* [Joan Izquierdo Balaciart] - <joanizquierdo07@gmail.com>
* [Raúl Rodríguez Villalonga] - <rrv.2846@gmail.com>

```

This README provides a clear overview of the project, its objectives, how to run it, and what to expect. Remember to fill in the optional sections if you want to include that information.
```
