# Tkinter Colorchooser
Crea una ventana que permite elegir un color y retorna su código en RGB y hexadecimal.

## Ejemplo

```python
# -*- coding: utf-8 -*-
"""
Ejemplo de ventana básico con colorchooser

"""
import tkinter as tk
from tkinter import colorchooser ###

class Example(tk.Frame): #Ventana principal
    def __init__(self,main):
        super().__init__(main)
        self.initUI()


    def initUI(self):
        self.master.title("Color chooser") #Título
        self.pack(fill=tk.BOTH, expand=1)

        #Botón
        self.btn = tk.Button(self, text="Choose Color", command=self.onChoose)
        self.btn.place(x=30, y=30)

        #Frame donde se muestra el color seleccionado
        self.frame = tk.Frame(self, border=1, relief=tk.SUNKEN, width=100,
                              height=100)
        self.frame.place(x=160, y=30)


    def onChoose(self):
        #Abre la ventana para seleccionar color y lo muestra en el frame
        (rgb, hx) = colorchooser.askcolor()
        self.frame.config(bg=hx)


def main():
    root = tk.Tk()
    root.geometry("300x150+300+300")
    ex = Example(root)
    ex.mainloop()


if __name__ == '__main__':
    main()
```
El resultado es el siguiente:

![ventanacolorchooser](https://user-images.githubusercontent.com/58320351/128614244-86fcde5c-8e88-448d-ad1e-cb579d217c91.png)
 
En este ejemplo se crea una clase para la interfaz, en la cual se define un botón (ver [Tkinter Button](https://juan-suarezp.github.io/Tk/content/button.html)) que está conectado al método `onChoose` y un frame (ver [Tkinter Frame](https://juan-suarezp.github.io/Tk/content/frame.html)) que va a mostrar el color elegido, así:

![funcioncolorchooser](https://user-images.githubusercontent.com/58320351/128614250-d55edfb5-7096-4d16-b183-5040da5f7b40.png)

El método `onChoose` abre una ventana predeterminada de Tkinter que permite seleccionar un color. Esta ventana se abre con `tkinter.colorchooser.askcolor` y retorna el código del color en RGB y en hexadecimal. Luego con el código en hexadecimal configura el frame para mostrar el color seleccionado.
