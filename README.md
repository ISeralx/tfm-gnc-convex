# GNC de un lanzador reutilizable — Guiado por optimización convexa

Trabajo Fin de Máster · Máster en Sistemas Espaciales, Universidad Europea.

Diseño y simulación del sistema de **Guiado, Navegación y Control (GNC)** de un lanzador
reutilizable, con guiado por **optimización convexa** para el aterrizaje propulsado
(*Powered Descent Landing*). Se reproduce y valida el caso marciano de Malyuta et al. (2022)
y se extiende hasta un GNC completo y el aterrizaje 6DOF con actitud.

## Contenido

### Notebook principal
- **`simulacion_pdg.ipynb`** — Reproduce el aterrizaje **3DOF de mínimo combustible** como un
  problema de cono de segundo orden (SOCP) con CVXPY + Clarabel, validado contra la
  referencia (**t_f = 75 s, 373.75 kg**, aterrizaje exacto). Incluye: construcción del solver
  (cambio logarítmico, aproximación de Taylor, discretización ZOH), búsqueda del tiempo de
  vuelo óptimo, verificación de restricciones, propagación RK4 y análisis de robustez
  Monte Carlo.

### `extensiones/` — exploración más allá del TFM
| Notebook | Contenido |
|---|---|
| `modulo_A_bucle_cerrado.ipynb` | Guiado en **bucle cerrado** (MPC de horizonte recesivo) |
| `modulo_B_navegacion.ipynb` | **Navegación** con filtro de Kalman → GNC completo |
| `modulo_D_scvx.ipynb` | **Convexificación sucesiva (SCvx)** sobre el 3DOF no lineal |
| `modulo_E_6dof_planar.ipynb` | Aterrizaje **6DOF con actitud** (planar) |
| `modulo_F_6dof_3d.ipynb` | **6DOF completo en 3D** (cuaterniones + Euler) + aerodinámica |
| `estudio_direccion_velocidad.ipynb` | Efecto de la dirección de la velocidad inicial |

### `visualizacion/`
- **`aterrizaje_6dof.html`** — Animación interactiva del aterrizaje 6DOF (abrir en el navegador).

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
