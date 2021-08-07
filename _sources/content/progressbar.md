# Tkinter Progressbar
Permite agregar una barra de progreso, puede conectarse con el progreso de una operación.

## Ejemplo

```python
# -*- coding: utf-8 -*-
"""
Ejemplo de ventana básico con progressbar

"""
#Importamos las librerías necesarias
import tkinter as tk
from tkinter import ttk

def aumentar(): #Aumenta 20% de la barra de progreso
    progressbar.step(19.99999999)

ventana = tk.Tk() #Ventana principal

progressbar = ttk.Progressbar(orient=tk.HORIZONTAL) #Barra de progreso
progressbar.pack()
#Cuando llega al 100% se reinicia
    
boton = tk.Button(text = "Aumentar", command = aumentar) #Botón
boton.pack()

ventana.mainloop()
```
El resultado es el siguiente:

![ventanaprogressbar](https://user-images.githubusercontent.com/58320351/128614498-838331dc-f9c8-4502-9c23-b7481f1be48b.png)

El botón (ver [Tkinter Button](https://juan-suarezp.github.io/Tk/content/button.html)) está conectado con la función `aumentar`, la cual aumenta el 20% de la barra de progreso cada vez que es llamada. Esta es una manera simple de ver el funcionamiento del widget progressbar.

![funcionprogressbar](https://user-images.githubusercontent.com/58320351/128614505-6016a017-dc35-442c-aafd-cf2601d157b9.png)

Primero se define la `tk.Tk`, luego se define la progressbar indicando su orientación. Al final se define la función y el botón.
