# Biblioteca Completa de Game Feel (por @game_feel_prompts)

Esta biblioteca recopila los 6 pilares de **"Juice" / Game Feel** para videojuegos en Pixel Art publicados por `@game_feel_prompts`. Cada efecto está desglosado con sus parámetros exactos, fórmulas matemáticas y tiempos de animación.

---

## 1. Taking Damage (Recibir Daño)
*El slime golpea al héroe.*

1. **Knockback:** Empujar al héroe 56px hacia atrás en un arco parabólico de 20px de altura y volver caminando.
2. **Blink I-Frames:** Parpadear el sprite cada 2 frames durante 0.6s de invencibilidad.
3. **Red Vignette:** Destellar 4 bandas rojas concéntricas en los bordes de la pantalla con desvanecimiento en 0.5s.
4. **Heart Break:** Temblar el último corazón del HUD, fracturarlo en 2 mitades que caen por gravedad rotando.
5. **Red Tint:** Rellenar el sprite del héroe de rojo al 90% al recibir el golpe, micro-parpadeo y desvanecer en 0.3s.
6. **Color Split:** Separar el sprite en copias roja y cian a 14px de distancia, más 4px de vibración (*shake*).

---

## 2. Hit Feedback (Feedback al Golpear)
*El héroe asesta un golpe con espada al enemigo.*

1. **Screen Shake:** Sacudida de cámara de 10px durante 0.25s con desaceleración rápida (*fast decay*).
2. **Hit Stop:** Congelar a ambos combatientes durante 0.12s al momento del contacto antes de reanudar el movimiento.
3. **White Flash:** Pintar el sprite del enemigo de blanco puro durante 3 frames tras el impacto.
4. **Damage Numbers:** Hacer emerger un número de daño pixelado sobre el enemigo (ej. "27"), elevándose y desvaneciéndose.
5. **Spark Burst:** Disparar 12 chispas pixeladas incandescentes desde el punto de contacto, afectadas por gravedad.
6. **Squash & Stretch:** Aplastar al enemigo un 138% de ancho y 62% de alto en el impacto, rebotando luego elásticamente.

---

## 3. Jump & Land (Salto y Aterrizaje)
*Mecánicas de movimiento y respuesta del suelo.*

1. **Dust Puff:** Al aterrizar, expulsar 3 nubes de polvo pixeladas hacia cada lateral, desvaneciéndose en 0.4s.
2. **Squash & Stretch:** Estirar el héroe al 122% de altura en el aire; aplastar al 130% de ancho al aterrizar y recuperar forma elásticamente.
3. **Camera Dip:** Al tocar el suelo fuertemente, bajar la cámara 12px y rebotar hacia arriba en 0.3s.
4. **Shock Ring:** Emitir un anillo pixelado dorado plano a lo largo del suelo desde los pies durante 0.4s.
5. **Ghost Trail:** Dejar 4 imágenes fantasma (*afterimages*) de color menta desvaneciéndose a lo largo del arco de salto cada 0.075s.
6. **Anticipation:** Agacharse (*crouch*) un 24% durante 0.18s antes del despegue, y luego impulsarse estirado verticalmente.

---

## 4. Chest Open (Apertura de Cofre)
*Interacción con cofres de tesoro.*

1. **Light Rays:** Emitir 10 rayos de luz dorada girando desde el interior del cofre (170px de longitud) durante 0.6s.
2. **Item Pop:** Expulsar una gema o ítem en un arco parabólico de 64px de altura, rebotando una vez antes de brillar.
3. **Lid Bounce:** Abrir la tapa con resorte hasta 118° con sobretiro (*overshoot*) y aplastar el cofre al 122% de ancho.
4. **Coin Fountain:** Disparar 14 monedas hacia arriba en fuente parabólica con física de gravedad y un rebote en el suelo.
5. **Rattle Tease:** Hacer vibrar y temblar el cofre $\pm 6^\circ$ durante 0.25s antes de abrirse, liberando estrellitas.
6. **Rarity Glow:** Resplandor según rareza (morado para épico/mítico o dorado para legendario) mientras el ítem asciende y gira.

---

## 5. Coin Pickup (Recolección de Monedas)
*Interacción con monedas y HUD.*

1. **Sparkle Pop:** Reemplazar la moneda al tocarla por un destello (*sparkle*) de 4 puntas que crece y desaparece.
2. **Fly to HUD:** La moneda vuela en arco parabólico hacia el contador del HUD en 0.35s; el contador da un golpe elástico (*bump*) al llegar.
3. **Floating +1:** Aparece un texto pixelado `+1` donde estaba la moneda, asciende 36px y se desvanece en 0.6s.
4. **Ring Burst:** Destellar la moneda en blanco y luego expandir un anillo pixelado dorado hacia afuera hasta 78px.
5. **Magnet Pull:** Al acercarse el héroe, la moneda es atraída magnéticamente, acelerando y estirándose hacia él.
6. **Pop & Shrink:** La moneda da un salto hacia arriba, crece al 150% girando velozmente y luego se reduce hasta absorberse.

---

## 6. Victory (Celebración de Victoria)
*Secuencia de fin de nivel o derrota de jefe.*

1. **Victory Flip:** El héroe salta 56px de altura, da una voltereta completa de 360° en el aire y aterriza con aplastamiento elástico (*squash*).
2. **Confetti Pop:** Dos cañones disparan 36 trozos de confeti multicolor hacia arriba que revolotean y caen lentamente.
3. **Win Banner:** Cartel "YOU WIN!" que entra con impacto de escala desde 240% hasta 100% en 0.1s con sacudida de 6px.
4. **Star Rating:** 3 estrellas doradas que caen e impactan con anillo expansivo en sus ranuras separadas por 0.12s.
5. **Fireworks:** 3 fuegos artificiales de 12 chispas cada uno estallan en el cielo separados por 0.12s.
6. **Light Rays:** 10 rayos dorados giratorios emergen detrás del héroe, con flash blanco en su sprite.
