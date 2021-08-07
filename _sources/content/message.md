# Tkinter Message
Permite mostrar texto, es posible cambiarlo pero no directamente por el usuario. El widget message es similar al label (ver [Tkinter Label](https://juan-suarezp.github.io/Tk/content/label.html)), solo que el message ajusta el texto a sus dimensiones.

## Ejemplo

```python
# -*- coding: utf-8 -*-
"""
Ejemplo de ventana básico con message

"""
#Importamos las librerías necesarias
import tkinter as tk

def accion(): #Suma 1 al valor anterior del message
    cont = int(variable.get())
    cont = cont+1
    variable.set(str(cont))

ventana = tk.Tk() #Crea la ventana principal
ventana.geometry("200x100")

#Message con mensaje inicial que no cambia
message1 = tk.Message(ventana,text="Mensaje sin cambiar")
message1.pack()

#Message con mensaje inicial que cambia
variable = tk.StringVar()
variable.set("0") #Texto inicial
message2 = tk.Message(ventana,textvariable=variable)
message2.pack()
    
#Se crea el botón y se conecta con la función
boton = tk.Button(ventana,text="Aumentar",command=accion)
boton.pack()

ventana.mainloop()
```
el resultado es el siguiente:

![ventanamessage](https://user-images.githubusercontent.com/58320351/128614435-313a5166-a130-4076-bcfe-6e461e685efd.png)

En la `tk.Tk` se agregan dos messages y un botón. Uno de los message tiene un mensaje inicial que no tiene posibilidad de cambio, mientras el otro message cambia cada vez que se presiona el botón. La función `acción` está conectada con el botón (ver [Tkinter Button](https://juan-suarezp.github.io/Tk/content/button.html)) y al ser ejecutada realiza el cambio en el message como se observa a continuación:

![funcionmessage](https://user-images.githubusercontent.com/58320351/128614438-488db0be-f35d-4aa4-9b7c-66513f4c4067.png)

Al definir los message, se indica el widget que los va a contener y el texto para mostrar al inicio. Si se desea cambiar el texto que hay en un message, se define `textvariable` que guarda el texto que hay en el message en una variable. Con esta variable se tiene la posibilidad de recuperar el texto que contiene (`variable.get`) o cambiarlo (`variable.set`).

[Aquí](https://www.tutorialspoint.com/python3/tk_message.htm) para ver más opciones de Message.
