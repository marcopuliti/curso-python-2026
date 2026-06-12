# Guía de instalación del entorno

Hay dos caminos. Si nunca instalaste software de desarrollo, **la opción A (Google Colab) te permite empezar sin instalar nada**. Para el resto del curso recomendamos completar también la opción B, que es la que usaremos en el laboratorio.

## Opción A — Google Colab (sin instalación)

1. Entrá a https://colab.research.google.com con una cuenta de Google.
2. `Archivo → Subir notebook` y elegí el archivo `.ipynb` de la clase.
3. Ejecutá las celdas con `Shift + Enter`.

Ventajas: funciona desde cualquier navegador, no requiere instalación.
Limitación: necesita conexión a internet y los archivos viven en la nube.

## Opción B — Anaconda + VS Code (recomendada para todo el curso)

### 1. Instalar Anaconda

1. Descargá el instalador desde https://www.anaconda.com/download (elegí tu sistema operativo).
2. Instalá con las opciones por defecto. En Windows, **no** hace falta marcar "Add to PATH".
3. Verificá: abrí *Anaconda Prompt* (Windows) o una terminal (Mac/Linux) y ejecutá:

   ```
   python --version
   conda --version
   ```

   Deberías ver `Python 3.x` y una versión de conda.

Anaconda ya incluye Jupyter, NumPy, Pandas y Matplotlib — todo lo que usaremos en los módulos 1 a 4.

### 2. Instalar Visual Studio Code

1. Descargá desde https://code.visualstudio.com/ e instalá con las opciones por defecto.
2. Abrí VS Code y, en la pestaña de extensiones (`Ctrl+Shift+X`), instalá:
   - **Python** (de Microsoft)
   - **Jupyter** (de Microsoft)
3. Abrí un notebook `.ipynb`: VS Code te va a pedir elegir un *kernel* → seleccioná el entorno de Anaconda (`base`).

### 3. Probar que todo funciona

Creá un archivo `hola.py` con este contenido y ejecutalo (botón ▶ en VS Code):

```python
print("¡Hola, mundo! Mi entorno funciona.")
```

Si ves el mensaje en la terminal, estás listo/a para la primera clase. 🎉

## Opción C — Jupyter Notebook clásico

Si preferís la interfaz clásica de Jupyter: abrí *Anaconda Navigator* y lanzá **Jupyter Notebook**, o ejecutá `jupyter notebook` en Anaconda Prompt. Se abre en el navegador y desde ahí navegás hasta los archivos `.ipynb` del curso.

## Problemas frecuentes

| Problema | Solución |
|---|---|
| `python` no se reconoce como comando (Windows) | Usá *Anaconda Prompt* en lugar del símbolo del sistema común. |
| VS Code no encuentra el kernel de Python | `Ctrl+Shift+P` → "Python: Select Interpreter" → elegir el de Anaconda. |
| El notebook no ejecuta celdas | Verificá que arriba a la derecha esté seleccionado el kernel de Anaconda. |

Si algo no funciona, traé tu computadora a la primera clase: la primera hora está reservada para dejar el entorno funcionando en todas las máquinas.
