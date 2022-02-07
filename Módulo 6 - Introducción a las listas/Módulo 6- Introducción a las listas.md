# Introducción

Como desarrollador, con frecuencia trabajarás con conjuntos de datos. Es posible que debas administrar varios nombres, edades o direcciones. Almacenar cada valor en una variable individual hace que el código sea más difícil de leer y escribir. Para almacenar varios valores, puedes usar una lista de Python.

## Escenario: Trabajar en una aplicación planetaria

Imagina que eres un desarrollador que quiere crear una aplicación para trabajar con una lista de planetas. Deseas pedirle al usuario el nombre de un planeta y mostrar los planetas más cerca y más lejos del sol.

En este módulo, aprenderás a trabajar con listas de Python y algunas de las operaciones más comunes.

## ¿Qué aprenderás?
Después de completar este módulo, podrás:

* Identificar cuándo usar una lista.
* Crea una lista.
* Obtener acceso a un elemento determinado de una lista mediante índices.
* Insertar elementos al final de una lista.
Ordenar y dividir una lista.

## ¿Cuál es el objetivo principal?
Al final de este módulo, comprenderás cuándo usar una estructura de lista y cómo puede ayudar a organizar tus datos.

---

## Introducción a las listas
Python tiene muchos tipos integrados, como cadenas y enteros. Python tiene un tipo para almacenar una colección de valores: la lista.

### Crear una lista
Para crear una lista, asigne una secuencia de valores a una variable. Cada valor está separado por una coma y rodeado por corchetes (``[]``). En el ejemplo siguiente se almacena la lista de todos los planetas de la variable ``planets``:
```
planets = ['Mercury', 'Venus', 'Earth', 'Mars', 'Jupiter', 'Saturn', 'Uranus', 'Neptune']
```

### Acceder a elementos de lista por índice

Puedes acceder a cualquier elemento de una lista poniendo el *index/índice* entre ``[]`` después del nombre de la variable de lista. Los índices comienzan desde 0, por lo que en el siguiente código ``planets[0]``, es el primer elemento de la lista ``planets``:

```
print('The first planet is', planets[0])
print('The second planet is', planets[1])
print('The third planet is', planets[2])
```
*Salida: 'The first planet is Mercury', 'The second planet is Venus', 'The third planet is Earth'*

**Nota: Todos los índices inician en 0, es decir en la posición 0 de la lista planets, es Mercury, en la posición 1 el elemento es Venus y así sucesivamente**

También puedes modificar los valores de una lista mediante un índice. Lo hacemos asignando un nuevo valor, de la misma manera que asignaría un valor a una variable. Por ejemplo, podrías cambiar el nombre de Marte en la lista para usar su apodo:

```
planets[3] = 'Red Planet'
print('Mars is also known as', planets[3])
```

*Salida: Mars is also known as Red Planet*

### Determinar la longitud de una lista
Para obtener la longitud de una lista, utilice la función integrada ``len``. El código siguiente crea una nueva variable,``number_of_planetsplanets`` . El código asigna a esa variable el número de elementos de la lista ``planets`` (8 planetas).

```
number_of_planets = len(planets)
print('There are', number_of_planets, 'planets in the solar system.')
```
*Salida: There are 8 planets in the solar system*

### Agregar valores a listas
Las listas en Python son dinámicas: Es decir, puedes agregar y eliminar elementos después de crearlos. Para agregar un elemento a una lista, utilice el método ``.append(value)``.

Por ejemplo, el código siguiente agrega la cadena ``'Pluto`` al final de la lista ``planets``:

```
planets.append('Pluto')
number_of_planets = len(planets)
print('There are actually', number_of_planets, 'planets in the solar system.')
```
*Salida: There are actually 9 planets in the solar system.*

### Eliminar valores de una lista
Puedes eliminar el último elemento de una lista llamando al método ``.pop()`` de la variable de lista:

```
planets.pop()  # Goodbye, Pluto
number_of_planets = len(planets)
print('No, there are definitely', number_of_planets, 'planets in the solar system.')
```

### Índices negativos

Hasta ahora hemos visto cómo usar índices para obtener un elemento individual de una lista:

```
print("The first planet is", planets[0])
```
*Salida: The first planet is Mercury*

Los índices comienzan en cero y aumentan. Los índices negativos comienzan al final de la lista y trabajan hacia atrás.

En el ejemplo siguiente, un índice de ``-1`` devuelve el último elemento de una lista. Un índice de ``-2`` retorna del penúltimo al último.

```
print('The last planet is', planets[-1])
print('The penultimate planet is', planets[-2])
```
*Salida: The last planet is Neptune*
*Salida: The penultimate planet is Uranus*

Si quisieras devolver del tercero al último, usarías un índice de ``-3``(y así sucesivamente).

### Buscar un valor en una lista
Para determinar en qué parte de una lista se almacena un valor, utilizamos el método ``index()`` de la lista. Este método busca el valor y devuelve el índice de ese elemento en la lista. Si no encuentra una coincidencia, devuelve ``-1``.

En el ejemplo siguiente se muestra el uso de ``'Jupiter`` como valor de índice:

```
jupiter_index = planets.index('Jupiter')
print('Jupiter is the', jupiter_index + 1, 'planet from the sun')
```
*Salida: Jupiter is the 5 planet from the sun*

## Trabajar con números en listas
Hasta ahora, has estado usando nombres de planetas en una lista. Es posible que te preguntes acerca de trabajar con otros tipos de datos, como números.

¿Sabías que la gravedad en otros planetas es más fuerte o más débil dependiendo de la masa o el tamaño del planeta? La gravedad a menudo se mide en G, donde la gravedad en la Tierra es 1 y otros planetas se miden en [relación con la Tierra](https://nssdc.gsfc.nasa.gov/planetary/factsheet/planet_table_ratio.html).

La gravedad en la luna es de 0,166 G, por lo que los astronautas pueden saltar tan alto en la luna. La gravedad en Neptuno es de 1,12 G, por lo que saltar es más difícil. Incluso los atletas olímpicos tendrían dificultades para saltar más de 2 metros sobre Neptuno.

![Planeta](https://raw.githubusercontent.com/FernandaOchoa/CursoIntroPython/main/images/planet.png)

### Almacenar números en listas
Para almacenar números con decimales en Python, utilizamos el tipo ``float``. Para crear un float, introduzca el número con el decimal y asígnelo a una variable:

```
gravity_on_earth = 1.0
gravity_on_the_moon = 0.166
```

En el siguiente código creamos una lista que muestra las fuerzas gravitacionales de los ocho planetas del sistema solar, en G:

```
gravity_on_planets = [0.378, 0.907, 1, 0.379, 2.36, 0.916, 0.889, 1.12]
```

En esta lista, ``gravity_on_planets[0]`` está la gravedad en Mercurio (0.378 G), ``gravity_on_planets[1]`` es la gravedad en Venus (0.907 G), y así sucesivamente.

En la Tierra, un autobús de dos pisos pesa 12,650 kilogramos (kg), que es 12.65 toneladas. En Mercurio, donde la gravedad es de 0,378 G, el mismo autobús pesa 12.65 toneladas multiplicadas por 0.378. En Python, para multiplicar dos valores, se utiliza el símbolo ``*``.

En el siguiente ejemplo, puedes calcular el peso de un bus de dos pisos en diferentes planetas obteniendo el valor de la lista:

```
bus_weight = 12650 # in kilograms, on Earth

print('On Earth, a double-decker bus weighs', bus_weight, 'kg')
print('On Mercury, a double-decker bus weighs', bus_weight * gravity_on_planets[0], 'kg')
```

*Salida: On Earth, a double-decker bus weighs 12650 kg*  
*Salida: On Mercury, a double-decker bus weighs 4781.7 kg*

### min() y max () con listas
Python tiene funciones integradas para calcular los números más grandes y más pequeños de una lista. La función ``max()`` devuelve el número más grande y la función ``min()`` devuelve el más pequeño. Así que ``min(gravity_on_planets)``devuelve el número más pequeño de la lista, ``gravity_on_planets`` que es 0.378 (Mercurio).

El siguiente código calcula los pesos mínimos y máximos en el sistema solar mediante el uso de esas funciones:

```
bus_weight = 12650 # in kilograms, on Earth

print('On Earth, a double-decker bus weighs', bus_weight, 'kg')
print('The lightest a bus would be in the solar system is', bus_weight * min(gravity_on_planets), 'kg')
print('The heaviest a bus would be in the solar system is', bus_weight * max(gravity_on_planets), 'kg')
```
```
Salida:
* On Earth, a double-decker bus weighs 12650 kg
* The lightest a bus would be in the solar system is 4781.7 kg
* The heaviest a bus would be in the solar system is 29854 kg
```
## Manipular datos de lista

Es posible que debas trabajar con diferentes partes de una lista. Por ejemplo, supongamos que tiene una lista con cantidades de lluvia para varios meses. Para analizar adecuadamente este tipo de datos, es posible que debas buscar precipitaciones en otoño o en un período de tres meses. O puede ser que desees ordenar la lista de mayor cantidad de lluvia a menor.

Python proporciona un soporte sólido para trabajar con los datos en las listas. Este soporte incluye el ``slicing`` (examinando solo una parte) y el ``sorting``.

### Slice list

Puedes recuperar una parte de una lista mediante un ``slice`` (Entendamos slice como una porción, un pedacito, un fragmento, segmento.). ``Slice`` utiliza corchetes, pero en lugar de un solo elemento, tiene los índices inicial y final de los elementos que queremos recuperar. Cuando se utiliza ``slice``, se crea una nueva lista que comienza en el índice inicial y que termina antes (y no incluye) el índice final.

La lista de planetas tiene ocho elementos. La Tierra es la tercera en la lista. Para obtener los planetas antes que la Tierra, use un ``slice`` para obtener elementos que comienzan en 0 y terminan en 2:

```
planets = ['Mercury', 'Venus', 'Earth', 'Mars', 'Jupiter', 'Saturn', 'Uranus', 'Neptune']
planets_before_earth = planets[0:2]
print(planets_before_earth)
```

*Salida: ['Mercury', 'Venus']*

Observa cómo la Tierra no está incluida en la lista. La razón es que el índice termina antes que el índice final.

Para obtener todos los planetas después de la Tierra, comenzamos en el tercero y vamos al octavo:

```
planets_after_earth = planets[3:8]
print(planets_after_earth) 
```
*Salida: ['Mars', 'Jupiter', 'Saturn', 'Uranus', 'Neptune']*

En este ejemplo, se muestra Neptuno. La razón es que el índice para Neptuno es `7`, porque la indexación comienza en `0`. Debido a que el índice final era `8`, incluye el último valor. Si no coloca el índice de detención en el ``slice``, Python asume que deseas ir al final de la lista:

```
planets_after_earth = planets[3:]
print(planets_after_earth)
```

*Salida: ['Mars', 'Jupiter', 'Saturn', 'Uranus', 'Neptune']*

Un ``slice`` crea una nueva lista. No modifica la lista actual.

### Uniendo listas

Has visto cómo puedes usar slices para dividir listas, pero ¿Qué hay de unirlas de nuevo?

Para unir dos listas, utilice el operador (`+`) con dos listas para devolver una nueva lista.

Hay 79 lunas conocidas de Júpiter. Las cuatro más grandes son Io, Europa, Ganímedes y Calisto. Estas se llaman las lunas galileanas, porque Galileo Galilei las descubrió usando su telescopio en 1610. Más cerca de Júpiter que del grupo galileo está el grupo de Amaltea. Consiste en las lunas Metis, Adrastea, Amaltea y Teba.

Crea dos listas. Llene la primera lista con las cuatro lunas de Amaltea y la segunda lista con las cuatro lunas galileanas. Únelos para crear una nueva lista:

```
amalthea_group = ['Metis', 'Adrastea', 'Amalthea', 'Thebe']
galilean_moons = ['Io', 'Europa', 'Ganymede', 'Callisto']

regular_satellite_moons = amalthea_group + galilean_moons
print('The regular satellite moons of Jupiter are', regular_satellite_moons)

```
*Salida: The regular satellite moons of Jupiter are ['Metis', 'Adrastea', 'Amalthea', 'Thebe', 'Io', 'Europa', 'Ganymede', 'Callisto']*

Al unir las listas, se crea una nueva lista. No se modifica la lista actual.

### Ordenar listas

Para ordenar una lista, utilizamos el método ``sort()`` de la lista. Python ordenará una lista de cadenas en orden alfabético y una lista de números en orden numérico:

```
regular_satellite_moons.sort()
print("The regular satellite moons of Jupiter are", regular_satellite_moons)
```
*Salida: The regular satellite moons of Jupiter are ['Adrastea', 'Amalthea', 'Callisto', 'Europa', 'Ganymede', 'Io', 'Metis', 'Thebe']*

Para ordenar una lista en forma inversa, llamamos al método ``.sort(reverse=True)`` de la lista:

```
regular_satellite_moons.sort(reverse=True)
print("The regular satellite moons of Jupiter are", regular_satellite_moons)
```
*Salida: The regular satellite moons of Jupiter are ['Thebe', 'Metis', 'Io', 'Ganymede', 'Europa', 'Callisto', 'Amalthea', 'Adrastea']*

Al usar el método ``.sort`` modificas la lista actual.

---

## Resumen

Queríamos trabajar con una colección de datos sobre planetas. Nuestra aplicación necesitaba la capacidad de determinar dónde estaban los elementos en relación con otros y mostrar los resultados. Hicimos esto usando una lista.

Las listas de Python son una herramienta importante cuando se trabaja con datos. Has visto cómo crear, dividir, unir y ordenar listas. Usará estas habilidades en casi todas las aplicaciones de Python que cree.

En este módulo, aprendiste a:

* Identificar cuándo usar una lista.
* Crear una lista.
* Obtener acceso a un elemento determinado de una lista mediante índices.
* Insertar elementos al final de una lista.
* Ordenar y dividir una lista.


---

Curso Propedútico de Python para Launch X - Innovacción Virtual.

Material desarrollado con base en los contenidos de MSLearn y la metáfora de LaunchX, traducción e implementación por: Fernanda Ochoa - Learning Producer de LaunchX.

Redes:
* GitHub: [FernandaOchoa](https://github.com/FernandaOchoa)
* Twitter: [@imonsh](https://twitter.com/imonsh)
* Instagram: [fherz8a](https://www.instagram.com/fherz8a/)