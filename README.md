# Proyecto grupo 4 · MCDI502 Gestión de Datos y Tecnologías Big Data

Trabajos del curso MCDI502 (Magíster en Ciencias de Datos e Inteligencia Artificial, UNAB) con Apache Spark.

## Integrantes
- Felipe Díaz Toro ([@fdiaztoro](https://github.com/fdiaztoro))
- Pablo Ríos Passteni ([@pablo9876](https://github.com/pablo9876))
- Guillermo Subiabre Chacón ([@Gsubiabre](https://github.com/Gsubiabre))
- Ninoska Yévenes Hernández ([@nyevenes](https://github.com/nyevenes))

## Evaluaciones
| Evaluación | Pondera | Vence |
| --- | --- | --- |
| Sumativa 2 · Taller 1 (RDDs, DataFrames, Spark SQL) | 40% | Dom 8 nov, 23:59 |
| Sumativa 3 · Taller 2 | 20% | Dom 15 nov, 23:59 |
| Sumativa 4 · Taller 3 | 20% | Dom 15 nov, 23:59 |

## Estructura
- `notebooks/`: notebooks de Jupyter (un archivo por taller). El Taller 2 se trabaja en VS Code.
- `data/raw/`: datasets descargados de Canvas. No se suben a GitHub (ver `.gitignore`).
- `docs/`: apuntes, guía de estudio y rúbricas.

## Datos del Taller 1

Copiar los seis archivos entregados por el docente en `data/raw/taller1_sumativa2/`:

| Archivo | Lectura |
| --- | --- |
| `deportista.csv` | CSV sin encabezado, separado por coma |
| `deportista2.csv` | CSV sin encabezado, separado por coma |
| `equipo.csv` | CSV con encabezado, separado por coma |
| `evento.csv` | CSV con encabezado, separado por coma; el notebook repara las filas con comillas adicionales |
| `resultados.csv` | CSV con encabezado, separado por punto y coma (`;`) |
| `juegos.json` | JSON multilínea |

El notebook usa `ruta = '../data/raw/taller1_sumativa2/'`: iniciar el kernel desde `notebooks/` o ajustar esa ruta al directorio de trabajo. En Colab, subir los archivos o montar Drive y adaptar la ruta.

En `juegos.json`, el campo original `temporada` contiene el año y `ciudad` contiene Verano/Invierno. La carga del notebook los renombra a `anio_edicion` y `temporada`.

El conjunto recibido el 7 de noviembre de 2026 incluye `deportista.csv`, que faltaba en la copia inicial. Los archivos originales permanecen excluidos de Git; cada integrante debe disponer de su copia. El inventario de tamaños y hashes está en `docs/datasets_taller1.md`. Disponer de todos los archivos no acredita una ejecución completa en Spark.

## Reglas de entrega del Taller 1
- Notebook: `mcdi502_s2_grupo4.ipynb`; video de 7 a 10 minutos: `mcdi502_s2_grupo4_video.mp4`.
- Sin tildes, ñ ni símbolos; un solo guion; máximo 20 caracteres sin extensión.
- Un integrante comprime ambos archivos en un único `.zip` y lo sube al buzón de Canvas.

## Taller 2 (Sumativa 3)

Se desarrolla en VS Code, con este repositorio y el entorno de conda del grupo (`grupo4_mcdi502`), según lo confirmado con el docente. Vence el domingo 15 de noviembre, 23:59.

- Notebook: `notebooks/mcdi502_s3_grupo4.ipynb`.
- Datos: cuatro fuentes en vivo (OpenMeteo, AQICN, MongoDB y MySQL), cada una con 100 registros.
- Secretos: crear un archivo `.env` en la raíz del repo (está en `.gitignore`) a partir de `.env.example`, con el token de AQICN y la URI de MongoDB que entrega el docente. No se suben a GitHub.
- macOS y Windows: el notebook detecta la ruta de Java del entorno de conda. En Windows no hace falta instalar Hadoop ni `winutils.exe`: la celda 1.3 descarga el conector de MongoDB a la carpeta `jars` de la instalación de Spark del entorno, que Spark carga al iniciar. Si al ejecutar la celda 1.3 ya había una sesión de Spark abierta, reiniciar el kernel.
- Trabajo en equipo: rama propia, PR a `develop` y aprobación de otra persona, como en el Taller 1.
- Entrega: `mcdi502_s3_grupo4.ipynb` y `mcdi502_s3_grupo4_video.mp4` (7 a 10 minutos) en un único `.zip`.
