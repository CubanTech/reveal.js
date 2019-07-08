ml](http://slides.cuban.tech/nodebots.html)

----------------

### Información Wifi

Red: cubantech

Contraseña: meet-ups

----------------

### Si aún no lo has hecho, instala Nodo

##### Subtítulos por aRGENTeaM https://nodejs.org/en/download/

######[Nodo de Descarga desde LAN](ftp://qnap01.local/Public/soft/nodejs)

---

- Este taller se basa en gran medida en un taller de[NY-Javascript](http://www.meetup.com/NY-Javascript) (ver[bit.ly/nyjs-nodebots](http://bit.ly/nyjs-nodebots))
- ... que se basa en gran medida en un taller de[Francis Gulotta](https://twitter.com/reconbot) y[Rick Waldron](https://twitter.com/rwaldron)
- Puede encontrar las diapositivas para ese taller en[gul.ly/3tjj](http://gul.ly/3tjj)
- Puedes inscribirte en uno de sus talleres en la página[Nodebots NYC Meetup page](http://www.meetup.com/nodebots/)

---

## Nuestras pautas de la comunidad

[Sé excelente el uno con el otro] (https://github.com/nodeschool/havana/blob/master/Code_of_Conduct.md)

---

Próximos Eventos CubanTech

- [CubanTech meetups](http://meetup.cuban.tech)
- [Encuentros en Cuba](http://docker.cuban.tech)
- [Blockstack Cuba meetups](http://blockstack.cuban.tech)
- [SciPyLA 2019](http://conf.scipyla.org)

---

# Enorme gracias a nuestro anfitrión

---

## ¿Qué son los Nodebots?

![](img/johnny-five.png)

---

## JavaScript + Robots = Nodebots

---

# ¡Comencemos!

---

## Our hardware

[![](img/hardware-kit-closed.jpg)](http://www.seeedstudio.com/depot/ARDX-The-starter-kit-for-Arduino-p-1153.html)

---

## Our hardware

[![](img/hardware-kit-open.jpg)](http://www.seeedstudio.com/depot/ARDX-The-starter-kit-for-Arduino-p-1153.html)

---

## A los kits les puede faltar equipo

------------

Si tiene problemas para encontrar un componente, háganoslo saber y le conseguiremos un reemplazo.

---

## ¿No funciona?

## ¡Probablemente hardware!

---

## Componentes que estamos cubriendo

- LEDs (diodos emisores de luz)
- Botones
- Servos

---

Siéntase libre de seleccionar los componentes que más le gusten y completar los retos que más le interesen.

---

# Empezando

--

## Instalar un nodo si aún no lo ha hecho

Nodo de descarga de Internet](https://nodejs.org/en/download/)

Nodo de descarga desde LAN](ftp://qnap01.local/Public/soft/nodejs)

--

## Crear directorio de proyectos

```sh
mkdir nodebots
cd nodebots
```

--

## Instala Johnny Five

```sh
npm instalar johnny-five
```

---

# Empezando

.... con ....

![](img/docker_logo.png)

--

TODO : Instalación del Docker de documentos

---

## Firmata estándar

- Permite a Johnny-Five comunicarse con el Arduino a través de USB
- La mayoría de los Arduinos ya tienen instalados los Firmatas Estándar de talleres anteriores
- Vamos a comprobar que tu Arduino ya tiene instalado el Firmato Estándar!

---

## Conecta el arduino

![](img/connecting-arduino.jpg)

---

Crear el fichero

1. Ve a tu directorio de nodebots
2. Cree un archivo llamado test.js
3. Copie el código que aparece a continuación y guarde

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {

  var led = nuevo five.Led(13);

  led.blink(500);
});
```

---

Ejecute el código

```sh
nodo test.js
```

---

## Este LED debería estar parpadeando cada .5 segundos

![](img/built-in-led.png)

---

Si funciona, ¡continúe! &rarr;

------------

Si no es así, pulsa &darr; para obtener instrucciones sobre cómo flashear tu Arduino con Firmata Estándar

--


## Cómo flashear tu Arduino con Firmata estándar (Plus)

1. Descargue el[Arduino IDE](https://www.arduino.cc/en/main/software)
2. Asegúrate de que tu Arduino está conectado vía USB
3. Abra el IDE de Arduino
4. Seleccione: Archivo > Ejemplos > Firmatos > StandardFirmataPlus
5. Seleccione: Herramientas > Tablero > Arduino/Genuino Uno
6. Seleccione: Herramientas > Puerto > <tu Arduino>``Arduino
7. Haga clic en el botón Upload![](img/arduino-ide-upload-button.png)
8. Vuelva a intentar hacer que el LED parpadee

---

## Componentes que estamos cubriendo

- LEDs (diodos emisores de luz) <span style="color:yellow"> LEDs (diodos emisores de luz) </span>
- Botones
- Servos

---

## LEDs

#### <span class="redled">LIGHT</span> <span class="green-led">EMITTING</span> <span class="blue-led">DIODES</span>

![](img/leds.jpg)

---

## Pines LED de identificación

- La clavija larga es positiva (y se pone en marcha)
- El pin corto es negativo (y va a tierra)

![](img/led-pin-diagram.png)

---

## Build This

![](img/arduino-led.png)

---

Guarde esto en un archivo y ejecútelo

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {

  var led = nuevo five.Led(11);

  // "parpadea" el led en períodos de fase de encendido y apagado de 500ms.
  led.blink(500);
});
```
`nodo blinky.js`s

---

## Si tiene éxito, deberías ver esto

![](img/blinking-led.gif)

---

## Cambio de la frecuencia de parpadeo

- Probablemente notó que la luz parpadea cada 0,5 segundos.
- Cambie el código para que parpadee a una velocidad diferente y luego vuelva a ejecutarlo para asegurarse de que funciona.
- Si está atascado, presione &darr; para ver una solución potencial

--

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {

  var led = nuevo five.Led(11);

  // "parpadea" el led en períodos de fase de encendido y apagado de 3.000 ms.
  led.blink(3000);
});
```

`nodo blinky.js`s

---

## The REPL

- Significa Read Evaluate Print Loop (Leer, Evaluar, Imprimir)
- Nos permite escribir el código en nuestro terminal y ver cómo afecta a nuestros robots.

---

## Escribe y ejecuta esto. Luego, continúe con la siguiente diapositiva.

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {
  var led = nuevo five.Led(11);

  esta.réplica.de.la.inyección({
    led: led
  });
});
```

`node led-boss.js`

---

## Escriba estos comandos en el REPL y observe cómo cambia el LED

```
> led.on();

> led.off();

> led.blink();

> led.stop();

> led.pulse();
```

---

## Inyección REPL

La razón por la que podemos acceder al objeto led en el REPL es por este bit de código en el ejemplo anterior. Expone el objeto led a nuestra sesión REPL.

```js
esta.réplica.de.la.inyección({
  led: led
});
```

---

## Paneras: Cableado sin soldadura

#### Los Panes nos permiten cablear rápidamente los componentes para hacer prototipos

![](img/breadboard.small.png)

---

## Paneras: Conexiones eléctricas

- Aquí puedes ver cómo se conectan las diferentes filas y columnas.
- Si no está claro, no dudes en buscar en Google o pedirle a un voluntario que te lo explique.

![](img/breadboard-diagram.small.jpg)

## Usa tu protoboard y un par de cables (el color no importa) para construir esto

![](img/arduino-led-breadboard.png)

---

Ahora ejecute uno de sus programas anteriores y asegúrese de que el LED siga parpadeando

---


## Desafíos del LED

Ahora que tiene los fundamentos de los LEDs, puede pasar al siguiente componente o trabajar en algunos desafíos de los LEDs.

- Pulse &rarr; para pasar al siguiente componente
- Pulse &darr; para desplazarse por los desafíos de los LEDs

--

## Desafíos del LED

*¡Intenta resolverlos tú mismo antes de mirar la solución!*

Pulse &darr; para desplazarse por los siguientes retos (y posibles soluciones)

1. Múltiples luces
2. Luces navideñas
3. Contador binario

--

### 1. Múltiples luces

Haga que 2 (o más) luces se alternen parpadeando

![](img/alternate-blinking.gif)

--

### Solución Potencial de Múltiples Luces - Hardware

![](img/alternate-blinking-hardware.png)

--

### Solución Potencial de Múltiples Luces - Código

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {

  var led1 = nuevo five.Led(10);
  var led2 = nuevo five.Led(11);
  var flag = false;

  setInterval(function() {
    si (bandera) {
      led1.on();
      led2.off();
    } más {
      led1.off();
      led2.on();
    }

    flag =! flag;
  }, 500);
});
```

--

### 2. Luces navideñas

#### Haz que un LED (o varios LEDs) pasen por diferentes configuraciones, como hacen algunas luces navideñas. Debería cambiar el ajuste cada pocos segundos. A continuación se muestran algunos ejemplos de configuración. Puede ver un ejemplo en la siguiente diapositiva.

- Apagado
- Sólido
- Parpadeando
- Pulsos (desvanecimiento hacia adentro y hacia afuera)
- Diferentes velocidades de parpadeo, pulsación o alternancia
- Alternando qué luces están encendidas

--

### 2. Luces navideñas

![](img/holiday-lights.gif)

--

### Potencial solución de luces navideñas - Hardware

![](img/holiday-lights-hardware.gif)

--

### Potencial solución para las luces navideñas - Código

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {
  var led = nuevo five.Led(11);
  var = 0;

  setInterval(function() {
    led.stop(); // Si llamamos pulso, tenemos que pararlo
    interruptor (ajuste) {
      caso 0:
        pulso.led();
        descanso;
      caso 1:
        led.off();
        descanso;
      caso 2:
        led.on();
        descanso;
    }
    ajuste = (ajuste + 1) % 3;
  }, 3000);
});
```

--


### 2. Luces navideñas (bonos)

1. Exponer una función a la REPL que le permite cambiar a la siguiente configuración desde la REPL
2. Añada un botón que, al pulsarlo, pase a la siguiente configuración (Nota: debe completar las diapositivas del componente de botones antes de intentarlo).

--

### Potencial solución de Bonus 1 para luces navideñas - Hardware

![](img/holiday-lights-hardware.gif)

--

### Posible solución de bonificación por luces navideñas 1 - Código

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {
  var led = nuevo five.Led(11);
  var = 0;

  function changeSetting() {
    led.stop(); // Si llamamos pulso, tenemos que pararlo
    interruptor (ajuste) {
      caso 0:
        pulso.led();
        descanso;
      caso 1:
        led.off();
        descanso;
      caso 2:
        led.on();
        descanso;
    }
    ajuste = (ajuste + 1) % 3;
  }

  esta.réplica.de.la.inyección({
    cs: changeSetting // Ahora podemos llamar a cs() desde el REPL
  });
});
```

--

### Potencial solución de Bonus 2 para luces navideñas

¡Estás por tu cuenta en esto!

--

### 3. Contador binario

Usando 3 LEDs, cuente de 0 a 7 en binario como se muestra a continuación. On representa 1 y off repesentes 0.

![](img/binary-counter.gif)

--

### Solución de contador binario potencial - Hardware

![](img/binary-counter-hardware.png)

--

### Solución de contador binaria potencial (alt 1) - Código

```js

var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {
  var led1 = nuevo five.Led(9);
  var led2 = nuevo five.Led(10);
  var led3 = nuevo five.Led(11);
  var num = 0;

  setInterval(function() {
    var binary = (num).toString(2);

    binario.slice(-1) === "1" ? led1.on() : led1.off();
    binario.slice(-2, -1) === "1" ? led2.on() : led2.off();
    binario.slice(-3, -2) === "1" ? led3.on() : led3.off();

    num = (num + 1) % 8;
  }, 1000);
});
```

--

### Solución de contador binaria potencial (alt 2) - Código

```js

var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {
  var =[nuevo cinco.Led(9), nuevo cinco.Led(10), nuevo cinco.Led(11)];
  var num = 0;

  setInterval(function() {
    var mask = 1;

    para (var i = 0; i < longitud de los leds; ++i, máscara <<<= 1) {
      var led = led[i];
      num & mask? led.on() : led.off();
    }

    num = (num + 1) % 8;
  }, 1000);
});
```

--

### 3. Contador binario (Bono)

Permite al usuario introducir un número a través de la REPL y mostrarlo en binario en los LEDs.

--

### Solución potencial de bono de contador binario

¡Estás por tu cuenta en esto!

---

## Componentes que estamos cubriendo

- LEDs (diodos emisores de luz)
- style="color: amarillo">Botones </span>
- Servos

---

## Botones

![](img/buttons.jpg)

---

## Build This

![](img/button-hardware.png)

---

## Guarda esto en un archivo y ejecútalo

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {
  var = nuevos cinco botones(2);

  button.on("press", function() {
    console.log ("Botón pulsado!");
  });

  button.on("hold", function() {
    console.log ("Button Held!");
  });

  button.on("release", function() {
    console.log ("Botón liberado!");
  });
});
```

`node button.js`

---

Intente presionar, soltar y mantener presionado el botón

Debería ver alguna salida como esta en el REPL

```

>> Botón pulsado!
Botón liberado!
Botón pulsado!
Botón liberado!
Botón pulsado!
Botón retenido!
Botón retenido!
Botón liberado!
```

---

## ¡Añadamos un LED!

![](img/button-led-hardware.png)

---

## Guarda esto en un archivo y ejecútalo

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {
  var led = nuevo five.Led(11);
  var = nuevos cinco botones(2);

  button.on("press", function() {
    led.on();
  });

  button.on("hold", function() {
    led.blink(50);
  });

  button.on("release", function() {
    led.stop().off();
  });
});
```

`node button_led.js`

---

El LED debe encenderse al presionar, apagarse al soltarlo y parpadear al mantenerlo presionado.

---

## Desafíos de los botones

Ahora que tiene los conceptos básicos de los botones, puede pasar al siguiente componente o trabajar en algunos desafíos de botones.

- Pulse &rarr; para pasar al siguiente componente
- Presione &darr; para desplazarse por los desafíos del botón

--

## Desafíos de los botones

*¡Intenta resolverlos tú mismo antes de mirar la solución!*

Pulse &darr; para desplazarse por los siguientes retos (y posibles soluciones)

1. Interruptor de luz
2. Clave de acceso
3. Luces navideñas

--

### 1. Interruptor de luz

Haga que al presionar un botón alternativamente encienda y apague un LED

--

### Solución de interruptor de luz potencial - Hardware

![](img/light-switch-hardware.png)

--

### Solución de interruptor de luz potencial - Código

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {
  var led = nuevo five.Led(11);
  var = nuevos cinco botones(2);
  var on = false;

  button.on("press", function() {
    si (on) {
      led.off();
    } más {
      led.on();
    }

    on =! on;
  });
});
```

--

### 2. Clave de acceso

Dispone de 2 botones y 1 LED. Hágalo de manera que tenga que presionar los botones en cierto orden para encender el LED.

--

### Posible solución de código de acceso - Hardware

![](img/passcode-hardware.png)

--

### Posible solución de código de acceso - Código

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {
  var led = nuevo five.Led(11);
  var1 = nuevos cinco botones(2);
  var2 = nuevos cinco botones(4);

  var = "12112";
  var presses = "";

  botón1.on("press", function() {
    pulsa += "1";
    if (presses.indexOf(passcode) > -1) {
      led.on();
    }
  });

  button2.on("press", function() {
    pulsa += "2";
    if (presses.indexOf(passcode) > -1) {
      led.on();
    }
  });
});
```

--

### 3. Luces navideñas

#### Haz que un LED (o varios LEDs) pasen por diferentes configuraciones, como hacen algunas luces navideñas. Debe cambiar el ajuste cada vez que se pulsa el botón. A continuación se muestran algunos ejemplos de configuración.

- Apagado
- Sólido
- Parpadeando
- Pulsos (desvanecimiento hacia adentro y hacia afuera)
- Diferentes velocidades de parpadeo, pulsación o alternancia
- Alternando qué luces están encendidas

--

### Potencial solución para las luces navideñas

¡Estás por tu cuenta en esto!

---

## Componentes que estamos cubriendo

- LEDs (diodos emisores de luz)
- Botones
- estilo <span="color: amarillo"> Servos </span>

---

## <span class="spin">S</span><span class="spin">E</span><span class="spin">R</span><span class="spin">V</span><span class="spin">O</span><span class="spin">S</span>.

![](img/servo.jpg)

---

Toma tu servo y añádele uno de los adjuntos.

![](img/servo.jpg)

---

## Build This

![](img/servo-hardware.png)

---

## Guarda esto en un archivo y ejecútalo

```js

var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {

  var servo = nuevo cinco.Servo(11);

  esta.réplica.de.la.inyección({
    servo: servo
  });
});
```

`node servo.js`s

---

Escribe estos comandos en la REPL y observa cómo reacciona el servo

```js

> servo.to(10); // Mover a 10 grados

> servo.to(200); // Mover a 200 grados

> Valor de servoaccionamiento; // Obtener la posición actual

> servo.min();

> servo.max();

> Alcance de los servomotores

> servo.center();

> servo.sweep();
```

---

## Servo Challenges

Ahora que tienes los fundamentos de los servos, puedes pasar al siguiente componente o trabajar en algunos desafíos de los servos.

Pulse &rarr; para pasar al siguiente componente
Pulse &darr; para desplazarse por los desafíos de los servos

--

## Servo Challenges

*¡Intenta resolverlos tú mismo antes de mirar la solución!*

Pulse &darr; para desplazarse por los siguientes retos (y posibles soluciones)

1. Rociador
2. Flechas
3. Botón

--

### 1. Rociador

Haz que el servo gire de un lado a otro como si fuera un aspersor.

![](img/sprinkler.gif)

--

### Solución potencial de rociadores - Hardware

![](img/sprinkler-hardware.png)

--

### Solución potencial de rociadores - Código

```js
var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {

  var servo = nuevo cinco.Servo(11);
  var min = rango servo[0];
  var max = rango servo[1];
  var = min;

  función step() {
    servo.to(valor);
    valor = (valor + 45) % máx;
    setTimeout(paso, 500);
  }

  step();
});
```

--

### 2. Flechas

Haz que al presionar el botón de flecha izquierda gire el servo en una dirección y al presionar el botón de flecha derecha gire en la otra dirección.

![](img/servo-arrows.gif)

--

### Solución de Flechas Potenciales - Hardware

![](img/servo-arrows-hardware.png)

--

### Solución de flechas potenciales - Código

```js

var cinco = require("johnny-five");
var = require("keypress");
var board = nuevo five.Board();

board.on("ready", function() {

  var servo = nuevo cinco.Servo(11);

  process.stdin.on("pulsar tecla", función(ch, tecla) {
    if (tecla && key.name === "left") {
      servo.min();
    else if (key && key.name === "right") {
      servo.max();
    }
  });

  process.stdin.setRawMode(true);
  process.stdin.resume();
});
```

--

### 3. Botón

Haz que el servo barra mientras se mantiene pulsado un botón

![](img/servo-sweep.gif)

-- 

### Potencial Solución de Botón - Hardware

![](img/servo-sweep-hardware.png)

--

### Potencial Solución de Botón - Código

```js

var cinco = require("johnny-five");
var board = nuevo five.Board();

board.on("ready", function() {
  var servo = nuevo cinco.Servo(11);
  var = nuevos cinco botones(2);

  button.on("press", function() {
    servo.sweep();
  });

  button.on("release", function() {
    servo.stop();
  });
});
```

---

Uh oh oh! Nos quedamos sin toboganes! Siéntase libre de probar algunos de los otros componentes de su kit mientras nosotros añadimos más!

---

## Winding Up

- Gracias por venir!
- Nos encantaría conocer su opinión: [bit.ly/nodebots-feedback](http://bit.ly/nodebots-feedback)
- Por favor, guarde los kits (puede comprar los suyos propios[aquí](http://www.seeedstudio.com/depot/ARDX-The-starter-kit-for-Arduino-p-1153.html))
