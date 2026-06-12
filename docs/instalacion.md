# Guía de instalación del entorno

El entorno oficial del curso es **Python + Visual Studio Code** (opción A), que es el que usaremos en el laboratorio. Si todavía no instalaste nada, la opción B (Google Colab) te permite seguir las clases desde el navegador sin instalar nada.

## Opción A — Python + VS Code (entorno oficial del curso)

### 1. Instalar Python

1. Descargá el instalador desde https://www.python.org/downloads/ (botón amarillo, última versión estable).
2. **Importante en Windows:** en la primera pantalla del instalador, marcá la casilla **"Add python.exe to PATH"** antes de hacer clic en *Install Now*.
3. Verificá: abrí una terminal (en Windows: `Win + R`, escribí `cmd`, Enter) y ejecutá:

   ```
   python --version
   pip --version
   ```

   Deberías ver `Python 3.x` y una versión de pip.

> **Nota Windows:** si `python` abre la Microsoft Store en lugar de mostrar la versión, falta el paso del PATH. Reinstalá marcando la casilla, o desactivá los alias en `Configuración → Aplicaciones → Alias de ejecución de aplicaciones`.

### 2. Instalar Visual Studio Code

1. Descargá desde https://code.visualstudio.com/ e instalá con las opciones por defecto.
2. Abrí VS Code y, en la pestaña de extensiones (`Ctrl+Shift+X`), instalá:
   - **Python** (de Microsoft)
   - **Jupyter** (de Microsoft)

### 3. Crear el entorno virtual del curso

**No vamos a instalar paquetes "en global":** todo el curso se trabaja dentro de un **entorno virtual** (*venv*), una carpeta autocontenida con su propio Python y sus propios paquetes. Así el curso no interfiere con nada más de tu máquina, y si algo se rompe, se borra la carpeta `.venv` y se crea de nuevo. Es la práctica profesional estándar y la vas a repetir en cada proyecto propio.

1. Creá una carpeta para el curso (por ejemplo `curso-python`) y abrila en VS Code: `Archivo → Abrir carpeta...`.
2. Abrí la terminal integrada (`Terminal → New Terminal`) y creá el entorno:

   ```
   python -m venv .venv
   ```

   Esto crea la carpeta `.venv` dentro del proyecto (puede tardar unos segundos).
3. Activá el entorno:

   - **Windows (PowerShell, la terminal por defecto de VS Code):** `.venv\Scripts\Activate.ps1`
   - **Windows (cmd):** `.venv\Scripts\activate.bat`
   - **Mac/Linux:** `source .venv/bin/activate`

   Sabés que está activo porque el prompt de la terminal pasa a mostrar `(.venv)` adelante.

   > Si PowerShell se queja con *"running scripts is disabled"*, ejecutá una sola vez `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`, cerrá la terminal, abrila de nuevo y reintentá.
4. Con el entorno **activado** (mirá el `(.venv)` en el prompt), instalá los paquetes del curso:

   ```
   pip install jupyter numpy pandas matplotlib seaborn
   ```

   Estos paquetes quedan dentro de `.venv`, no en tu sistema.

> **De ahora en más:** cada vez que abras una terminal para trabajar en el curso, activá primero el entorno (paso 3). VS Code suele activarlo solo cuando detecta `.venv` en la carpeta abierta, pero verificá que el prompt diga `(.venv)`.

### 4. Probar que todo funciona

1. **Script:** creá un archivo `hola.py` con este contenido y ejecutalo con el botón ▶ de VS Code:

   ```python
   print("¡Hola, mundo! Mi entorno funciona.")
   ```

2. **Notebook:** abrí un archivo `.ipynb` del curso. VS Code te va a pedir elegir un *kernel*: arriba a la derecha, `Select Kernel → Python Environments` y elegí el que dice **`.venv`** (no el Python global). Ejecutá una celda con `Shift + Enter`.

Si ambas cosas funcionan, estás listo/a para la primera clase. 🎉

## Opción B — Google Colab (sin instalación)

1. Entrá a https://colab.research.google.com con una cuenta de Google.
2. `Archivo → Subir notebook` y elegí el archivo `.ipynb` de la clase.
3. Ejecutá las celdas con `Shift + Enter`.

Ventajas: funciona desde cualquier navegador, sin instalar nada, y ya trae NumPy, Pandas y Matplotlib.
Limitaciones: necesita conexión a internet, los archivos viven en la nube, y no sirve para la parte de scripts `.py` ni para Git (módulo 5). Usalo como plan B, no como entorno principal.

## Problemas frecuentes

| Problema | Solución |
|---|---|
| `python` no se reconoce o abre la Microsoft Store (Windows) | Reinstalá Python marcando **"Add python.exe to PATH"**, o desactivá los alias en `Configuración → Aplicaciones → Alias de ejecución de aplicaciones`. |
| *"running scripts is disabled"* al activar el venv (PowerShell) | `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` una sola vez, y abrí una terminal nueva. |
| `pip` no se reconoce | Activá primero el entorno (paso 3). Si persiste, probá `python -m pip install ...`. |
| VS Code no encuentra el kernel `.venv` | `Ctrl+Shift+P` → "Python: Select Interpreter" → elegí el de `.venv`. Si no aparece, cerrá y reabrí VS Code con la carpeta del curso abierta. |
| El notebook no ejecuta celdas | Verificá que arriba a la derecha esté seleccionado el kernel `.venv` (no "Select Kernel"). |
| `ModuleNotFoundError: No module named 'numpy'` | Instalaste los paquetes fuera del entorno o elegiste el kernel equivocado: activá `.venv` y repetí el paso 4, o cambiá el kernel del notebook a `.venv`. |

Si algo no funciona, traé tu computadora a la primera clase: la primera hora está reservada para dejar el entorno funcionando en todas las máquinas.
