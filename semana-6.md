---
layout: default
title: "Semana 6: Ingeniería de prompting"
nav_order: 8
---

# Semana 6: Ingeniería de prompting y videojuego

## Reto del profesor

Crear un videojuego con **HTML, CSS y JavaScript**, publicarlo en GitHub Pages y vincularlo desde el repositorio. La actividad también pide usar contexto, probar instrucciones y refinar el resultado de manera iterativa.

## NEXUS: Arena Mecánica

Desarrollé un videojuego de plataformas 2D de ciencia ficción. El jugador controla al robot N-07, reúne núcleos de energía, evita o combate enemigos y avanza hasta el enfrentamiento final contra Archon.

<a class="btn btn-primary" href="{{ '/nexus-arena-mecanica.html' | relative_url }}" target="_blank" rel="noopener">Jugar a pantalla completa</a>

También puedes jugarlo aquí mismo:

<iframe
  src="{{ '/nexus-arena-mecanica.html' | relative_url }}"
  title="NEXUS: Arena Mecánica"
  width="100%"
  height="650"
  style="border: 0; border-radius: 12px; background: #071014;"
  allow="fullscreen"
  allowfullscreen>
</iframe>

## Controles

- **Moverse:** A / D o flechas izquierda y derecha.
- **Saltar:** W o flecha arriba.
- **Disparar:** barra espaciadora.
- **Impulso:** Shift izquierdo.
- **Pausar o continuar:** Esc o P.
- **Reiniciar el nivel:** R.

## Los seis sectores

1. **Laboratorio:** reúne los núcleos y activa la salida.
2. **Fábrica de robots:** supera plataformas y unidades de seguridad.
3. **Núcleo central:** derrota al primer guardián.
4. **Jardín de silicio:** explora una zona de investigación invadida.
5. **Forja de titanio:** enfrenta enemigos más resistentes y recoge cinco núcleos.
6. **Última defensa:** combate final contra Archon, con dos fases de ataque.

La campaña aumenta la dificultad por etapas. Los núcleos suman puntos y recuperan parte de la integridad y energía del robot. El juego también guarda el récord de puntuación en el navegador.

## Proceso de ingeniería de prompting

**Prompt inicial:** “Crea un videojuego en HTML, CSS y JavaScript que pueda publicar en GitHub Pages.”

Después agregué rol, contexto y requisitos para que la instrucción fuera más precisa:

> Actúa como diseñador y programador de videojuegos web. Crea un juego de plataformas 2D de ciencia ficción en un solo archivo HTML, con CSS y JavaScript integrados, que funcione sin bibliotecas externas en GitHub Pages. El personaje es N-07, un robot de mantenimiento. Incluye seis sectores con escenarios y dificultad progresiva, enemigos, núcleos coleccionables, dos enfrentamientos contra jefes, una interfaz clara, controles de teclado y controles táctiles para móvil. Explica los controles, conserva un menú para iniciar la partida y permite jugar dentro de la página.

Luego refiné el resultado por iteraciones: pedí una presentación visual más cuidada, añadí sectores y progresión, y mejoré el combate final. La estructura del prompt incluye **rol, tarea clara, contexto, restricciones y ejemplos concretos de mecánicas**, siguiendo las recomendaciones de la clase.

## Tecnologías y funcionamiento

- **HTML** estructura el menú, las instrucciones y las pantallas.
- **CSS** define la interfaz adaptable, los controles táctiles y el estilo visual.
- **JavaScript y Canvas 2D** dibujan y actualizan el mundo, las colisiones, los enemigos, proyectiles, objetos y niveles.
- **Web Audio API** crea efectos de sonido durante la partida.

El archivo del juego está publicado en este mismo repositorio: [ver el código fuente de NEXUS](https://github.com/FERNXNDXRO/portafolio-just-the-docs/blob/main/nexus-arena-mecanica.html).

## Uso de inteligencia artificial

Utilicé ChatGPT como apoyo para proponer estructura, código, mecánicas y mejoras visuales. Fui dando instrucciones más específicas y pedí cambios por iteraciones; las decisiones sobre la temática, los controles y la progresión se definieron para este proyecto. El resultado debe revisarse y jugarse antes de presentarlo.

**Referencia:** OpenAI. (2026). *ChatGPT* [asistente de inteligencia artificial]. https://chatgpt.com/
