# GNC de un lanzador reutilizable — Guiado por optimización convexa

Trabajo Fin de Máster · Máster en Sistemas Espaciales, Universidad Europea.

Diseño y simulación del sistema de **Guiado, Navegación y Control (GNC)** de un lanzador
reutilizable, con guiado por **optimización convexa** para el aterrizaje propulsado
(*Powered Descent Landing*). Se reproduce y valida el caso marciano de Malyuta et al. (2022).

## Contenido

### Notebook principal
- **`simulacion_pdg.ipynb`** — Reproduce el aterrizaje **3DOF de mínimo combustible** como un
  problema de cono de segundo orden (SOCP) con CVXPY + Clarabel, validado contra la
  referencia (**t_f = 75 s, 373.75 kg**, aterrizaje exacto). Incluye: construcción del solver
  (cambio logarítmico, aproximación de Taylor, discretización ZOH), búsqueda del tiempo de
  vuelo óptimo, verificación de restricciones, propagación RK4 y análisis de robustez
  Monte Carlo.

### Presentación de la defensa
- **`presentacion/defensa_animada.html`** — Presentación animada de la defensa del TFM
  (26 diapositivas). Es autocontenida: se abre en cualquier navegador, sin conexión.
  Controles: → o clic para avanzar, ← para retroceder, F pantalla completa, H ayuda.
  **Verla en línea:** https://iseralx.github.io/tfm-gnc-convex/presentacion/defensa_animada.html
- **`presentacion/defensa_preguntas.html`** — Preguntas y respuestas de apoyo (33), con índice clicable.
  **Verla en línea:** https://iseralx.github.io/tfm-gnc-convex/presentacion/defensa_preguntas.html


## Cómo ejecutar

Requiere Python 3.9+ y las dependencias de `requirements.txt`:

```bash
pip install -r requirements.txt
jupyter notebook simulacion_pdg.ipynb
```

Ejecutar las celdas de arriba a abajo. El solver convexo (Clarabel) se instala con CVXPY.

## Referencia principal

Malyuta, D., Reynolds, T., Szmuk, M., Lew, T., Bonalli, R., Pavone, M., Açıkmeşe, B. (2022).
*Convex Optimization for Trajectory Generation: A Tutorial.* IEEE Control Systems Magazine.
