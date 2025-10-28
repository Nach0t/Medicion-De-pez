## DESCRIPCIÓN GENERAL:
Este proyecto implementa un sistema de **detección y medición automática de peces** utilizando la arquitectura **YOLOv8**.  
El flujo completo incluye:

1. Entrenamiento con validación cruzada (K-Fold)
2. Validación externa con conjunto independiente
3. Medición física de la longitud real (en centímetros)

---

## 1. REQUISITOS PREVIOS

### Hardware recomendado:
- GPU **NVIDIA** con soporte **CUDA** 
- **16 GB RAM** (mínimo 8 GB)
- Espacio libre en disco: ~15 GB

### Software:
- **Python 3.10+**
- **Git**
- **Windows 10/11** o **Linux**
- Drivers CUDA actualizados

---

## 2. CREAR Y ACTIVAR EL ENTORNO VIRTUAL

```bash
python gitclone/https://github.com/Nach0t/Medicion-De-pez.git
```

### En Windows (CMD o PowerShell):

```bash
python -m venv .venv
.venv\Scriptsctivate
```

### En Linux:
```bash
python3 -m venv .venv
source .venv/bin/activate
```

Verificar que el entorno está activo:
```bash
python --version
```

Debe mostrar una versión ≥ 3.10.

---

## 3. INSTALAR DEPENDENCIAS

Primero, actualizar `pip`:
```bash
pip install --upgrade pip
```

Luego instalar dependencias:
```bash
pip install -r requirements.txt
```

Si no tienes el archivo `requirements.txt`, instala manualmente:

```bash
pip install ultralytics opencv-python torch torchvision matplotlib jupyterlab
```

---

## 4. EJECUCIÓN DEL PROYECTO

1️⃣ Activar el entorno virtual (si aún no está activo).  
2️⃣ Iniciar Jupyter Notebook:
```bash
jupyter notebook
```

3️⃣ Se abrirá una pestaña en el navegador. Ahí selecciona el archivo:
```
yolo_fish_system_notebook.ipynb
```

4️⃣ Ejecuta las celdas en orden:

| Bloque | Descripción |
|--------|-------------|
| 1️⃣ | Configuración y dependencias |
| 2️⃣ | Entrenamiento K-Fold |
| 3️⃣ | Validación externa |
| 4️⃣ | Medición física de los peces |

---

## 5. RESULTADOS GENERADOS

| Carpeta | Descripción |
|---------|-------------|
| `runs_kfold/` | Resultados de los 5 folds de entrenamiento |
| `val_final/` | Detecciones finales del mejor modelo |
| `val_medidos/` | Imágenes con longitudes en centímetros |

**Conversión utilizada**:
```
longitud_cm = longitud_px * (50 / 1456)
```

---

## 6. REINICIO LIMPIO DEL PROYECTO

Si deseas repetir todo el proceso desde cero:
```bash
rmdir /s /q runs_kfold val_final val_medidos
```

(En Linux/WSL usa: `rm -rf runs_kfold val_final val_medidos`)

Luego vuelve a ejecutar el notebook completo.

---

## 7. SOLUCIÓN DE ERRORES COMUNES

| Error | Causa / Solución |
|-------|------------------|
| `CUDA not available` | Verifica drivers NVIDIA y PyTorch con soporte CUDA (`python -c "import torch; print(torch.cuda.is_available())"`) |
| `No module named ultralytics` | Ejecuta `pip install ultralytics` dentro del entorno virtual |
| `best.pt not found` | Asegúrate de ejecutar correctamente el bloque de entrenamiento K-Fold antes de la validación externa |

---

## 8. CIERRE Y DESACTIVACIÓN DEL ENTORNO

Para salir del entorno virtual:
```bash
deactivate
```

---