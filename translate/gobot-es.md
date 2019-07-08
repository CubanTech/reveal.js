# Taller de gobots

#### Estas diapositivas: [slides.cuban.tech/gobot.html](http://slides.cuban.tech/gobot.html)

----------------

### Información Wifi

Red: cubantech

Contraseña: meet-ups

----------------

### Si aún no lo has hecho, instala Go

- [Descargar Go](https://golang.com/)

- [Descargar Go desde LAN](ftp://qnap01.local/Public/soft/go)

## Nuestras pautas de la comunidad

[Ser excelente el uno con el otro](https://github.com/nodeschool/havana/blob/master/Code_of_Conduct.md)

---

Próximos Eventos CubanTech

- [CubanTech meetups](http://meetup.cuban.tech)
- [Encuentros en Cuba](http://docker.cuban.tech)
- [Blockstack Cuba meetups](http://blockstack.cuban.tech)
- [SciPyLA 2018](http://scipyla.org/conf/2018)
  * Universidad de Sancti Spiritus, 22-25 de noviembre de 2017.

---

# Enorme gracias a nuestro anfitrión

---

## ¿Qué son los gobots?

![](img/gobot.png)

---

## Golang + Robots = Gobots

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

## Instalar Go si aún no lo has hecho

[Descargar Go de Internet](https://golang.org/)

[Descargar Go de LAN](ftp://qnap01.local/Public/soft/go)

--

## Crear directorio de proyectos

```sh
mkdir gobots
cd gobots
```

--

## Instalar Gobot

```sh
go get -d -u gobot.io/x/gobot/....
```

---

# Empezando

## Firmata estándar

- Permite a Gobot comunicarse con el Arduino a través de USB
- La mayoría de los Arduinos ya tienen instalados los Firmatas Estándar de talleres anteriores
- Vamos a comprobar que tu Arduino ya tiene instalado el Firmata Estándar!

---

## Conecta el arduino

![](img/connecting-arduino.jpg)

---

Crear el fichero

1. Ve a tu directorio de gobots
2. Cree un archivo llamado test.go
3. Copie el código que aparece a continuación y guarde

```go
package main

import (
  "time"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/platforms/firmata"
)

func main() {

  firmataAdaptor := firmata.NewAdaptor("/dev/ttyACM0");
  led := gpio.NewLedDriver(firmataAdaptor, "13");

  work := func() {

    gobot.Every(1 * time.Second, func() {

      led.Toggle();

    });

  };

  robot := gobot.NewRobot("bot",
    []gobot.Connection{firmataAdaptor},
    []gobot.Device{led},
    work,
  );

  robot.Start();

}
```

---

Ejecute el código

```sh
go run test.go
```

---

## Este LED debería estar parpadeando cada 1 segundo

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
4. Seleccione: `Arhivo > Ejemplos > Firmata > StandardFirmataPlus`
5. Seleccione: `Herramientas > Placa > Arduino/Genuino Uno`
6. Seleccione: `Herramientas > Puerto > <tu Arduino>`
7. Haga clic en el botón Upload ![](img/arduino-ide-upload-button.png)
8. Vuelva a intentar hacer que el LED parpadee

---

## Componentes que estamos cubriendo

- <span style="color:yellow">LEDs (diodos emisores de luz)</span>
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

## Construya esto

![](img/arduino-led.png)

---

Guarde esto en un archivo y ejecútelo

```go
package main

import (
  "time"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/platforms/firmata"
)

func main() {

  firmataAdaptor := firmata.NewAdaptor("/dev/ttyACM0");
  led := gpio.NewLedDriver(firmataAdaptor, "11");

  work := func() {

    gobot.Every(500 * time.Millisecond, func() {

      led.Toggle();

    });

  };

  robot := gobot.NewRobot("bot",
    []gobot.Connection{firmataAdaptor},
    []gobot.Device{led},
    work,
  );

  robot.Start();

}
```
`node blinky.go`

---

## Si tiene éxito, deberías ver esto

![](img/blinking-led.gif)

---

## Cambio de la frecuencia de parpadeo

- Probablemente notó que la luz parpadea cada 0,5 segundos.
- Cambie el código para que parpadee a una velocidad diferente y luego vuelva a ejecutarlo para asegurarse de que funciona.
- Si está atascado, presione &darr; para ver una solución potencial

--

```go
package main

import (
  "time"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/platforms/firmata"
)

func main() {

  firmataAdaptor := firmata.NewAdaptor("/dev/ttyACM0");
  led := gpio.NewLedDriver(firmataAdaptor, "13");

  work := func() {

    gobot.Every(3 * time.Second, func() {

      led.Toggle();

    });

  };

  robot := gobot.NewRobot("bot",
    []gobot.Connection{firmataAdaptor},
    []gobot.Device{led},
    work,
  );

  robot.Start();

}
```

`node blinky.go`

---

## Paneles: Cableado sin soldadura

#### Los paneles nos permiten conectar rápidamente los componentes para hacer prototipos

![](img/breadboard.small.png)

---

## Paneles: Conexiones eléctricas

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
2. Contador binario

--

### 1. Múltiples luces

Haga que 2 (o más) luces se alternen parpadeando

![](img/alternate-blinking.gif)

--

### Solución Potencial de Múltiples Luces - Hardware

![](img/alternate-blinking-hardware.png)

--

### Solución Potencial de Múltiples Luces - Código

```go
package main

import (
  "time"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/platforms/firmata"
)

func main() {

  firmataAdaptor := firmata.NewAdaptor("/dev/ttyACM0");
  led1 := gpio.NewLedDriver(firmataAdaptor, "13");
  led2 := gpio.NewLedDriver(firmataAdaptor, "12");

  work := func() {

    first := true

    gobot.Every(1 * time.Second, func() {

      if first == true {
        led1.On();
        led2.Off();
        first = false;
      } else {
        led1.Off();
        led2.On();
        first = true
      }

    });

  };

  robot := gobot.NewRobot("bot",
    []gobot.Connection{firmataAdaptor},
    []gobot.Device{led1, led2},
    work,
  );

  robot.Start();

}
```

--

### Solución de contador binario potencial (isaacvr) - Código

```go
package main

import (
  "time"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/platforms/firmata"
)

func main() {

  firmataAdaptor := firmata.NewAdaptor("/dev/ttyACM0");
  led1 := gpio.NewLedDriver(firmataAdaptor, "13");
  led2 := gpio.NewLedDriver(firmataAdaptor, "12");
  led3 := gpio.NewLedDriver(firmataAdaptor, "11");
  led4 := gpio.NewLedDriver(firmataAdaptor, "10");

  ledList := []*gpio.LedDriver{ led1, led2, led3, led4 }

  work := func() {

    var cnt int = 0
    var aux int = 0
    var val int = 0

    gobot.Every(1 * time.Second, func() {

      if cnt == 16 {
        cnt = 0
      }

      aux = cnt

      for _, led := range ledList {
        val = aux % 2
        if val == 1 {
          led.On()
        } else {
          led.Off()
        }
        aux = aux / 2
      }

      cnt = cnt + 1

    });

  };

  robot := gobot.NewRobot("bot",
    []gobot.Connection{firmataAdaptor},
    []gobot.Device{led1, led2, led3, led4},
    work,
  );

  robot.Start();

}
```

--

### Solución binaria alternativa para el contador (olemis) - Código

```go

package main

import (
  "time"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/platforms/firmata"
)

func main() {
  firmataAdaptor := firmata.NewAdaptor("/dev/ttyACM0")
  leds := []*gpio.LedDriver {
    gpio.NewLedDriver(firmataAdaptor, "3")
    gpio.NewLedDriver(firmataAdaptor, "5")
    gpio.NewLedDriver(firmataAdaptor, "10")
    gpio.NewLedDriver(firmataAdaptor, "12")
  }

  counter := 0

  work := func () {
    for _, led := range leds {
      led.Off()
    }

    gobot.Every(1 * time.Second, func() {
      mask := 1
      for _, led := range leds {
        if mask & counter == 0 {
          led.Off()
        } else {
          led.On()
        }
        mask = mask << 1
      }
      counter++
    })
  }

  robot := gobot.NewRobot("bot",
    []gobot.Connection{firmataAdaptor},
    []gobot.Device{leds[0], leds[1], leds[2], leds[3]},
    work,
  );

  robot.Start();

}

```

---

## Botones

![](img/buttons.jpg)

---

## Build This

![](img/button-hardware.png)

---

## Guarda esto en un archivo y ejecútalo


```go
package main

import (
  "fmt"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/platforms/firmata"
)

func main() {

  firmataAdaptor := firmata.NewAdaptor("/dev/ttyACM0");
  button := gpio.NewButtonDriver(firmataAdaptor, "2")
  led := gpio.NewLedDriver(firmataAdaptor, "13")

  work := func() {

    button.On(gpio.ButtonPush, func(data interface{}) {
      led.On();
      fmt.Println("Button Pressed!");
    });

    button.On(gpio.ButtonRelease, func(data interface{}) {
      led.Off();
      fmt.Println("Button Released!");
    });

  };

  robot := gobot.NewRobot("bot",
    []gobot.Connection{firmataAdaptor},
    []gobot.Device{button, led},
    work,
  );

  robot.Start();

}
```

`go run button.go`
---

Intente presionar, soltar y mantener presionado el botón

Deberías ver alguna salida como esta en la consola

```

>> Botón pulsado!
Botón liberado!
Botón pulsado!
Botón liberado!
Botón pulsado!
Botón liberado!
```

---

El LED debe encenderse al presionar y apagarse al soltarlo.

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
2. Luces navideñas
3. Clave de acceso

--

### 1. Interruptor de luz

Haga que al presionar un botón alternativamente encienda y apague un LED

--

### Solución de interruptor de luz potencial - Hardware

![](img/light-switch-hardware.png)

--

### Solución de interruptor de luz potencial - Código

```go
package main

import (
  "fmt"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/platforms/firmata"
)

func main() {

  firmataAdaptor := firmata.NewAdaptor("/dev/ttyACM0");
  button := gpio.NewButtonDriver(firmataAdaptor, "2")
  led := gpio.NewLedDriver(firmataAdaptor, "13")

  work := func() {

    isOn := false;

    button.On(gpio.ButtonPush, func(data interface{}) {
      if isOn == true {
        led.Off();
        isOn = false;
      } else {
        led.On();
        isOn = true
      }
    });

  };

  robot := gobot.NewRobot("bot",
    []gobot.Connection{firmataAdaptor},
    []gobot.Device{button, led},
    work,
  );

  robot.Start();

}
```

--

## Componentes que estamos cubriendo

- LEDs (diodos emisores de luz)
- Botones
- <span style="color: yellow"> Servos </span>

---

## <span class="spin">S</span><span class="spin">E</span><span class="spin">R</span><span class="spin">V</span><span class="spin">O</span><span class="spin">S</span>

![](img/servo.jpg)

---

Toma tu servo y añádele uno de los adjuntos.

![](img/servo.jpg)

---

## Construya esto

![](img/servo-hardware.png)

---

## Servo Challenges

Ahora puedes pasar al siguiente componente, o trabajar en algunos desafíos de servo

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

```go
package main

import (
  "time"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/platforms/firmata"
)

func main() {

  firmataAdaptor := firmata.NewAdaptor("/dev/ttyACM0")
  servo := gpio.NewServoDriver(firmataAdaptor, "11")

  work := func() {

    var angle uint8 = 0;
    var max uint8 = 180;

    servo.Move(angle)

    gobot.Every(500 * time.Millisecond, func() {

      angle = (angle + 45) % max

      servo.Move( angle )

    });

  }

  robot := gobot.NewRobot("servoBot",
    []gobot.Connection{firmataAdaptor},
    []gobot.Device{servo},
    work,
  )

  robot.Start()

}
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

```go
package main

import (
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/platforms/firmata"
  term "github.com/nsf/termbox-go"
)

func reset() {
  term.Sync()
}

func main() {

  err := term.Init();

  if err != nil {
    panic(err)
  }

  defer term.Close()

  firmataAdaptor := firmata.NewAdaptor("/dev/ttyACM0")
  servo := gpio.NewServoDriver(firmataAdaptor, "11")

  work := func() {

    var angle uint8 = 0;

    servo.Move(angle)

    for {
      reset();
      switch ev := term.PollEvent(); ev.Type {
      case term.EventKey:
        switch ev.Key {
        case term.KeyArrowLeft:
          angle = 0
          servo.Move(angle)
        case term.KeyArrowRight:
          angle = 180
          servo.Move(angle)
        }
      }
    }

  }

  robot := gobot.NewRobot("servoBot",
    []gobot.Connection{firmataAdaptor},
    []gobot.Device{servo},
    work,
  )

  robot.Start()

}
```

--

Uh oh oh! Nos acabamos las diapositivas! Siéntase libre de probar algunos de los otros componentes de su kit mientras nosotros añadimos más!

---

## Winding Up

- Gracias por venir!