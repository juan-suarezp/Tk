# Eventos

```python
# -*- coding: utf-8 -*-
"""
Ejemplo de ventana con eventos simples

"""
import tkinter as tk 

def Fun1(event): #Un click
    print("Single Click") 

def Fun2(event): #Doble click                
    print("Double Click")


Ventana = tk.Tk()
Ventana.title("Titulo ventana")
Ventana.geometry("320x100")

#Label
Label = tk.Label(Ventana, text='Mouse clicks en label')
Label.pack()

#Botón
Boton = tk.Button(Ventana, text='Mouse clicks en botón')
Boton.pack()

#bind conecta los eventos a los widgets
Boton.bind('<Button-1>', Fun1)
Boton.bind('<Double-1>', Fun2)

Label.bind('<Button-1>', Fun1)
Label.bind('<Double-1>', Fun2) 

Ventana.mainloop()
```
El resultado es el siguiente:

![ventanaeventos](https://user-images.githubusercontent.com/58320351/128614298-7df22811-ab49-413e-a2bf-d354210fe9a8.png)

[Aquí](https://effbot.org/tkinterbook/tkinter-events-and-bindings.htm) para ver más eventos.

[Aquí](https://www.geeksforgeeks.org/python-binding-function-in-tkinter/) para ver otros ejemplos.
