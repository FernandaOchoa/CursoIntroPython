# Introducción

Las cadenas de Python son uno de los tipos principales y más comunes en el lenguaje. Interactuar con cadenas, incluido el formato y el reemplazo de texto, es una habilidad esencial a desarrollar para trabajar con código Python.

## Escenario: Crear un programa para describir hechos sobre la Luna

Imagina que estás creando un programa para describir algunas mediciones y otra información sobre la Luna. Deberás usar varias operaciones de cadena para crear el resultado.

## ¿Qué aprenderás?
Al final de este módulo, podrás:

* Utilizar métodos de cadena especiales.
* Utilizar variables para introducir valores en el texto.
* Aplicar otras técnicas de formato avanzadas para cambiar la forma en que se presenta el texto.

## ¿Cuál es el objetivo principal?
En este módulo, incorporarás operaciones de cadena cuando crees un programa Python.

---

## Conceptos básicos de cadenas en Python

Aunque las cadenas en Python parecen ser simples y directas, hay cierta complejidad en las reglas de cadena que es importante comprender. Conocer las reglas le ayuda a evitar ser sorprendido por el comportamiento de las cadenas cuando modifica valores o da formato al texto.

### Inmutabilidad de las cadenas
En Python, las cadenas son inmutables. Es decir, no pueden cambiar. Esta propiedad del tipo de cadena puede ser sorprendente, porque Python no te da errores cuando alteras las cadenas.

En nuestro ejemplo para este módulo, tienes un solo hecho sobre la Luna que está asignado a una variable, y debes agregarle otro hecho (oración). Usando el intérprete de Python, parece que agregar el segundo hecho alteraría la variable:

```
fact = 'The Moon has no atmosphere.'
fact + 'No sound can be heard on the Moon.'
```
*Salida: 'The Moon has no atmosphere.No sound can be heard on the Moon.'*

Aunque puede parecer que hemos modificado la variable ``fact``, una comprobación rápida del valor revela que el valor original no ha cambiado:

```
fact
```
*Salida: 'The Moon has no atmosphere.'*

El truco aquí es que debes usar un valor devuelto. Cuando agregas cadenas, Python no modifica ninguna cadena, pero devuelve una nueva cadena como resultado. Para mantener este nuevo resultado, asígnelo a una nueva variable:

```
two_facts = fact + 'No sound can be heard on the Moon.'
two_facts
```
*Salida: 'The Moon has no atmosphere.No sound can be heard on the Moon.'*

Como resultado, las operaciones en cadenas siempre producen nuevas cadenas.

### Acerca del uso de comillas

Puedes incluir cadenas de Python entre comillas simples, dobles o triples. Aunque puedes usarlos indistintamente, es mejor usar un tipo de manera consistente dentro de un proyecto. Por ejemplo, la siguiente cadena utiliza comillas dobles:

```
moon_radius = "The Moon has a radius of 1,080 miles"
```

Sin embargo, cuando una cadena contiene palabras, números o caracteres especiales (una subcadena) que también están entre comillas, debes usar un estilo diferente. Por ejemplo, si una subcadena utiliza comillas dobles, encierra toda la cadena entre comillas simples, como se muestra aquí:

```
'The "near side" is the part of the Moon that faces the Earth'
```

Del mismo modo, si hay comillas simples (o un apóstrofo, como en Moon en el siguiente ejemplo) en cualquier lugar dentro de la cadena, encierra toda la cadena entre comillas dobles:

```
"We only see about 60% of the Moon's surface"
```

Si no se alternan comillas simples y dobles, el intérprete de Python puede provocar un error de sintaxis, como se muestra aquí:

```
'We only see about 60% of the Moon's surface'
  File '<stdin>', line 1
    'We only see about 60% of the Moon's surface'
                                       ^
SyntaxError: invalid syntax
```

Cuando el texto tiene una combinación de comillas simples y dobles, puedes utilizar comillas triples para evitar problemas con el intérprete:

```
"""We only see about 60% of the Moon's surface, this is known as the "near side"."""
```

### Texto multilínea

Hay algunas maneras diferentes de definir varias líneas de texto como una sola variable. Las formas más comunes son:

* Utiliza un carácter de nueva línea ().\n
* Utiliza comillas triples (""")..
* Los caracteres de nueva línea separan el texto en varias líneas al imprimir la salida:

```
multiline = "Facts about the Moon:\n There is no atmosphere.\n There is no sound."
print(multiline)
Facts about the Moon:
 There is no atmosphere.
 There is no sound.
 ```

 Puedes lograr el mismo resultado utilizando comillas triples:}

 ```
 multiline = """Facts about the Moon:
...  There is no atmosphere.
...  There is no sound."""
print(multiline)
Facts about the Moon:
 There is no atmosphere.
 There is no sound
  ```

---

## Métodos string en Python

Las cadenas son uno de los tipos de métodos más comunes en Python. A menudo tendrá que manipularlos para extraer información o ajustarse a un formato determinado. Python incluye varios métodos de cadena que están diseñados para realizar las transformaciones más comunes y útiles.

Los métodos de cadena forman parte del tipo ``str``. Esto significa que los métodos existen como variables de cadena o parte de la cadena directamente. Por ejemplo, el método ``.title()`` se puede utilizar con una cadena directamente:

```
'temperatures and facts about the moon'.title()
```
*Salida: 'Temperatures And Facts About The Moon'*

Y el mismo comportamiento y uso ocurre en una variable:

```
heading = 'temperatures and facts about the moon'
heading.title()
```
*Salida: 'Temperatures And Facts About The Moon'*

### Dividir una cadena

Un método de cadena común es ``.split()`` . Sin argumentos, el método separará la cadena en cada espacio. Esto crearía una lista de cada palabra o número que está separado por un espacio:

```
temperatures = '''Daylight: 260 F
... Nighttime: -280 F'''
temperatures .split()
```
*Salida: ['Daylight:', '260', 'F', 'Nighttime:', '-280', 'F']*

En este ejemplo, se trata de varias líneas, por lo que el carácter de nueva línea (implícito) se puede utilizar para dividir la cadena al final de cada línea, creando líneas individuales:

```
temperatures .split('\n')
```
*Salida: ['Daylight: 260 F', 'Nighttime: -280 F']*

Este tipo de división se vuelve útil cuando necesita un bucle para procesar o extraer información, o cuando está cargando datos de un archivo de texto u otro recurso.

### Buscar una cadena

Además de usar un bucle, algunos métodos de cadena pueden buscar contenido antes del procesamiento, sin la necesidad de un bucle. Supongamos que tienes dos oraciones que discuten las temperaturas en varios planetas y lunas, pero solo te interesan las temperaturas que están relacionadas con nuestra Luna. Es decir, si las frases no hablan de la Luna, no deben procesarse para extraer información.

La forma más sencilla de descubrir si existe una palabra, un carácter o un grupo de caracteres determinados en una cadena es sin usar un método:

```
'Moon' in 'This text will describe facts and challenges with space travel'
```
*Salida: False*
```
'Moon' in 'This text will describe facts about the Moon'
```
*Salida: True*

Un enfoque para encontrar la posición de una palabra específica en una cadena es usar el método ```.find()```:

```
temperatures = """Saturn has a daytime temperature of -170 degrees Celsius,
... while Mars has -28 Celsius."""
```

```
temperatures.find('Moon')
```
*Salida: -1*

El método ```.find()``` devuelve ```-1``` un cuando no se encuentra la palabra o devuelve el índice (el número que representa el lugar en la cadena). Así es como se comportaría si estuvieras buscando la palabra Marte:

```
temperatures.find('Mars')
```
*Salida: 68*

``68`` es la posición donde aparece en la cadena 'Mars'.

Otra forma de buscar contenido es usar el método ``.count()``, que devuelve el número total de apariciones de una determinada palabra en una cadena:

```
temperatures.count('Mars')
```
*Salida: 1*
```
temperatures.count('Moon')
```
*Salida: 0*

Las cadenas en Python distinguen entre mayúsculas y minúsculas, lo que significa que Luna (Moon) y luna (moon) se consideran palabras diferentes. Para realizar una comparación sin distinción de mayúsculas y minúsculas, puedes convertir una cadena en todas las letras minúsculas mediante el método: ``.lower()``.

```
"The Moon And The Earth".lower()
```
*Salida: 'the moon and the earth'*

Al igual que el método ``.lower()``, las cadenas tienen un método que hace lo contrario ``.upper()``, convirtiendo cada carácter en mayúsculas:

```
'The Moon And The Earth'.upper()
```
*'THE MOON AND THE EARTH'*

Cuando buscas y compruebas contenido, un enfoque más sólido es poner en minúsculas una cadena para que el estilo de escritura no impida una coincidencia. Por ejemplo, si estás contando el número de veces que aparece 'la' palabra, el método no contaría las veces en que aparece 'La', aunque ambas sean la misma palabra. Puedes utilizar el método ``.lower()`` para cambiar todos los caracteres a minúsculas.

### Comprobar el contenido

Hay ocasiones en las que procesarás texto para extraer información que es irregular en su presentación. Por ejemplo, la siguiente cadena es más sencilla de procesar que un párrafo no estructurado:

```
temperatures = 'Mars Average Temperature: -60 C'
```
Para extraer la temperatura promedio en Marte (Mars), puedes hacerlo con los siguientes métodos:

```
parts = temperatures.split(':')
parts
```
*Salida: ['Mars average temperature', ' -60 C']*

```
parts[-1]
```
*Salida: ' -60 C'*

Los métodos anteriores confían ciegamente en que todo lo que está después de los ``dos puntos (:)`` es una temperatura. La cadena se divide en cuanto encuentra ``:``, lo que produce una lista de dos elementos. Usando ``[-1]`` en la lista devuelve el último elemento, que es la temperatura en este ejemplo.

Si el texto es irregular, no puedes usar los mismos métodos de división para obtener el valor. Debes iterar por todos los elementos y comprobar si los valores son de un tipo determinado. Python tiene métodos que ayudan a comprobar el tipo de cadena:
```
>>> mars_temperature = 'The highest temperature on Mars is about 30 C'
```
```
for item in mars_temperature.split():
    if item.isnumeric():
        print(item)

```
*Salida: 30*

Al igual que el método ``.isnumeric()``, puedes comprobar si hay cadenas que se parezcan a decimales ``.isdecimal()``

*Dato: Podría ser sorprendente saber que ``"-70".isnumeric()`` regresa ``False``. Esto se debe a que todos los caracteres de la cadena tendrían que ser numéricos y el guión ``(-)`` no es numérico. Si necesitas comprobar los números negativos en una cadena, el método ``.isnumeric()`` no funcionaría.*

Hay validaciones adicionales que puedes aplicar en cadenas para comprobar si hay valores. Para los números negativos, el guión está prefijado al número, y eso se puede detectar con el método: ``.startswith()``.

```
'-60'.startswith('-')
```
*Salida: True*

Del mismo modo, el método ``.endswith()`` ayuda a verificar el último carácter de una cadena:

```
if "30 C".endswith("C"):
    print("This temperature is in Celsius")

```
*Salida: 'This temperature is in Celsius'*

### Transformar texto
Hay otros métodos que ayudan en situaciones en las que el texto necesita ser transformado en otra cosa. 

Hasta ahora, hemos visto cadenas que pueden usar ``C`` para Celsius y ``F`` para Fahrenheit. Puedes utilizar el método ``.replace()`` para buscar y reemplazar apariciones de un carácter o grupo de caracteres:

```
'Saturn has a daytime temperature of -170 degrees Celsius, while Mars has -28 Celsius.'.replace('Celsius', 'C')
```

*Salida: 'Saturn has a daytime temperature of -170 degrees C, while Mars has -28 C.'*

Como se mencionó anteriormente, ``.lower()`` es una buena manera de normalizar el texto para hacer una búsqueda sin distinción de mayúsculas y minúsculas. Revisemos rápidamente si algún texto distingue las temperaturas:

```
text = 'Temperatures on the Moon can vary wildly.'
'temperatures' in text
```

*Salida: False*

```
'temperatures' in text.lower()
```
*Salida: True*

Es posible que no necesites hacer una verificación que no distinga entre mayúsculas y minúsculas todo el tiempo, pero estandarizar cada letra es un buen enfoque cuando el texto utiliza un estilo de escritura mixto.

Después de dividir el texto y realizar las transformaciones, es posible que debas volver a juntar todas las partes. Así como el método ``.split()`` puede separar caracteres, el método ``.join()`` puede volver a unirlos. 

El método ``.join()`` requiere un iterable (como una lista de Python) como argumento, por lo que su uso se ve diferente de otros métodos de cadena:

```
moon_facts = ['The Moon is drifting away from the Earth.', 'On average, the Moon is moving about 4cm every year']
'\n'.join(moon_facts)
```
*Salida: 'The Moon is drifting away from the Earth.\nOn average, the Moon is moving about 4cm every year'*

En este ejemplo, el carácter salto de línea ``'\n'`` (retorno de carro, newline) se utiliza para unir todos los elementos de la lista.

---

## Formato de cadenas en Python

Además de transformar el texto y realizar operaciones básicas, como la coincidencia y la búsqueda, es esencial dar formato al texto cuando se presenta información. La forma más sencilla de presentar información de texto con Python es usar la función ``print()``. Te resultará fundamental obtener información en variables y otras estructuras de datos en cadenas que puedan usar ``print()``.

#### Formato con signo de porcentaje ``(%)``

El marcador de posición es ``%s``, y la variable se pasa al texto después del carácter ``%`` fuera de la cadena. A continuación te explico cómo dar formato mediante el uso del carácter``%``:

```
mass_percentage = '1/6'
print('On the Moon, you would weigh about %s of your weight on Earth' % mass_percentage)
```
*Salida: On the Moon, you would weigh about 1/6 of your weight on Earth*

El uso de múltiples valores cambia la sintaxis, ya que requiere paréntesis para rodear las variables que se pasan:

```
print("""Both sides of the %s get the same amount of sunlight,
    but only one side is seen from %s because
    the %s rotates around its own axis when it orbits %s.""" % ('Moon', 'Earth', 'Moon', 'Earth'))
```
*Salida: Both sides of the Moon get the same amount of sunlight,
but only one side is seen from Earth because
the Moon rotates around its own axis when it orbits Earth.*

Aunque este método sigue siendo una forma válida de dar formato a las cadenas, puede provocar errores y una disminución en la claridad en el código cuando se trata de múltiples variables. Cualquiera de las otras dos opciones de formato descritas aquí sería más adecuada para este propósito.

El método ``format()``

El método ``.format()``utiliza llaves ``({})`` como marcadores de posición dentro de una cadena y utiliza la asignación de variables para reemplazar el texto.

```
mass_percentage = '1/6'
print('On the Moon, you would weigh about {} of your weight on Earth'.format(mass_percentage))
```
*Salida: On the Moon, you would weigh about 1/6 of your weight on Earth*

No es necesario asignar variables repetidas varias veces, lo que lo hace menos detallado porque se deben asignar menos variables:

```
print("""You are lighter on the {0}, because on the {0} 
... you would weigh about {1} of your weight on Earth""".format("Moon", mass_percentage))
```
*Salida: You are lighter on the Moon, because on the Moon you would weigh about 1/6 of your weight on Earth*

En lugar de llaves vacías, la sustitución es usar números. Si queremos usar en el primer argumento ``{0}`` (índice de cero) en este caso ``Moon{0}`` sería con el método ``.format()``. Para la repetición simple ``{0}`` funciona bien, pero reduce la legibilidad. Para mejorar la legibilidad, utilizamos argumentos de palabras clave en ``.format()`` y, a continuación, hacemos referencia a los mismos argumentos dentro de las llaves:

```
print("""You are lighter on the {moon}, because on the {moon} 
... you would weigh about {mass} of your weight on Earth""".format(moon="Moon", mass=mass_percentage))
```

*Salida: You are lighter on the Moon, because on the Moon you would weigh about 1/6 of your weight on Earth*

#### Acerca de las cadenas con f

A partir de la versión 3.6 de Python, es posible usar f-strings. Estas cadenas parecen plantillas con las mismas variables con nombre que las del código. El uso de cadenas f en el ejemplo anterior se vería así:

```
print(f'On the Moon, you would weigh about {mass_percentage} of your weight on Earth')
```
*Salida: On the Moon, you would weigh about 1/6 of your weight on Earth*

Las variables van dentro de llaves y la cadena debe usar el prefijo ``f``

Además de que las cadenas f son menos detalladas que cualquier otra opción de formato, es posible usar expresiones dentro de las llaves. Estas expresiones pueden ser funciones u operaciones directas. Por ejemplo, si deseas representar el valor ``1/6`` como un porcentaje con un decimal, puede utilizar la función ``round()`` directamente:

```
round(100/6, 1)
```
*Salida: 16.7*

Con las cadenas f, no es necesario asignar un valor a una variable de antemano:

```
print(f'On the Moon, you would weigh about {round(100/6, 1)}% of your weight on Earth')
```
*Salida: On the Moon, you would weigh about 16.7% of your weight on Earth*

El uso de una expresión no requiere una llamada a una función. Cualquiera de los métodos de cadena también son válidos. Por ejemplo, la cadena podría imponer un estilo de escritura específico para crear un título:

```
subject = 'interesting facts about the moon'
f'{subject.title()}'
```
'Interesting Facts About The Moon'

--- 

# Resumen

Las cadenas de Python son uno de los tipos de datos más comunes utilizados en el lenguaje. En este módulo, aprendimos sobre algunas de sus propiedades  y los métodos más comunes para manipularlas. Finalmente, vimos formas de dar formato a las cadenas mediante el uso de tres técnicas diferentes:

* Uso del formateador ``%``.
* Uso de ``.format()`` en una cadena.
* Usamos ``f-strings``.  

Este conocimiento fundamental te ayudará con otras estructuras de datos en Python que funcionan bien con cadenas, como diccionarios y listas.

Curso Propedútico de Python para Launch X - Innovacción Virtual.

Material desarrollado con base en los contenidos de MSLearn y la metáfora de LaunchX, traducción e implementación por: Fernanda Ochoa - Learning Producer de LaunchX.

Redes:
* GitHub: [FernandaOchoa](https://github.com/FernandaOchoa)
* Twitter: [@imonsh](https://twitter.com/imonsh)
* Instagram: [fherz8a](https://www.instagram.com/fherz8a/)