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

### 3. Instalar los paquetes del curso

En una terminal (podés usar la integrada de VS Code: menú `Terminal → New Terminal`), ejecutá:

```
pip install jupyter numpy pandas matplotlib seaborn
```

Eso instala el soporte de notebooks y las bibliotecas que usaremos en los módulos 1 a 4.

### 4. Probar que todo funciona

1. **Script:** creá un archivo `hola.py` con este contenido y ejecutalo con el botón ▶ de VS Code:

   ```python
   print("¡Hola, mundo! Mi entorno funciona.")
   ```

2. **Notebook:** abrí un archivo `.ipynb` del curso. VS Code te va a pedir elegir un *kernel*: arriba a la derecha, `Select Kernel → Python Environments` y elegí el Python que acabás de instalar. Ejecutá una celda con `Shift + Enter`.

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
| `pip` no se reconoce | Probá `python -m pip install ...` en lugar de `pip install ...`. |
| VS Code no encuentra el kernel de Python | `Ctrl+Shift+P` → "Python: Select Interpreter" → elegí el Python instalado. Si no aparece, cerrá y reabrí VS Code. |
| El notebook no ejecuta celdas | Verificá que arriba a la derecha esté seleccionado el kernel de Python (no "Select Kernel"). |
| `ModuleNotFoundError: No module named 'numpy'` | Faltan los paquetes del paso 3: `pip install jupyter numpy pandas matplotlib seaborn`. |

Si algo no funciona, traé tu computadora a la primera clase: la primera hora está reservada para dejar el entorno funcionando en todas las máquinas.
