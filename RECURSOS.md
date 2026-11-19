# Recursos para Desarrollo de Videojuegos

## PixelFX (por Patch)
- **Sitio web / Galería en vivo:** https://patch-gg.github.io/pixelfx/
- **Repositorio GitHub:** https://github.com/patch-gg/pixelfx

### ¿Qué es?
PixelFX es una librería open-source con más de 240+ efectos visuales (VFX) en pixel art programados puramente en código (JavaScript/Canvas), sin depender de sprite sheets pre-renderizados.

### Características Principales:
1. **Generación por código:** 
   - Modificación dinámica de colores, escalas, semillas aleatorias (*seeds*) y orientación en tiempo real.
2. **Tipos de efectos:**
   - **Efectos Puros (*Pure*):** Bucles sin estado (auras, portales, cascadas, proyectiles) calculados directamente a partir del tiempo.
   - **Efectos Simulados (*Simulated*):** Sistemas de partículas y escombros con física simulada a 120Hz (humo, chispas rebotando, explosiones).
3. **Compatibilidad:**
   - **Web / HTML5:** Integración directa con JavaScript/Canvas (`npm i github:patch-gg/pixelfx`).
   - **Motores (Godot, Unity, GameMaker, Bevy, etc.):** Incluye scripts en Node.js (`node tools/render.mjs`) para exportar cualquier efecto como sprite sheet en formato PNG y JSON con información de tiempos.
4. **Herramientas de IA:**
   - Incluye prompts/skills para crear y refinar nuevos efectos mediante agentes.
