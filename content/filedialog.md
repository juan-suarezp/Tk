# Tkinter Filedialog
Crea una ventana que permite seleccionar un archivo y retornar la ruta del archivo seleccionado.

## Ejemplo

```python
# -*- coding: utf-8 -*-
"""
Ejemplo básico de ventana con filedialog

"""
import tkinter as tk
# from tkinter import filedialog ###

class Example(tk.Frame): #Ventana principal
    def __init__(self,main):
        super().__init__(main)
        self.initUI()


    def initUI(self):
        self.master.title("File dialog") #Título
        self.pack(fill=tk.BOTH, expand=1)

        menubar = tk.Menu(self.master) #Barra menú
        self.master.config(menu=menubar)

        fileMenu = tk.Menu(menubar, tearoff=0) #Menú file
        fileMenu.add_command(label="Open", command=self.Abrir)
        menubar.add_cascade(label="File", menu=fileMenu) #Pestaña en barra menú
        
        #Donde se muestra el archivo seleccionado
        self.txt = tk.Text(self.master)
        self.txt.pack(fill=tk.BOTH, expand=1)


    def Abrir(self):
        #Abre el dialogo para seleccionar archivo y lo muestra en el widget
        #Tipos de archivos
        ftypes = [('Python files', '*.py'), ('All files', '*')]
        #Retorna la ruta del archivo seleccionado
        ruta = tk.filedialog.askopenfilename(filetypes = ftypes)
        if ruta != '':
            self.txt.insert(tk.END, "Archivo: "+ruta+"\n\n\n") #Muestra ruta
            text = self.Leer(ruta)
            self.txt.insert(tk.END, text) #Muestra texto del archivo


    def Leer(self, filename):
        #Lee el archivo y retorna el texto que contiene
        with open(filename, "r") as f:
            text = f.read()

        return text


def main():
    root = tk.Tk()
    root.geometry("400x400")
    ex = Example(root)
    ex.mainloop()


if __name__ == '__main__':
    main()
```
El resultado es el siguiente:

![ventanafiledialog](https://user-images.githubusercontent.com/58320351/128614311-8ced5707-f186-4bfd-9172-f8e84ea15caf.png)

En este ejemplo se crea una clase para la interfaz, en la cual se define un menú (ver [Tkinter Menu](https://juan-suarezp.github.io/Tk/content/menu.html)) con una sola opción que está conectada al método `Abrir` y un text (ver [Tkinter Text](https://juan-suarezp.github.io/Tk/content/text.html)) en el que se mostrará la ruta y el texto que contiene el archivo seleccionado. Por ejemplo, si se selecciona el archivo .py del ejemplo el resultado es el siguiente:

![funcionfiledialog](https://user-images.githubusercontent.com/58320351/128614312-97318e94-5aad-45d0-92bd-acb3575e9d09.png)

El método `Abrir` abre la ventana que permite seleccionar el archivo. Esta ventana se abre con `tk.filedialog.askopenfilename` y se indica las opciones de tipo de archivos a buscar con `filetypes`, en el ejemplo se pueden buscar archivos .py o cualquier tipo de archivos. Estas opciones se agregan como se observa en la lista `ftypes`. Luego, se valida que se haya seleccionado un archivo, de ser así, se muestra la ruta en el text y por medio del método `Leer` se lee y retorna el texto del archivo para finalmente mostrarlo también en el text.
