# Tkinter Notebook
Permite gestionar una colección de ventanas y mostrar una sola a la vez. Cada una de las ventanas secundarias está asociada a una pestaña que se puede seleccionar para mostrar la ventana respectiva.

## Ejemplo

```python
# -*- coding: utf-8 -*-
"""
Ejemplo de ventana básico con notebook

"""
import tkinter as tk
from tkinter import ttk

ventana = tk.Tk()
ventana.title("Panel de pestañas")

#Crear el panel de pestañas.
notebook = ttk.Notebook(ventana)

#Crear el contenido de cada una de las pestañas.
label1 = ttk.Label(notebook, text="Texto pestaña 1")
label2 = ttk.Label(notebook, text="Texto pestaña 2")

#Añadirlas al panel con su respectivo texto.
notebook.add(label1, text="Pestaña 1", padding=20)
notebook.add(label2, text="Pestaña 2", padding=20)

notebook.pack(padx=10, pady=10)

ventana.mainloop()
```
El resultado es el siguiente:

![ventananotebook](https://user-images.githubusercontent.com/58320351/128614475-1aff7d71-d5b3-40cf-9122-2ce69250ab8c.png)

Al seleccionar la otra pestaña se muestra la otra ventana como sigue:

![cambionotebook](https://user-images.githubusercontent.com/58320351/128614481-601d1f8e-a062-40a7-b861-dd1cef4cc638.png)

Después de definir la `tk.Tk`, se define el notebook indicando el widget que lo va a contener. Luego, se definen los label (ver [Tkinter Label](https://juan-suarezp.github.io/Tk/content/label.html)) indicando que estarán en el notebook. Finalmente, se agregan las pestañas al notebook con `notebook.add` indicando el widget que va a estar en la pestaña; en este caso, un label para cada pestaña.

Es importante resaltar que cada pestaña de un notebook solo puede contener un widget, es decir, si se quiere crear una ventana con notebook y varios widgets en las pestañas, es necesario organizar los widgets de cada pestaña en un frame (ver [Tkinter Frame](https://juan-suarezp.github.io/Tk/content/frame.html)). Finalmente, este frame sería el widget que se indica para estar en la pestaña en `notebook.add`.
