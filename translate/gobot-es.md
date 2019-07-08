# Taller de gobots

#### Estas diapositivas: [slides.cuban.tech/gobot.html](http://slides.cuban.tech/gobot.html)

----------------

### Información Wifi

Red: cubantech

Contraseña: meet-ups

----------------

### Si aún no lo has hecho, instala Go

- [Descargar Go](https://golang.com/)

##### Descargar Go desde LAN] (ftp://qnap01.local/Public/soft/go)

## Nuestras pautas de la comunidad

[Sé excelente el uno con el otro] (https://github.com/nodeschool/havana/blob/master/Code_of_Conduct.md)

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

## Instalar Go si aún no lo has hecho

Descargar Go from the Internet] (https://golang.org/)

Descargar Go from LAN] (ftp://qnap01.local/Public/soft/go)

--

## Crear directorio de proyectos

```sh
gobots de mkdir
cd gobots
```

--

## Instalar Gobot

```sh
ve a buscar -d -u gobot.io/x/gobot/....
```

---

# Empezando

## Firmata estándar

- Permite a Gobot comunicarse con el Arduino a través de USB
- La mayoría de los Arduinos ya tienen instalados los Firmatas Estándar de talleres anteriores
- Vamos a comprobar que tu Arduino ya tiene instalado el Firmato Estándar!

---

## Conecta el arduino

![](img/connecting-arduino.jpg)

---

Crear el fichero

1. Ve a tu directorio de gobots
2. Cree un archivo llamado test.go
3. Copie el código que aparece a continuación y guarde

```Ir
paquete principal

importar (
  "tiempo"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/plataformas/firmata"
)

func principal() {

  firmataAdaptador := firmata.NewAdaptador("/dev/ttyACM0");
  led := gpio.newLedDriver(firmataAdaptor, "13");

  trabajo := func() {

    gobot.Every(1 * time.Second, func() {

      led.Toggle();

    });

  };

  robot := gobot.newRobot("bot",
    Conexión{firmataAdaptador},
    gobot. Dispositivo,
    trabajo,
  );

  robot. Inicio();

}
```

---

Ejecute el código

```sh
ir a ejecutar test.go
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

```Ir
paquete principal

importar (
  "tiempo"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot/plataformas/firmata"
)

func principal() {

  firmataAdaptador := firmata.NewAdaptador("/dev/ttyACM0");
  led := gpio.newLedDriver(firmataAdaptor, "11");

  trabajo := func() {

    gobot.Every(500 * time.Millisecond, func() {

      led.Toggle();

    });

  };

  robot := gobot.newRobot("bot",
    Conexión{firmataAdaptador},
    gobot. Dispositivo,
    trabajo,
  );

  robot. Inicio();

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

```Ir
paquete principal

importar (
  "tiempo"
  "gobot.io/x/gobot"
  "gobot.io/x/gobot/drivers/gpio"
  "gobot.io/x/gobot