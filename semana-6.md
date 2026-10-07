---
layout: default
title: Semana 6
nav_order: 8
---

# Semana 6: Videojuego NEXUS: Arena Mecánica

En esta actividad desarrollé un videojuego de plataformas en 2D con **HTML, CSS y JavaScript**. El jugador controla a N-07, un robot que debe avanzar por instalaciones mecánicas, evitar o derrotar enemigos y reunir núcleos de energía hasta llegar al enfrentamiento final.

## Jugar

[**ABRIR NEXUS: ARENA MECÁNICA**](nexus-arena-mecanica.html){: .btn .btn-primary target="_blank" }

También puedes jugarlo directamente aquí. Si no aparece el juego, usa el botón de arriba.

<iframe
  src="{{ '/nexus-arena-mecanica.html' | relative_url }}"
  title="Videojuego NEXUS: Arena Mecánica"
  width="100%"
  height="650"
  style="border: 0; border-radius: 12px; background: #071014;"
  allow="fullscreen"
  allowfullscreen>
</iframe>

## Cómo se juega

- **Moverse:** A / D o flechas izquierda y derecha.
- **Saltar:** W o flecha arriba.
- **Disparar:** barra espaciadora.
- **Impulso (dash):** Shift izquierdo.
- **Pausar o continuar:** Esc o P.
- **Reiniciar el nivel:** R.

El juego cuenta con tres sectores: laboratorio, fábrica y núcleo central. En los primeros dos hay que recolectar todos los núcleos para activar la salida; en el último, el objetivo es vencer al jefe Archon.

## Tecnologías y funcionamiento

- **HTML** organiza el menú, las instrucciones y las pantallas del juego.
- **CSS** define la interfaz adaptable y su presentación visual.
- **JavaScript y Canvas 2D** dibujan el escenario y actualizan al jugador, enemigos, proyectiles, colisiones, partículas y niveles.
- **Web Audio API** genera efectos de sonido durante la partida.

## Objetivo de aprendizaje

Practicar la integración de estructura, estilos y programación en una aplicación interactiva, además de organizar los elementos de un videojuego mediante estados, funciones y ciclos de actualización.
