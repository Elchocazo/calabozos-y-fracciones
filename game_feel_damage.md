# Análisis de Efectos: Taking Damage (game_feel_prompts)

Fuente analizada: Perfil **`@game_feel_prompts`**  
Publicación: **"Taking Damage / ダメージを受ける演出 (Part 1) — the slime hits the hero"**

Este perfil se especializa en **"Game Feel" (Juice)** para videojuegos retro / pixel art: micropulsos de animación, físicas, shaders y feedback sensorial que hacen que una acción (en este caso, recibir daño de un slime) se sienta contundente, legible y satisfactoria.

---

## Desglose Técnico de los 6 Efectos

### 1. Knockback (Retroceso con arco parabólico)
- **Instrucción original:** *"On hit, push the hero back 56px on a 20px arc, then walk back in."*
- **Implementación matemática:**
  - Desplazamiento horizontal: retroceso de $-56\text{ px}$ hacia atrás en una curva de desaceleración (Ease-Out).
  - Desplazamiento vertical (arco parabólico): altura de $-20\text{ px}$ en el pico ($h(t) = 4 \times 20 \times t \times (1 - t)$).
  - Fase de recuperación: tras tocar el suelo, camina de vuelta a su posición original con pasos rítmicos.

### 2. Blink I-Frames (Parpadeo de frames de invencibilidad)
- **Instrucción original:** *"Blink the hero sprite every 2 frames for 0.6s of invincibility."*
- **Implementación matemática:**
  - Duración total: $0.6\text{ segundos}$ ($36\text{ frames}$ a 60 FPS).
  - Frecuencia de parpadeo: `Math.floor(frame / 2) % 2 === 0` (visible durante 2 frames, invisible/translúcido al 20% durante 2 frames).
  - Propósito: Comunica al jugador que es inmune a daño consecutivo e impide muertes instantáneas injustas.

### 3. Red Vignette (Viñeta perimetral de alerta roja)
- **Instrucción original:** *"Flash 4 red pixel bands around the screen edge, fading over 0.5s."*
- **Implementación visual:**
  - 4 bandas o franjas de pixeles escalonadas con alfa decreciente (por ejemplo, bandas de 4px, 8px, 12px, 16px con `rgba(255, 30, 30, alpha)`).
  - Duración: Se desvanece gradualmente (fade out lineal o ease-out) durante $0.5\text{ s}$.

### 4. Heart Break (Destrucción de corazón en el HUD)
- **Instrucción original:** *"Shake the last HUD heart, crack it in two halves that fall away."*
- **Implementación visual:**
  - Fase 1 (Impacto / Shake): El último corazón activo vibra horizontalmente $(\pm 3\text{px})$ durante $0.15\text{ s}$.
  - Fase 2 (Fractura): Se divide en dos sprites/mitades (izquierda y derecha).
  - Fase 3 (Caída por gravedad):
    - Mitad izquierda: velocidad inicial $(-1.5\text{ px/f}, -3\text{ px/f})$, rotación antihoraria, gravedad $+0.2\text{ px/f}^2$.
    - Mitad derecha: velocidad inicial $(+1.5\text{ px/f}, -3\text{ px/f})$, rotación horaria, gravedad $+0.2\text{ px/f}^2$.
    - Desvanecimiento por alfa hasta desaparecer.

### 5. Red Tint / Flash (Flash de tinte rojo)
- **Instrucción original:** *"Fill the hero sprite red at 90% on hit, flicker, fade out in 0.3s."*
- **Implementación visual:**
  - Tinte monocromático rojo intenso (`#ff2030` con 90% opacidad mediante blend mode `source-atop` o canvas compositing).
  - Parpadeo de 1 o 2 frames a blanco puro / rojo antes de comenzar el desvanecimiento.
  - Duración: $0.3\text{ s}$ en volver a su paleta original.

### 6. Color Split / Aberración Cromática
- **Instrucción original:** *"Split the hero into red and cyan copies 14px apart, plus a 4px shake."*
- **Implementación visual:**
  - Canal rojo desplazado $-7\text{ px}$ hacia la izquierda (o $+14\text{ px}$ total respecto al cian).
  - Canal cian desplazado $+7\text{ px}$ hacia la derecha.
  - Agitación sísmica (*screen/sprite shake*): temblor de $\pm 4\text{ px}$ en los ejes X e Y durante $0.15 - 0.2\text{ s}$.
  - Los canales convergen rápidamente al centro conforme el impacto se disipa.

---

## El Secreto del "Game Juice"
En juegos profesionales (estilo *Celeste*, *Hollow Knight* o *Dead Cells*), estos 6 efectos **no se usan aislados**: se combinan en capas con pesos controlados para dar el impacto definitivo cuando el jugador recibe un golpe.
