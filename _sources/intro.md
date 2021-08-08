# Tkinter
```{admonition} Departamento de Ingeniería Eléctrica - Facultad de Ingeniería - Universidad de Antioquia
Este repositorio es una guía para los estudiantes de ingeniería eléctrica que están cursando algoritmos y programación/computación numérica en la Universidad de Antioquia.
```
```{note}
Versión de Python: 3.8
```

Tkinter es una librería de Python que permite crear interfaz gráfica de usuario (GUI en inglés). Es la librería que viene por defecto con la instalación de Python; esto no significa que otras alternativas, como por ejemplo [PyQt](https://github.com/juan-suarezp/PythonPyQtTutorial), sean más potentes que Tkinter.

## GUI con Tkinter
El primer paso para crear una GUI es crear la ventana principal (`Tk`), como se muestra en el siguiente código:

```python
import tkinter as tk

ventana = tk.Tk()
ventana.mainloop()
```

El resultado es el siguiente:

![ventana](https://user-images.githubusercontent.com/58320351/128613754-7121acb1-4fa8-4d74-a703-561d961e0652.png)

Una aplicación solo puede tener una `Tk`, debido a que es la raiz del programa y el primer widget que se debe crear; por lo tanto, cerrar la `Tk` cerraría la GUI. Existen otro tipo de ventanas llamadas `Toplevel` que son ventanas de la aplicación, la diferencia con la `Tk` es que al cerrar una ventana `Toplevel` destruirá todos los widgets secundarios colocados en esa ventana pero no cerrará el programa. Es importante resaltar que, además de la `Tk` y las ventanas `Toplevel`, existen algunas ventanas predeterminadas como las de [Filedialog](https://juan-suarezp.github.io/Tk/content/filedialog.html) o las de [Messagebox](https://juan-suarezp.github.io/Tk/content/messagebox.html) y otros widgets como los [Frames](https://juan-suarezp.github.io/Tk/content/frame.html) y [Labelframes](https://juan-suarezp.github.io/Tk/content/labelframe.html) que sirven como contenedores de otros widgets.

Una vez se tiene la ventana principal, lo siguiente es agregar los botones, entradas, labels y demás widgets que necesitemos. Para esto, Tkinter cuenta con tres mecanismos para gestionar la geometría de los widgets de nuestra GUI: los métodos `pack()`, `grid()` y `place()`.

### Pack
Este mecanismo para gestionar la geometría de los widgets los organiza en bloques antes de ubicarlos en el widget principal. Veamos un ejemplo simple con algunos botones:

```python
import tkinter as tk

ventana = tk.Tk()

boton1 = tk.Button(ventana, text="1")
boton1.pack(side="top")
boton2 = tk.Button(ventana, text="2")
boton2.pack(side="top")
boton3 = tk.Button(ventana, text="3")
boton3.pack(side="left")
boton4 = tk.Button(ventana, text="4")
boton4.pack(side="bottom")

ventana.mainloop()
```
![ventanapack](https://user-images.githubusercontent.com/58320351/128613760-e41cec97-9c6c-438e-81d5-5a7886e6af01.png)


Se puede observar que se respeta el orden en que se "empacan" los widgets. Esto se observa claramente con los botones 1 y 2, los cuales tienen `side = "top"`, como el botón 1 está primero, se respeta y queda sobre el botón 2 que después queda sobre los widgets que se ubiquen después. Es un método muy útil cuando se va a crear una aplicación con pocos widgets.

[Aquí](https://www.tutorialspoint.com/python/tk_pack.htm) para ver más sobre el método pack.

### Grid
Este mecanismo para gestionar la geometría de los widgets los organiza en una tabla en el widget principal. Veamos el ejemplo anterior con este método:

```python
import tkinter as tk

ventana = tk.Tk()

boton1 = tk.Button(ventana, text="1")
boton1.grid(row=0, column=0)
boton2 = tk.Button(ventana, text="2")
boton2.grid(row=1, column=1)
boton3 = tk.Button(ventana, text="3")
boton3.grid(row=2, column=2)
boton4 = tk.Button(ventana, text="4")
boton4.grid(row=3, column=3)

ventana.mainloop()
```
![ventanagrid](https://user-images.githubusercontent.com/58320351/128613762-43fd36e9-fc90-4b16-92e2-1537ae146f05.png)

Este método permite ubicar los widgets indicando la fila y la columna. Por defecto, el tamaño de las filas y columnas está dado por los widgets que estén ubicados en ellas, pero es posible cambiar el tamaño y combinar filas o columnas. Este método es muy útil cuando las aplicaciones contienen muchos widgets.

[Aquí](https://www.tutorialspoint.com/python/tk_grid.htm) para ver más sobre el método grid.

### Place
Este mecanismo para gestionar la geometría de los widgets permite ubicarlos en una posición específica en el widget principal. continuando con el ejemplo anterior:

```python
import tkinter as tk

ventana = tk.Tk()

boton1 = tk.Button(ventana, text="1")
boton1.place(x=0, y=0)
boton2 = tk.Button(ventana, text="2")
boton2.place(x=100, y=0)
boton3 = tk.Button(ventana, text="3")
boton3.place(x=100, y=100)
boton4 = tk.Button(ventana, text="4")
boton4.place(x=0, y=100)

ventana.mainloop()
```
![ventanaplace](https://user-images.githubusercontent.com/58320351/128613764-209a56e3-cf08-4292-b955-f96c99c6ae66.png)

Este método tiene la ventaja de que permite ubicar exactamente donde se quiere los widgets, pero hay que tener cuidado con su tamaño. Cuando son muchos widgets se vuelve problemático ubicarlos todos.

[Aquí](https://www.tutorialspoint.com/python/tk_place.htm) para ver más sobre el método place.
