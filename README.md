# Sistema de Detección y Medición de Peces — YOLOv8

Este proyecto implementa un sistema de **detección y medición automática de peces** utilizando la arquitectura **YOLOv8**.

---

## Pasos rápidos para ejecutar

### 0. Descargar el repositorio
```bash
git clone https://github.com/Nach0t/Medicion-De-pez.git
cd Medicion-De-pez
```


### 1. Crear y activar el entorno virtual

**Windows (CMD o PowerShell):**
```bash
python -m venv .venv
.venv\Scripts\activate
```

**Linux / WSL:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

---

### 2. Instalar dependencias
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

---

### 3. Abrir el proyecto en Jupyter Notebook
```bash
jupyter lab
```
Luego abre el archivo:
```
yolo_fish_full_pipeline.ipynb
```

---

### 4. Ejecutar todas las celdas en orden (▶ Run All)

El sistema:
- Entrena con validación cruzada (K-Fold)
- Realiza validación externa
- Mide la longitud real de los peces

---

## Resultados

| Carpeta | Contenido |
|----------|------------|
| `runs_kfold/` | Modelos entrenados (1 por fold) |
| `val_final/` | Detecciones del mejor modelo |
| `val_medidos/` | Peces medidos en centímetros |


---

## Reinicio limpio (opcional)
```bash
rm -rf runs_kfold val_final val_medidos
```
