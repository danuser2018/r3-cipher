[![CC BY 4.0][cc-by-shield]][cc-by]
# Cifrado R3
|   | **0** | **1** | **2** |   |
| :------------: | :------------: | :------------: | :------------: | :------------: |
| **00** | A | B | C | **1** |
| **01** | D | E | F | **2** |
| **02** | G | H | I | **3** |
| **10** | J | K | L | **4** |
| **11** | M | N | Ñ | **5** |
| **12** | O | P | Q | **6** |
| **20** | R | S | T | **7** |
| **21** | U | V | W | **8** |
| **22** | X | Y | Z | **9** |

## Cifrado
### Paso 1
Cada letra se representa por un número de tres dígitos, el primero correspondiente a la columna, y los dos últimos correspondientes a la fila.

A: 000
B: 100
C: 200
D: 201
.
.
.
Z: 222

### Paso 2
Cada número de tres dígitos se codifica de la siguiente forma: 
1. Se toman los dos primeros dígitos y se apunta el número de fila
2. Para codificar el último dígito se toman una letra al azar de la columna que coincida con dicho dígito.

Así, por ejemplo. La letra P (112) se podría codificar como 5L. Ya que 11 es la fila 5 y L es una letra al azar de la columna del 2. También valdría 5Q, o 5T, cualquier letra de la columna 2.

### Ejemplo
El texto HOLA MUNDO se podría cifrar como: 4I2Z8M1U 2B3E5S1F2W

| H | O | L | A |   | M | U | N | D | O |
| :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | :------------: |
| 102 | 012 | 210 | 000 |   | 011 | 021  | 111 | 001 | 012 |
| 4I | 2Z | 8M | 1U |  | 2B | 3E | 5S | 1F | 2W |

## Descifrado
### Paso 1
Consiste en obtener los tres dígitos que codifican cada letra
1. Separamos los caracteres del texto cifrado de dos en dos (el primero será un número, el segundo una letra).
2. Para cada conjunto de 2 caracteres: Tomamos el primero (el número). Traducimos la fila a los dos primeros dígitos.
3. El segundo carácter, la letra se traduce por el dígito que representa esa columna. Así, 4I se traduce en 102 (10 son los dígitos de la fila 4) y 2 es la columna donde está I.

### Paso 2
Consiste en traducir cada número de 3 dígitos en su correspondiente letra:
1. El primer dígito determina la columna
2. Los dos últimos dígitos, la fila.

Así, 102 se traduce por H.

### Ejemplo
El texto 4I2Z8M1U 2B3E5S1F2W se descifra como: HOLA MUNDO 

| 4I | 2Z | 8M | 1U |  | 2B | 3E | 5S | 1F | 2W |
| :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | :------------: | :------------: |
| 102 | 012 | 210 | 000 |   | 011 | 021  | 111 | 001 | 012 |
| H | O | L | A |   | M | U | N | D | O |

## Añadiendo una clave
Para hacer más robusto el cifrado se puede añadir una clave. Para ello basta con seleccionar una palabra clave que no contenga letras duplicadas (si las contiene se eliminan los duplicados) y se construye la tabla escribiendo la palabra primero, y el resto del alfabeto a continuación, comenzando por la siguiente letra del alfabeto después de la clave

Por ejemplo, si la clave es MURCIELAGO

la tabla quedaría:

|   | **0** | **1** | **2** |   |
| :------------: | :------------: | :------------: | :------------: | :------------: |
| **00** | M | U | R | **1** |
| **01** | C | I | E | **2** |
| **02** | L | A | G | **3** |
| **10** | O | P | Q | **4** |
| **11** | S | T | V | **5** |
| **12** | W | X | Y | **6** |
| **20** | Z | B | D | **7** |
| **21** | F | H | J | **8** |
| **22** | K | N | Ñ | **9** |

El cifrado y el descifrado se realizan exactamente de la misma forma que se realizaban antes.

# Créditos
- A [Santiago Soler](https://github.com/santisoler) por su [repo para añadir licencias de creative commons a proyectos de github](https://github.com/santisoler/cc-licenses)

# Licencia
Esta obra está bajo una licencia de [Creative Commons Reconocimiento 4.0 Internacional][cc-by]

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/deed.es
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg
