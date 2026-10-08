---
layout: default
title: "Semana 6: Ingeniería de prompting"
nav_order: 8
---

# Semana 6: Ingeniería de prompting y videojuego

## Reto del profesor

Crear un videojuego con **HTML, CSS y JavaScript**, publicarlo en GitHub Pages y vincularlo desde el repositorio. La actividad también pide usar contexto, probar instrucciones y refinar el resultado de manera iterativa.

## NEXUS: Arena Mecánica

Desarrollé un videojuego de plataformas 2D de ciencia ficción. El jugador controla al robot N-07, reúne núcleos de energía, evita o combate enemigos y avanza hasta el enfrentamiento final contra Archon. La campaña incluye seis sectores y ahora también permite jugar en **cooperativo local para dos personas**.

También puedes jugarlo aquí mismo:

<iframe
  id="nexus-game"
  src="{{ '/nexus-arena-mecanica.html' | relative_url }}"
  title="NEXUS: Arena Mecánica"
  width="100%"
  height="650"
  style="border: 0; border-radius: 12px; background: #071014;"
  allow="fullscreen"
  allowfullscreen>
</iframe>

<button type="button" onclick="document.getElementById('nexus-game').requestFullscreen?.()" style="display:block; width:fit-content; margin:22px auto 30px; padding:16px 26px; border:3px solid #101820; border-radius:12px; background:#ffd43b; color:#111; box-shadow:0 5px 0 #b78300,0 10px 24px rgba(0,0,0,.22); font-size:1.15rem; font-weight:900; letter-spacing:.04em; text-align:center; cursor:pointer;">🎮 JUGAR EN PANTALLA COMPLETA</button>

## Cómo jugar

Puedes iniciar una partida individual o elegir **Modo cooperativo · 2 jugadores** en el menú del juego. En cooperativo, ambas personas juegan en la misma computadora, comparten la puntuación y colaboran durante los seis sectores. Cada robot tiene **tres vidas** y su propia integridad. Al agotarse la integridad, pierde una vida y reaparece; la partida termina cuando el jugador individual, o ambos integrantes del equipo, se quedan sin vidas.

### Controles para dos jugadores

- **Jugador 1:** A / D para moverse, W para saltar, Espacio para disparar y Shift izquierdo para el impulso.
- **Jugador 2:** flechas izquierda y derecha para moverse, flecha arriba para saltar, Enter para disparar y Shift derecho para el impulso.
- **Pausa o continuar:** Esc o P.
- **Reiniciar el nivel:** R.

En el modo individual, también puedes usar las flechas para moverte y saltar. Desde el menú principal, abre **Personalizar robot**. Ahí encontrarás apartados separados para **Vestimenta y accesorios** y **Color del uniforme**. El robot de vista previa gira continuamente y también puedes arrastrarlo para verlo en 360°. Puedes elegir antena, casco táctico, mochila, alas, gorra de piloto, corona o sombrero; además, hay cuatro estilos de uniforme y seis colores prediseñados, con opción de crear uno personalizado. La apariencia elegida se conserva en el navegador y se refleja en el juego. Durante la partida, la parte superior muestra la integridad, energía y vidas de cada jugador.

## Los seis sectores

1. **Laboratorio:** reúne los núcleos y activa la salida.
2. **Fábrica de robots:** supera plataformas y unidades de seguridad.
3. **Núcleo central:** derrota al primer guardián.
4. **Jardín de silicio:** explora una zona de investigación invadida.
5. **Forja de titanio:** enfrenta enemigos más resistentes y recoge cinco núcleos.
6. **Última defensa:** combate final contra Archon, con dos fases de ataque.

La campaña tiene seis sectores que aumentan de dificultad, desde el laboratorio hasta la última defensa. Al terminar un sector aparece una evaluación de tres estrellas: 3 si no se gastaron vidas, 2 si se perdió una y 1 si se perdieron dos o más. Al iniciar cada sector, cada jugador recibe tres vidas nuevas; al perder una, reaparece con la integridad restaurada. El mapa de campaña muestra la ruta, los sectores desbloqueados y las estrellas obtenidas; desde ahí se inicia el siguiente nivel. La puntuación y las estrellas ganadas se conservan durante la campaña. El siguiente sector continúa desde el mapa, sin regresar al sector 1. Los núcleos suman puntos y recuperan parte de la integridad del equipo. El juego también guarda el récord de puntuación en el navegador.

## Proceso de ingeniería de prompting

**Prompt inicial:** “Crea un videojuego en HTML, CSS y JavaScript que pueda publicar en GitHub Pages.”

Después agregué rol, contexto y requisitos para que la instrucción fuera más precisa:

> Actúa como diseñador y programador de videojuegos web. Crea un juego de plataformas 2D de ciencia ficción en un solo archivo HTML, con CSS y JavaScript integrados, que funcione sin bibliotecas externas en GitHub Pages. El personaje es N-07, un robot de mantenimiento. Incluye seis sectores con escenarios y dificultad progresiva, enemigos, núcleos coleccionables, dos enfrentamientos contra jefes, una interfaz clara, controles de teclado y controles táctiles para móvil. Explica los controles, conserva un menú para iniciar la partida y permite jugar dentro de la página.

Luego refiné el resultado por iteraciones: pedí una presentación visual más cuidada, añadí sectores y progresión, mejoré el combate final y agregué el modo cooperativo con controles para cada jugador. La estructura del prompt incluye **rol, tarea clara, contexto, restricciones y ejemplos concretos de mecánicas**, siguiendo las recomendaciones de la clase.

## Tecnologías y funcionamiento

- **HTML** estructura el menú, las instrucciones y las pantallas.
- **CSS** define la interfaz adaptable, los controles táctiles y el estilo visual.
- **JavaScript y Canvas 2D** dibujan y actualizan el mundo, las colisiones, los enemigos, proyectiles, objetos y niveles.
- **Web Audio API** crea efectos de sonido durante la partida.

Al abrir la página aparece una animación de arranque de NEXUS antes del menú principal; puedes entrar al menú con el botón en pantalla o esperar a que termine. Al iniciar una partida también se muestra una breve activación de los robots.

El archivo del juego está publicado en este mismo repositorio: [ver el código fuente de NEXUS](https://github.com/FERNXNDXRO/portafolio-just-the-docs/blob/main/nexus-arena-mecanica.html).

## Uso de inteligencia artificial

Utilicé ChatGPT como apoyo para proponer estructura, código, mecánicas y mejoras visuales. Fui dando instrucciones más específicas y pedí cambios por iteraciones; las decisiones sobre la temática, los controles y la progresión se definieron para este proyecto. El resultado debe revisarse y jugarse antes de presentarlo.

**Referencia:** OpenAI. (2026). *ChatGPT* [asistente de inteligencia artificial]. https://chatgpt.com/

