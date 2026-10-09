[README.md](https://github.com/user-attachments/files/33258948/README.md)
# Bomberman (NES) — Remake en Godot

Remake del **Bomberman de NES (1985)** desarrollado en **Godot 4.7.2** con GDScript, como trabajo práctico de la materia *Motores de Desarrollo* de la Tecnicatura en Desarrollo de Videojuegos (UNLaM, 2026).

<img width="854" height="744" alt="Bombra-Mania" src="https://github.com/user-attachments/assets/641be4fa-e93d-4f82-96d0-ff1a1a0a11c3" />


## 🎮 Jugar

Descargá el ejecutable para Windows desde la sección [**Releases**](../../releases), descomprimí y abrí `BomberMania.exe`. No requiere instalación.

> Windows puede mostrar el aviso "Windows protegió su PC" porque el ejecutable no está firmado: elegí **Más información → Ejecutar de todas formas**.

## Controles

| Acción | Teclas |
|---|---|
| Moverse | Flechas / WASD |
| Poner bomba | Espacio / Z |
| Detonar (con Detonator) | X |
| Pausa | Escape / P |

## Características

- **2 niveles** con mapa generado proceduralmente en cada partida (bloques fijos en damero y ladrillos al azar).
- Movimiento sobre grilla con **corrección automática al carril**, como en el original.
- **Explosiones en cruz** con alcance variable, destrucción de ladrillos y **reacción en cadena** entre bombas.
- **3 tipos de enemigos** con distinto comportamiento:
  - **Ballom**: deambula y gira al azar en los cruces.
  - **Onil**: más rápido y persigue al jugador.
  - **Pontan**: aparecen al agotarse el tiempo, persiguen y atraviesan ladrillos.
- **8 power-ups**: Bomb Up, Fire Up, Speed y 5 especiales (Wallpass, Detonator, Bombpass, Flamepass y Mystery).
- Puerta de salida y power-ups escondidos bajo ladrillos.
- **Multiplicador de puntos** al eliminar varios enemigos con una misma bomba.
- **Ranking persistente** con los 5 mejores puntajes.
- HUD con tiempo, puntaje y vidas; pausa; pantallas de título, intro de nivel, victoria y game over.
- Música y efectos de sonido originales.

## Aspectos técnicos

- **Arquitectura por escenas**: jugador, bomba, fuego, enemigos, power-ups, puerta, HUD y pantallas como escenas independientes y reutilizables.
- **Comunicación por señales** entre nodos (explosiones, muertes, ladrillos destruidos, cambios de puntaje), sin dependencias directas.
- **Autoloads** para el estado global (`GameManager`: vidas, puntaje, tiempo, nivel y ranking) y el audio (`AudioManager`, con pool de reproductores de efectos).
- **Capas de colisión** separadas (mundo, jugador, enemigos, bombas y ladrillos), lo que permite que power-ups como Wallpass o Bombpass solo cambien la máscara de colisión del jugador.
- **Niveles como escenas heredadas**: el nivel 2 hereda del 1 y solo modifica parámetros exportados en el Inspector.
- Un mismo script de enemigo configurado por Inspector (velocidad, puntaje, probabilidad de giro y de persecución, atravesar ladrillos) para los tres tipos.
- Herramientas de depuración disponibles solo en builds de debug (modo dios, otorgar power-ups, generar enemigos).

## Ejecutar el proyecto

1. Instalar [Godot 4.7.2](https://godotengine.org/).
2. Clonar el repositorio y abrir `project.godot` desde el gestor de proyectos.
3. Ejecutar con **F5**.

## Créditos

- Juego original: **Bomberman** © 1985 Hudson Soft. Este es un proyecto educativo y sin fines de lucro, sin afiliación con los titulares de los derechos.
- Sprites: [The Spriters Resource](https://www.spriters-resource.com/nes/) (ripeos de Black Squirrel y SuperJustinBros).
- Música: [KHInsider](https://downloads.khinsider.com/).
- Efectos de sonido: [The Sounds Resource](https://sounds.spriters-resource.com/).
- Fuente: [Press Start 2P](https://fonts.google.com/specimen/Press+Start+2P) (SIL Open Font License).

Desarrollado por **Nahuel Eberle** · [GitHub](https://github.com/nahueleberle)
