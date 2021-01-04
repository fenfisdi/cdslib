# Guía de desarrollo 
  ## Introducción
Este documento brinda las convenciones de escritura de código Python para todos los módulos y submódulos de la librería CDSLib. El documento intenta cubrir la mayor cantidad de casos posibles, sin embargo, el documento es un documento vivo y escalable a través del tiempo.

 ## Módulos
   #### Importaciones
- Las importaciones se deben de hacer siempre al inicio de cada módulo, y en líneas separadas.
    NO:
      import os, copy, time, functools
    SI:
      import os
      import copy
      import time
      import functools
- Las importaciones se deben dar en el siguiente orden:
    1.	Importaciones de la librería estándar
    2.	Importaciones de librerías de terceros
    3.	Importaciones locales de la aplicación / librería
    
- Al final del bloque de importaciones se deben dejar 2 líneas en blanco:
    import os
    import copy
    import time
    import functools
    import numpy as np
    import pandas as pd
    #Linea en blanco
    #Linea en blanco
    class Clase:

- Para las importaciones de módulos locales que se encuentren dentro de carpetas, se de utilizar su ruta relativa (la definida en el archivo __init__.py de cada carpeta).

#### Nombramiento
  Los módulos deben tener nombres cortos y en singular, con un estilo pascal case para mejorar la legibilidad.

#### Caracteres por linea
  El proyecto CDSLib se rige por lo establecido en el pep8 sobre la longitud de caracteres por linea.

#### Tamaño
  Cada modulo debe tener un tamaño máximo de 250 líneas de Código. 
  El modulo debe contener a lo sumo una clase, en caso de ser un módulo de funciones, pueden ser incluidos N funciones, sin superar las 250 líneas de código en total

## Variables
#### Locales
  Las variables locales deben ir al inicio de cada ámbito o scope, en caso de contener dos o más palabras deben ser separadas por underscore (como lo dicta el pep8), sus nombres deben ser claros e intuitivos.
#### Globales
  No se deben usar variables globales en el proyecto, en caso de ser necesarias se considerar el uso de un archivo de parámetros o variables de ambiente

## Espacios en blanco en expresiones y sentencias 
  Los espacios en blanco pueden ayudar a una mejor lectura del código, sin embargo, deben ser usados de manera adecuada, a continuación, se muestran diferentes casos para el uso de espacios en blanco:
  - Inmediatamente dentro de paréntesis, corchetes o llaves:
    NO:
      spam( ham[ 1 ], { eggs: 2 } )
    SI:
      spam(ham[1], {eggs: 2})
  - Inmediatamente antes de una coma, un punto y coma o dos puntos:
    NO:
      if x == 4 : 
        print (x)
    SI:
      if x == 4: 
        print (x)

  - Inmediatamente antes del paréntesis que comienza la lista de argumentos en la llamada a una función:
    NO:
      Spam (1)
    SI:
      Spam(1)
  - Inmediatamente antes de un corchete que empieza una indexación:
    NO:
      dict ['key'] = list [index]
    SI:
      dict['key'] = list[index]
  - Más de un espacio alrededor de un operador de asignación (u otro) para alinearlo con otro:
    NO:
      x             = 1
      y             = 2
      long_variable = 3
    SI:
      x = 1
      y = 2
      long_variable = 3
## Clases
#### Nombramiento
Debe describir la función de clase, debe ser en singular y en convención pascal case.
	Las propiedades de la clase deben ser nombradas según convención del pep8 y ser claras. Se debe poder intuir cuál es su rol dentro de la clase
#### Tamaño
 La clase no debe superar las 250 líneas de código
#### Documentación
 Todas las clases deben llevar su respectiva documentación, al igual que cada una de sus funciones

## Métodos y funciones
  Los métodos o funciones deben ser precisas y tener funcionales muy específicas.
  Dentro de las funciones no deben ser incluidas llamados a funciones que hayan sido creadas después de la función donde se ejecuta el llamado.
#### Tamaño
  No deben exceder las 20 líneas de código, en caso de que se superen las 20 líneas, es necesario crear nuevas funciones para acotar el alcance de cada una de ellas o buscar técnicas de refactorización 
#### Parámetros
  El número de parámetros de cada función deben ser máximo 5, en caso de que exceda los 5 parámetros, se deben pasar como parámetro entidades cuyas propiedades sean los parámetros iniciales o buscar técnicas de refactorización.
  El nombre de los parámetros debe ser de la misma forma que las variables.
#### Nombramiento
  Deben ser nombrados de manera que se entienda su función y/o comportamiento, en letras minúsculas y con guiones bajos (underscores) si así lo requiere para facilitar su entendimiento
#### Documentación
  Todas las funciones o métodos deben estar debidamente documentadas, especificando el tipo de los parámetros, su funcionalidad y su retorno (si lo tiene). 

