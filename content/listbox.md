# Tkinter Listbox
Permite agregar un espacio para crear una lista de opciones. Es posible configurar si se permite seleccionar una o varias opciones a la vez.

## Ejemplo

```python
# -*- coding: utf-8 -*-
"""
Ejemplo de ventana básico con listbox

"""
#Importamos las librerías necesarias
import tkinter as tk

def mostrar():
    #Verifica si hay algún elemento seleccionado y lo muestra
    if len(listbox.curselection()) != 0:
        seleccion=''
        for ind in listbox.curselection():
            seleccion = seleccion+listbox.get(ind)+"\n"
        print(seleccion)

ventana = tk.Tk() #Crea la ventana principal

#Se crea un frame
frame = tk.Frame(ventana)
frame.pack()

# Crear una barra de deslizamiento con orientación vertical
scrollbar1 = tk.Scrollbar(frame, orient=tk.VERTICAL)
# Ubicarla a la derecha.
scrollbar1.pack(side=tk.RIGHT, fill=tk.Y)

#Crear la lista y vincular con la barra de deslizamiento.
listbox = tk.Listbox(frame, yscrollcommand=scrollbar1.set, selectmode="multiple")
scrollbar1.config(command=listbox.yview)

# Insertar 20 elementos
for i in range(20):
    listbox.insert(i, "Elemento {}".format(i))

listbox.pack()
        
#Se crea un botón y se conecta con la función
boton = tk.Button(ventana,text="Mostrar selección",command=mostrar)
boton.pack()

ventana.mainloop()
```
El resultado es el siguiente:

![ventanalistbox](https://user-images.githubusercontent.com/58320351/128614356-f96ffdd3-5301-4ea6-8f68-718faebaa5c8.png)

Este ejemplo muestra cómo se puede ingresar elementos a la lista con `listbox.insert` y cómo se recupera el índice del (de los) elemento (s) seleccionado(s) con `listbox.curselection`.

Se crea un frame (ver [Tkinter Frame](https://juan-suarezp.github.io/Tk/content/frame.html)) para contener una barra de desplazamiento (ver [Tkinter Scrollbar](https://juan-suarezp.github.io/Tk/content/scrollbar.html)) y una listbox. Además, se crea un botón (ver [Tkinter Button](https://juan-suarezp.github.io/Tk/content/button.html)) que está conectado a la función `mostrar`. La función muestra en la terminal los elementos que están seleccionados de la lista, así:

![funcionlistbox](https://user-images.githubusercontent.com/58320351/128614361-806cb55d-2b6d-4850-b254-66b2330ddab7.png)

Después de crear la `tk.Tk`, se define el frame, la barra de desplazamiento, la listbox, la función y el botón. Para la listbox se define que va a estar contenida en el frame, al igual que la barra de desplazamiento, además de las opciones `yscrollcommand` y `selectmode`. `yscrollcommand` se define como `scrollbar1.set` e indica la barra de desplazamiento para la listbox en el  eje y, en este caso `scrollbar1`. `selectmode` indica si es posible seleccionar una o varias opciones de la lista a la vez.

[Aquí](https://www.tutorialspoint.com/python3/tk_listbox.htm) para ver más opciones de Listbox.
