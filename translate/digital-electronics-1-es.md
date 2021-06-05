## Electrónica digital

###### Parte 1 - Circuitos lógicos, puertas, biestables

#### Estas diapositivas: [slides.cuban.tech/digital-electronics-1.html](http://slides.cuban.tech/digital-electronics-1.html)

---

### Información Wifi

Red: cubantech

Contraseña: meet-ups

---

---

# Enorme gracias a nuestro anfitrión

---

## Contorno

- Lógica booleana, puertas, circuitos lógicos.
- Multiplexores
- ALU
- Biestable
- Manos a la obra! Construye un cierre SR

---

# ¡Comencemos!

---

## Nuestro hardware

[![](img/hardware-kit-closed.jpg)](http://www.seeedstudio.com/depot/ARDX-The-starter-kit-for-Arduino-p-1153.html)

---

## Nuestro hardware

[![](img/hardware-kit-open.jpg)](http://www.seeedstudio.com/depot/ARDX-The-starter-kit-for-Arduino-p-1153.html)

---

## A los kits les puede faltar equipo

---

Si tiene problemas para encontrar un componente, háganoslo saber y le conseguiremos un reemplazo.

---

## ¿No funciona?

## ¡Probablemente hardware!

---

## Componentes que estamos cubriendo

- Puertas lógicas
- Multiplexores
- ALU
- Bistables

---

Siéntase libre de seleccionar los componentes que más le gusten y completar los retos que más le interesen.

---

# Empezando

## Lógica booleana

- Operación lógica usando 1's y 0's
- Operaciones de unión, intersección y complemento

---

## Grupos de circuitos lógicos

- CLC (Circuito Lógico Combinado)
  - Asíncrono
- SSC (Circuito Síncrono Secuencial)
  - Síncrono, generalmente con una sola señal de reloj

---

# Puertas Basicas

---

## Buffers (regulador)

![](img/buffer.jpg)

---

## Puerta NOT

![](img/not-gate.jpg)

- La versión negada de **_a_** is **_/a_**

---

## Puerta AND

![](img/and-gate.jpg)

- **_a_** AND **_b_** = **_a_** \* **_b_**

--

## Propiedades AND

- **a** \* **a** = **a**
- **a** \* **1** = **a**
- **a** \* **/a** = **0**
- **a** \* **0** = **0**

---

## Puerta OR

![](img/or-gate.jpg)

- **_a_** OR **_b_** = **_a_** + **_b_**

--

## Propiedades OR

- **a** + **a** = **a**
- **a** + **0** = **a**
- **a** + **1** = **1**
- **a** + **/a** = **1**

---

## Puerta XOR

![](img/xor-gate.jpg)

- **_a_** XOR **_b_** = **_a_** &#xA69A; **_b_**

--

## Propiedades XOR

- **a** &#xA69A; **a** = **0**
- **a** &#xA69A; **/a** = **1**
- **a** &#xA69A; **0** = **a**
- **a** &#xA69A; **1** = **/a**

---

## Puertas universales

![](img/universal-gates.jpg)

- **_a_** NAND **_b_** = /(**_a_** \* **_b_**)
- **_a_** NOR **_b_** = /(**_a_** + **_b_**)

--

## ¿Por qué son universales?

- Las puertas universales pueden sustituir a TODAS las demás puertas
- Puede construir cualquier circuito digital usando sólo puertas NAND o NOR

--

## Las leyes de De Morgan

- **/**(**a** + **b**) = **/a** \* **/b**
- **/**(**a** \* **b**) = **/a** + **/b**

---

## Creando la verdad de la mesa a partir de un circuito

--

![](img/digital-example-1.jpg)

--

![](img/digital-example-2.jpg)

--

- x = a \* b

- y = /(b + c)

--

- S = x &#xA69A; y

- S = (a \* b) &#xA69A; /(b + c)

--

![](img/digital-example-3.jpg)

--

![](img/digital-example-4.jpg)

---

## Construyendo el circuito desde la tabla de verdad

![](img/ejemplo-digital-4.jpg)

--

### Expresiones canónicas

- Suma de productos o producto de sumas
- Cada término de la expresión es un término canónico
- Un término canónico siempre contiene **_TODOS_** las entradas (o las entradas negadas) exactamente una vez

--

## Expresiones canónicas (ejemplo)

- A, B y C: entradas
- S = (A + B + C) \* (/A + B + /C)
- S = (A \* /B \* /C) + (/A \* /B \* C) + (A \* /B \* C)

--

## Cómo extraer la expresión canónica

- Decidir si la expresión canónica será:
  - una suma de productos
  - un producto de sumas

--

## Una suma de productos (minterm)

- Seleccionar todas las combinaciones con S = 1
- Si el valor de una entrada en esa combinación es igual a S, entonces aparecerá sin cambios en el término canónico.
- Si es diferente a S, entonces ponemos la versión negada de esa entrada.

--

## Una suma de productos (ejemplo)

![](img/digital-example-4.jpg)

--

## Una suma de productos (ejemplo)

### Las combinaciones de ABC con S = 1

- 0 0 0
- 1 0 0
- 1 1 0
- 1 1 1

--

## Una suma de productos (ejemplo)

Tomemos la combinación **1 0 0**

- A = 1 (es igual a S => sin cambios)
- B = 0 (no es igual a S => negado)
- C = 0 (no es igual a S => negado)

Así será el término canónico: **A \* /B \* /C**

--

## Una suma de productos (ejemplo)

Para la combinación **1 1 0** el término canónico es: **A \* B \* /C**

- La suma de los productos canónicos de la tabla es:
  - (**/A \* /B \* /C**) + (**A \* /B \* /C**) + (**A \* B \* /C**) + (**A \* B \* C**)

--

## El circuito de la expresión canónica:

![](img/ejemplo-digital-5.jpg)

--

## Un producto de sumas (maxterm)

- Similar al minterm pero tomamos S = 0
- El producto de las sumas canónicas para la mesa es:
  - (A + B + /C) \* (A + /B + C) \* (A + /B + /C) \* (/A + B + /C)

--

## ¿Cómo decidir si usar expresiones maxterm o minterm?

- Si la tabla verdadero-falso contiene más de 1 que de 0 en S, utilice maxterm
- De lo contrario, use minterm
- El circuito obtenido por la vía inversa, es también válido pero mayor

--

# Usando sólo puertas universales

--

## Tomemos el último circuito

![](img/ejemplo-digital-5.jpg)

--

## Añade una pequeña modificación

![](img/ejemplo-digital-8.jpg)

--

## De aquí....

- NOT se puede obtener de la propiedad:
  - **/a** = **/(a + a)**
- Usando las leyes de De Morgan....

--

## Obtenemos esto....

![](img/ejemplo-digital-9.jpg)

---

## Desafío #1

### Vamos a crear un sumador de 1-bits (medio sumador)

- A + B

![](img/ejemplo-digital-7.jpg)

---

## Multiplexores

- Un multiplexor es un _Selector de canales_
- Seleccione una de las múltiples entradas y póngala en la salida
- Con las entradas de selección _n_ se pueden direccionar hasta 2<sup>n</sup> señales.

![](img/ejemplo-digital-6.jpg)

--

## Multiplexor de 1 bit con 1 entrada de selección

![](img/ejemplo-digital-10.jpg)

---

## ALU (Unidad Aritmética-Lógica)

- Es un circuito que le permite _seleccionar_ entre operaciones
- La ALU puede realizar operaciones aritméticas o lógicas

--

## ALU

![](img/ALU.jpg)

--

## ALU de 1 bit

- Realiza **XOR**, **AND**, **OR** y **SUMA**.

![](img/1-bit-ALU.jpg)

--

## Visión general moderna

- Intel Core i9 utiliza 7 ALU por núcleo
- Cada ALU es diferente dependiendo del uso
- Algunas ALUs sólo realizan operaciones lógicas y operaciones aritméticas simples.
- Algunas otras ALUs realizan operaciones complejas como producto o división.
- Utilizan la microarquitectura Skylake con soporte para hasta AVX-512
- Las ALUs se utilizan no sólo para variables sino también para calcular el direccionamiento de la memoria.

---

## Bistables

- Un biestable es un circuito que puede estar en uno de los dos estados durante un tiempo indefinido.
- Puede **_almacenar_** información

---

## Cierres

- Biestable asíncrono
- Tipo SR
- Tipo D

--

## Cierre SR

![](img/sr-latch.jpg)

--

## Cierre D

![](img/d-latch.jpg)

--

## Construyendo un pestillo SR

![](img/4000_Pinout.jpg)

--

## Esquema de circuito

- Paso 1 (Suministro de energía)

![](img/sr-latch-fr1.jpg)

--

## Esquema de circuito

- Paso 2 (Conexión de las entradas)

![](img/sr-latch-fr2.jpg)

--

## Esquema de circuito

- Paso 3 (retroalimentación del pestillo SR)

![](img/sr-latch-fr3.jpg)

--

## Esquema de circuito

- Paso 4 (Conexión de los LEDs)

![](img/sr-latch-fr4.jpg)

--

## Esquema de circuito

- Resultado

![](img/sr-latch-fr5.jpg)

---

## Flip-Flop

- Biestable síncrono
- Tipo D
- Tipo JK
- Tipo T

--

## Flip-Flop tipo D

- Se basa en el pestillo D
- La entrada **Enable** se sustituye por un detector de flanco ascendente (entrada de reloj).

--

## Flip-Flop tipo D

![](img/d-flip-flip-flip.jpg)

---

## Aplicaciones de las chancletas

- Registros
- Registros de cambio
- Diseño de sistemas síncronos (utilizando la técnica de máquinas de estado finito)
- Almacenamiento
- Mostradores
- Microprocesadores

---

## Próximos eventos

- Electrónica digital (parte 2)
  - Mapa de Karnaugh
  - Máquina de estado finito

---

## Conclusiones

- Gracias por venir!
