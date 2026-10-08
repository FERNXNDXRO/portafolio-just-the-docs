---
layout: default
title: "Semana 5: Ensamble y control del brazo robot"
nav_order: 7
---

# Semana 5: Ensamble y control del brazo robot

En esta semana ensamblamos el brazo de MDF y conectamos sus cuatro servomotores SG90 al Arduino. Cada potenciómetro controla un servo: al girarlo, cambia el ángulo del motor correspondiente.

## Materiales y componentes

- Arduino Uno.
- 4 servomotores SG90.
- 4 potenciómetros (se recomienda 10 kΩ).
- Piezas del brazo cortadas en MDF de 3 mm.
- Cables jumper y conexiones para los servos.
- Tornillos, tuercas y separadores para ensamblar las piezas.
- Fuente regulada de 5 V con corriente suficiente para los servos.

## Conexiones

| Control | Potenciómetro | Señal del servo | Movimiento |
|---|---|---|---|
| 1 | A0 | D3 | Base |
| 2 | A1 | D5 | Hombro |
| 3 | A2 | D6 | Codo |
| 4 | A3 | D9 | Pinza |

En cada potenciómetro, conecta una terminal exterior a **5 V**, la otra a **GND** y la terminal central a la entrada analógica indicada. En cada servo, conecta señal al pin indicado, alimentación roja a **5 V** y cable café/negro a **GND**.

**Alimentación:** cuatro servos pueden consumir más corriente de la que el pin 5 V del Arduino puede entregar. Usa una fuente regulada externa de 5 V adecuada para los servos y conecta su GND al GND del Arduino. No conectes la salida positiva de la fuente externa al pin 5 V del Arduino.

## Código Arduino

El programa lee las cuatro entradas analógicas, convierte cada lectura (0–1023) en un ángulo (0–180°) y manda el ángulo al servo correspondiente. Si algún mecanismo se fuerza contra el MDF, ajusta sus límites mecánicos y el rango del ángulo antes de seguir probando.

```cpp
#include <Servo.h>

const byte NUM_SERVOS = 4;
const byte pinesPot[NUM_SERVOS]  = {A0, A1, A2, A3};
const byte pinesServo[NUM_SERVOS] = {3, 5, 6, 9};

Servo servos[NUM_SERVOS];
int angulos[NUM_SERVOS] = {90, 90, 90, 90};

void setup() {
  for (byte i = 0; i < NUM_SERVOS; i++) {
    servos[i].attach(pinesServo[i]);
    servos[i].write(angulos[i]);  // posición inicial
  }
}

void loop() {
  for (byte i = 0; i < NUM_SERVOS; i++) {
    int lectura = analogRead(pinesPot[i]);        // valor de 0 a 1023
    int angulo = map(lectura, 0, 1023, 0, 180);  // convertir a grados
    angulo = constrain(angulo, 0, 180);
    servos[i].write(angulo);
  }

  delay(15); // pausa breve para que los servos sigan el movimiento
}
```

## Instrucciones para cargar y probar

1. Conecta el Arduino Uno a la computadora y abre Arduino IDE.
2. Selecciona la placa **Arduino Uno** y el puerto correspondiente.
3. Verifica que esté disponible la biblioteca **Servo** (viene incluida en Arduino IDE).
4. Copia el código, pulsa **Verificar** y después **Subir**.
5. Conecta los cuatro potenciómetros y los servos según la tabla. Revisa polaridad y tierra común antes de encender.
6. Enciende la fuente externa de 5 V. Gira un potenciómetro a la vez y confirma que se mueve únicamente el servo asignado.
7. Si un servo zumba, se calienta o intenta forzar una articulación, apaga la fuente y corrige el sentido, el montaje o el rango de movimiento.
8. Prueba la pinza con una pelota de 6 cm. Registra si logra sujetarla durante 5 segundos y agrega aquí el video de evidencia.

## Evidencia fotográfica del ensamble y control

Estas fotografías muestran el armado del brazo, sus servomotores y las conexiones con Arduino y los potenciómetros.

<div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:16px;margin:18px 0;">
  <figure style="margin:0;"><img src="{{ '/assets/img/semana-5/vista-general-brazo-control.jpg' | relative_url }}" alt="Vista general del brazo robot ensamblado y su circuito de control" loading="lazy" style="width:100%;border-radius:12px;"><figcaption>Vista general del brazo robot y el sistema de control.</figcaption></figure>
  <figure style="margin:0;"><img src="{{ '/assets/img/semana-5/detalle-mecanismo-brazo.jpg' | relative_url }}" alt="Detalle lateral del mecanismo y las uniones del brazo robot" loading="lazy" style="width:100%;border-radius:12px;"><figcaption>Detalle de la estructura, articulaciones y servomotores.</figcaption></figure>
  <figure style="margin:0;"><img src="{{ '/assets/img/semana-5/conexiones-arduino-potenciometros.jpg' | relative_url }}" alt="Detalle de conexiones entre Arduino, protoboard y potenciómetros" loading="lazy" style="width:100%;border-radius:12px;"><figcaption>Conexiones del Arduino y los potenciómetros en la protoboard.</figcaption></figure>
  <figure style="margin:0;"><img src="{{ '/assets/img/semana-5/montaje-servos-y-potenciometros.jpg' | relative_url }}" alt="Brazo conectado al Arduino, los servomotores y la protoboard de control" loading="lazy" style="width:100%;border-radius:12px;"><figcaption>Prueba del brazo con sus servos y controles conectados.</figcaption></figure>
</div>

## Videos de movimiento

Los siguientes videos se pueden reproducir directamente desde esta página con el control de reproducción.

<video controls playsinline preload="metadata" width="100%">
  <source src="{{ '/assets/videos/VIDEO.mp4' | relative_url }}" type="video/mp4">
  Tu navegador no puede reproducir este video.
</video>

<video controls playsinline preload="metadata" width="100%">
  <source src="{{ '/assets/videos/VIDEO2.mp4' | relative_url }}" type="video/mp4">
  Tu navegador no puede reproducir este video.
</video>

## Resultado y evidencia

El brazo ensamblado integra la base, las articulaciones, la pinza, cuatro servos y el Arduino. En esta sección se documentan las pruebas de movimiento y su resultado.
