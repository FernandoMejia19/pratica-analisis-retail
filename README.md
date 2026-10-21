# 🛒 Predicción de Demanda en Retail con Deep Learning (LSTM)
**Práctica de Laboratorio N° 2 — Aprendizaje Automático**  
**Universidad Politécnica Salesiana (UPS Ecuador)**  
**Docente:** Ing. Remigio Hurtado  
**Integrantes:** Erick Salinas, Fernando Mejia, David Villa, Patricio Lucero  

---

## ¿De qué trata este proyecto?
Este proyecto implementa una solución de **Machine Learning / Deep Learning** para predecir la demanda comercial de 10 productos clave a lo largo del tiempo, utilizando datos del benchmark industrial **FreshRetailNet-50K** (publicado por *Dingdong Limited* en Hugging Face).

El objetivo es resolver el problema de la **Demanda Censurada** (cuando un producto se agota en percha, las ventas caen a 0 aunque la gente quiera comprar) usando una **Red Neuronal Recurrente (LSTM)** en TensorFlow/Keras que aprende los patrones de fin de semana y variables exógenas como descuentos y clima.

---

## Archivos

*  **`practica_demanda.ipynb`**: Cuaderno Jupyter principal. Contiene todo el código documentado celda por celda (EDA, Feature Engineering, entrenamiento de la red LSTM, cálculo de RMSE/MAE/R² y funciones de predicción para producción).
*  **`data/`**: Contiene los CSVs generados:
  * `inventory.csv`: Catálogo maestro y stock actual de los 10 productos.
  * `sales_history.csv`: 60 días continuos de historial de ventas (600 filas).
*  **`analisis/`**: Contiene los 3 gráficos en alta resolución (`grafico_top10.png`, `grafico_real_vs_pred.png`, `grafico_proyeccion.png`).
*  **`requirements.txt`**: Lista de librerías necesarias con sus versiones probadas.

---

##  Guía Rápida: Cómo ejecutar el proyecto en tu computadora

### Requisito previo
Tener instalado **Python** (versión 3.10, 3.11, 3.12 o 3.13).  
Puedes verificarlo abriendo una terminal y escribiendo:
```bash
python --version
```

---

### Paso a Paso (Para Windows con PowerShell)

#### 1. Abre la terminal en esta carpeta
Haz clic derecho en un espacio vacío dentro de esta carpeta y selecciona **"Abrir en Terminal"** (o abre PowerShell y usa `cd` para entrar aquí).

#### 2. Crea el entorno virtual
Escribe el siguiente comando y presiona Enter:
```powershell
python -m venv venv
```
*(Esto creará una carpetita llamada `venv` donde se guardarán las librerías sin alterar tu Python global).*

#### 3. Activa el entorno virtual
En Windows PowerShell:
```powershell
.\venv\Scripts\Activate.ps1
```
> ⚠️ **¿Te sale un error rojo que dice "la ejecución de scripts está deshabilitada en este sistema"?**  
> No te preocupes, es una protección por defecto de Windows. Se soluciona ejecutando este comando una sola vez en esa ventana:
> ```powershell
> Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
> ```
> Y luego vuelve a ejecutar: `.\venv\Scripts\Activate.ps1`.  
> Sabrás que está activado porque verás `(venv)` al inicio de tu línea de comandos.

*(Si usas CMD clásico en lugar de PowerShell, el comando de activación es: `venv\Scripts\activate.bat`)*  
*(Si alguno usa Mac o Linux, el comando es: `source venv/bin/activate`)*

#### 4. Instala las dependencias
Con el entorno `(venv)` activo, ejecuta:
```bash
pip install -r requirements.txt
```
Esto descargará automáticamente `pandas`, `numpy`, `scikit-learn`, `tensorflow`, `keras`, `datasets`, `matplotlib`, `seaborn`, `plotly`, `jupyter` y `python-pptx`.

#### 5. Ejecutar y ver el Cuaderno Jupyter
Tienes dos opciones:
* **Opción A (Recomendada con VS Code):** Abre la carpeta en Visual Studio Code, abre el archivo `practica_demanda.ipynb` y arriba a la derecha en "Select Kernel" elige tu entorno `venv (Python 3.x)`.
* **Opción B (Navegador web con Jupyter):** Escribe en tu terminal:
  ```bash
  jupyter notebook
  ```
  Se abrirá tu navegador web; solo haz clic en `practica_demanda.ipynb` y podrás ejecutar celda por celda o presionar **"Run All"**.

---

##  Comandos rapidos (Copia y Pega todo en PowerShell de una vez)

Si quieres hacer todo el proceso en 1 solo paso en Windows PowerShell:
```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass; python -m venv venv; .\venv\Scripts\Activate.ps1; python -m pip install --upgrade pip; pip install -r requirements.txt; jupyter notebook practica_demanda.ipynb
```

---

