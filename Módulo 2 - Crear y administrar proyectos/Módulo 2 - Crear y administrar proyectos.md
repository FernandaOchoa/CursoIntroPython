# Introducción

En este punto, has creado pequeños programas que utilizan las bibliotecas que vienen con la instalación de Python. Funcionan bien. Pero a medida que construyes programas más avanzados, debes hacerte una pregunta: ¿Cuánto de esta nueva funcionalidad escribo y cuánto ya está escrito que puedo usar en mis propios programas?

Como desarrollador, es probable que crees muchos programas en una sola máquina. Esos programas también se pueden usar en otras máquinas. Sin embargo, algunas de estas máquinas pueden tener versiones de Python instaladas que no son lo que espera. O bien, pueden tener bibliotecas instaladas que son de versión inferior o superior a las que necesita su programa.

Entonces, ¿Qué hacer? Debes encontrar una manera de que tu programa funcione de forma aislada, para que no moleste lo que está instalado en la máquina de destino. También debes asegurarte de que una máquina no deshabilite tu programa porque tiene instalada la versión incorrecta de Python o la versión de la biblioteca.

## Escenario: Construyamos un programa

A medida que tus habilidades crecen y comienzas a construir programas más avanzados, siempre deseas comenzar con un buen enfoque. Deseas pensar en el programa que compila como un proyecto, con el código distribuido en muchos archivos. Si es posible, también deseas utilizar bibliotecas que otros han escrito, para acelerar el tiempo de desarrollo.

## ¿Qué aprenderás?
Al final de este módulo, podrás:

* Crear un proyecto de Python.
* Desarrollar y ejecutar tu código de forma aislada en una máquina.
* Usar bibliotecas que otra persona haya escrito.
* Restaurar un proyecto a partir de una lista de dependencias.

## ¿Cuál es el objetivo principal?
Utilizar bibliotecas y planificar tu proyecto para crear programas Python que sean más avanzados.

### Trabajar con paquetes

La mayoría de los programas que escribas se basarán en código escrito por otros. Este código a menudo viene en forma de paquetes, que son módulos externos o bibliotecas que se incluyen en el proyecto. Al igual que con cualquier proyecto que requiera un conjunto de recursos, es importante considerar cómo te asegurarás de que los recursos adecuados estén disponibles para tu programa.

Un buen comienzo es aprender a administrar tu programa. Una forma de hacerlo es pensar en el programa como un proyecto. Python aborda esto mediante el uso de algo llamado entornos virtuales.

### ¿Qué es un entorno virtual?

Tienes una máquina de desarrollo. En esa máquina, es posible que tengas una versión de Python instalada o una versión de una biblioteca que quieras usar. ¿Qué sucede cuando mueves tu programa a una máquina que tiene una versión diferente de Python instalada o diferentes versiones de las bibliotecas de las que depende?

Una cosa que no deseas hacer es asumir que tu programa funcionará y que puede instalar la última versión de las bibliotecas de las que depende. Si haces eso, podrías terminar destruyendo la capacidad de los otros programas para funcionar en la máquina de destino. La solución es encontrar una manera de que tu aplicación funcione de forma aislada.

La solución de Python para estos problemas es un entorno virtual. Un entorno virtual es una copia autónoma de todo lo necesario para ejecutar el programa. Esto incluye el intérprete de Python y cualquier biblioteca que su programa necesite. Mediante el uso de un entorno virtual, puedes asegurarte de que tu programa tendrá acceso a las versiones y recursos correctos para ejecutarse correctamente.

El flujo de trabajo básico se ve así:

* Crear un entorno virtual que no afecte al resto de la máquina.
* Ingresar al entorno virtual, donde especifique la versión de Python y las bibliotecas que necesita.
* Desarrolla tu programa.

Crear un entorno virtual
Para crear un entorno virtual, llame al módulo. El módulo espera un nombre como argumento.venv

Sigue estos pasos:

Ve al directorio donde deseas guardar tu proyecto. (Documentos/TuFolderPreferido)

Utiliza el siguiente comando para llamar al módulo ``venv``. El comando difiere ligeramente dependiendo de tu sistema operativo.

En consola: 
``python3 -m venv env  ``

Donde: 
* python3: La versión de python a utilizar.
* venv: Llamada al módulo ``venv`` conocido como virtual environment.
* env: Nombre de nuestro entorno virtual.

En este punto, se crean algunos directorios:
```
/env
  /bin
  /include
  lib
```
Tu entorno necesita el directorio ``venv`` para realizar un seguimiento de detalles como qué versión de Python y qué bibliotecas está utilizando. No coloque los archivos de programa en el directorio ``venv``. Te sugerimos que coloques tus archivos en el directorio ``src``o algo similar. La estructura del proyecto podría verse así:
```
```