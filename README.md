# Global Food & Nutrition Database

Análisis detallado del conjunto de datos [Global Food & Nutrition Database 2026 – Health Scores & Allergens](https://drive.google.com/file/u/1/d/1IyK0jgDmyde9jdAT6hJFtjSWIYT3yaVz/view?usp=drive_link).

Todo el análisis (limpieza, análisis exploratorio y validación de hipótesis) está en el notebook `entrega.ipynb`.

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `entrega.ipynb` | Notebook principal con todo el análisis |
| `requirements.txt` | Dependencias de Python con versiones fijas |
| `global_food.csv` | Dataset  |

## Requisitos previos

- **Python 3.12** (es la versión con la que se probó; versiones anteriores a 3.11 no son compatibles con las librerías fijadas).
- **pip** (viene incluido con Python).
- **Git**, para clonar el repositorio.


Para verificar la versión de Python:

```bash
python3 --version
```

## Instalación

### 1. Clonar el repositorio

```bash
git clone https://github.com/SantiWilli/TPEspecialFundamentos.git
cd TPEspecialFundamentos
```

### 2. Crear y activar un entorno virtual

Se recomienda usar un entorno virtual para no mezclar estas librerías con las del sistema.

**Linux / macOS:**

```bash
python3 -m venv venv
source venv/bin/activate
```

**Windows (PowerShell):**

```powershell
python -m venv venv
venv\Scripts\Activate.ps1
```

Con el entorno activado, la terminal muestra `(venv)` al principio de la línea.

### 3. Instalar las dependencias

Las dependencias se instalan automáticamente al ejecutar la **primera celda** del notebook (`%pip install -r requirements.txt`), por lo que alcanza con ejecutar el notebook completo (**Run All**).

Para poder abrir el notebook, el entorno solo necesita el kernel de Jupyter:
- **VS Code:** al seleccionar el entorno `venv` como kernel, el editor ofrece instalar `ipykernel`; aceptar.
- **Jupyter en el navegador:** ejecutar `pip install notebook` antes de abrirlo.

> Si se ejecutaron celdas antes que la primera, reiniciar el kernel (**Restart**) después de instalar las dependencias.


## Dataset

El notebook busca el archivo `global_food.csv` en la **misma carpeta** que `entrega.ipynb`:

- Si el archivo existe, lo usa directamente.
- Si no existe, lo descarga automáticamente desde Google Drive.

Si la descarga automática fallara, se puede bajar a mano desde el [link del dataset](https://drive.google.com/file/u/1/d/1IyK0jgDmyde9jdAT6hJFtjSWIYT3yaVz/view?usp=drive_link) y guardarlo como `global_food.csv` en la raíz del repositorio.

## Ejecución

Con el entorno virtual activado, hay dos opciones.

### Opción A: Jupyter en el navegador

```bash
jupyter notebook entrega.ipynb
```

Se abre el notebook en el navegador. Para ejecutarlo completo: menú **Run → Run All Cells**.

### Opción B: Visual Studio Code

1. Abrir la carpeta del repositorio en VS Code (con la extensión **Jupyter** instalada).
2. Abrir `entrega.ipynb`.
3. Arriba a la derecha, en **Select Kernel**, elegir el intérprete del entorno virtual creado (`venv`).
4. Ejecutar todo con **Run All**.

> Las celdas deben ejecutarse **en orden**, de arriba hacia abajo: cada sección usa el dataset limpio que generan las anteriores.

## Resultados generados

Además de las tablas y gráficos que se muestran dentro del notebook, la ejecución genera el archivo:

- `SWEETVIZ_REPORT.html`: reporte exploratorio automático de Sweetviz, que se puede abrir con cualquier navegador.

## Problemas frecuentes

| Problema | Solución |
|---|---|
| `ModuleNotFoundError: No module named '...'` | El notebook se está ejecutando con un kernel distinto al del entorno virtual. Seleccionar el kernel de `venv` (ver Opción B) o verificar que el entorno esté activado antes de correr `jupyter notebook`. |
| `FileNotFoundError: global_food.csv` | Descargar el dataset a mano (ver sección [Dataset](#dataset)) y ubicarlo junto al notebook. |
| Error al instalar las dependencias | Verificar que la versión de Python sea 3.12 y actualizar pip con `pip install --upgrade pip`. |
| La celda de Sweetviz no abre el navegador | Es normal: el reporte se guarda igual como `SWEETVIZ_REPORT.html` en la carpeta del proyecto. |
