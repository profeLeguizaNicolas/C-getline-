<div style="text-align:justify">

# `cin` en C++.

`cin` es un objeto que pertenece a la librería `<iostream>` y significa *Console Input* (entrada por consola). Se utiliza para leer datos ingresados por el usuario desde el teclado y almacenarlos en variables.

El operador que se utiliza junto con `cin` es `>>`, que se conoce como `operador de extracción`.

**Ejemplo básico de uso:**

```C++
int numero;
cout << "Ingrese un número: ";
cin >> numero;
```
Cuando se ejecuta este código, el programa esperará que el usuario escriba un valor y presione Enter. El valor ingresado se almacena en la variable `numero`.

## Características importantes de `cin`:

- `cin` detiene la lectura cuando encuentra un espacio o un salto de línea `\n`.

- No captura espacios. Por ejemplo, si se ingresa `Juan Perez`, `cin >> nombre` solo guardará `Juan` en la variable.

- Puede dejar en el `buffer` de entrada caracteres pendientes, como el `\n` después de presionar Enter, lo que puede causar problemas si después se utiliza otra función de entrada como `getline`.

## `getline` en C++.

`getline` es una función que permite leer una línea completa de texto, incluyendo espacios, desde el teclado.

En C++ existen dos versiones principales de `getline`:

1. Para arreglos de caracteres `char[]`.

```C++
cin.getline(nombre, tamaño);
```
Esta función lee caracteres hasta que encuentra un salto de línea `\n` o hasta que se llena el arreglo ( con tamaño - 1). Luego elimina el `\n` y finaliza la cadena con `\0`.

2. Para objetos `string`:

```C++
string texto;
getline(cin,  texto);
```

Esta es una versión más moderna y flexible. Permite leer líneas completas y almacena el texto en un objeto `string`. 

## Características importantes de `getline`:

- Captura toda la línea, incluyendo espacios, hasta que encuentra `\n`.
- Elimina automáticamente el salto de de línea `\n` del buffer.
- Es útil para ingresar nombres completos, frases o textos largos.
- Puede recibir un delimitador opcional difernete a `\n`. Ejemplo:

```C++
cin.getline(nombre, 100, '.');
```
Este código leerá caracteres hasta encontrar un punto `.` en lugar del salto de línea.

## Diferencias entre `cin` y `getline`.

<div style="text-align: center">

|        cin >>                                 |                     getline                          |
|-----------------------------------------------|------------------------------------------------------|        
| Lee hasta el primer espacio o salto de línea. | Lee hasta encontrar un salto de línea o delimitador. |
| No lee espacios.                              | Sí lee espacios.                                     |
| Útil para: Números, palabras cortas           | Útil para: frases, nombres completos.                |
| Puede dejar \n en el buffer.                  | Limpia el \n automaticamente.                        |

</div>

<br>
<hr>
<br>

**Ejercicio 1**

Crear un programa que lea una frase completa desde teclado usando getline y luego la muestre letra por letra en consola (una por línea).

<div style="text-align:center">

<video src="Videos/video1.mp4" controls=""> </video>

</div>

<hr>

**Ejercicio 2**

Escribir un programa que use getline para leer una frase con espacios. Luego contar cuántas palabras tiene la frase (considerando que las palabras están separadas por espacios).

<div style="text-align: center">

<video src="Videos/video2.mp4" controls=""> </video>

</div>

<hr>

**Ejercicio 3**

Lee una frase y muestra cada palabra en una línea nueva. hazlo con un ciclo y detección de espacios.

<div style="text-align: center">

<video src="Videos/video3.mp4" controls=""> </video>

</div>

<hr>

**Ejercicio 4**

Lee una frase y luego imprímela al revés, carácter por carácter.

<div style="text-align: center">

<video src="Videos/video4.mp4" controls=""> </video>

</div>

<hr>

**Ejercicio 5**

Lee una frase y luego crea una nueva cadena donde se eliminan todos los espacios.

<div style="text-align: center">

<video src="Videos/video5.mp4" controls=""> </video>

</div>

**Ayuda:**

## Tabla: Cómo reconocer espacio, salto de línea y fin de cadena

<div style="text-align: center">

| Concepto       | Carácter | Valor numérico | ¿Cómo lo reconozco?                                     |
|:---------------|:---------|:---------------|:--------------------------------------------------------|
| Espacio        | `' '`     | 32              | Es un espacio simple, como entre dos palabras.           |
| Salto de línea | `'\n'`    | 10              | Es cuando el cursor baja una línea (Enter).              |
| Fin de cadena  | `'\0'`    | 0               | Termina una cadena de texto. No se ve, es interno.       |

</div>

</div>