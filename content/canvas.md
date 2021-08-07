# Tkinter Canvas
Permite agregar espacios rectangulares para dibujar líneas, polígonos, arcos, óvalos o mostrar imágenes.

## Ejemplo

```python
# -*- coding: utf-8 -*-
"""
Ejemplo de ventana básico con canvas para dibujar

"""
#Importamos las librerías necesarias
import tkinter as tk

def accionArc():
    #Dibuja un arco
    canvas.create_arc(10,10,250,250, start = 0, extent = 150, fill = "blue")
    
def accionLine():
    #Dibuja una línea
    canvas.create_line(20,20,250,250,fill = "white")

ventana = tk.Tk() #Crea la ventana principal
ventana.geometry("500x500") #Tamaño de la ventana en pixeles

#Espacio para dibujar
canvas = tk.Canvas(ventana,bd = 10,bg ="black")
canvas.pack()

#Botones para las acciones
botonArc = tk.Button(ventana,text="Arco",command=accionArc)
botonArc.pack()

botonLine = tk.Button(ventana,text="Línea",command=accionLine)
botonLine.pack()

ventana.mainloop()
```
El resultado es el siguiente:

![ventanacanvas](https://user-images.githubusercontent.com/58320351/128614213-802fb5d2-31c8-4988-993f-dff209e4f7dc.png)

Los botones (ver [Tkinter Button](https://juan-suarezp.github.io/Tk/content/button.html)) `Arco` y `Línea` están conectados respectivamente con las funciones `accionArc` y `accionLine`. Al presionar el botón `Arco` resulta:

![arcocanvas](https://user-images.githubusercontent.com/58320351/128614214-bf787fbf-9246-4a6d-9e06-adfeed070682.png)

`canvas.create_arc` dibuja un arco, se debe indicar las coordenadas y es posible indicar el ángulo inicial, el ángulo final y el color del arco.

Luego se presiona el botón línea:

![lineacanvas](https://user-images.githubusercontent.com/58320351/128614216-625b7e7f-b29a-445b-87cd-bc0c5f9a877f.png)

`canvas.create_line` dibuja una línea, se debe indicar las coordenas de los dos puntos y es posible indicar el color.

Después de crear la ventana principal, se crea el canvas con `tk.Canvas` y se indica el widget que lo va a contener `ventana`. Además, se usaron las opciones `bd` y `bg`, la primera permite crear un borde en el canvas y la segunda permite seleccionar el color del fondo.

[Aquí](https://www.tutorialspoint.com/python3/tk_canvas.htm) para ver más opciones de Canvas.
