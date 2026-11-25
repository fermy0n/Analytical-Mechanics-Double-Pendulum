# Analytical-Mechanics-Double-Pendulum

Simulación numérica de un péndulo doble en python con RK4: análisis de conservación de energía, modos normales (caso simétrico), exponentes de Lyapunov, trayectorias y secciones de Poincaré.
---

El script está dividido en cinco bloques principales de validación física y dinámica no lineal:

1. **Conservación de la Energía y Precisión Numérica:**
   - Evalúa el error relativo de la energía mecánica total ($E = T + V$) a lo largo del tiempo para distintos pasos de integración ($\Delta t = 0.01\text{ s}$ y $\Delta t = 0.005\text{ s}$), verificando la estabilidad del integrador RK4.
2. **Modos Normales (Lineal):**
   - *Nota: Esta sección y sus gráficas son válidas exclusivamente para el **caso simétrico** ($m_1 = m_2 = m$, $l_1 = l_2 = l$) bajo la aproximación de ángulos pequeños.*
   - Compara los autovalores ($\lambda$) y frecuencias propias teóricas ($\omega_1, \omega_2$) con la evolución temporal obtenida numéricamente.
3. **Exponentes de Lyapunov y Horizonte de Predictibilidad:**
   - Calcula el máximo exponente de Lyapunov ($\lambda$) mediante el algoritmo de renormalización periódica de **Benettin** y lo contrasta con un ajuste lineal sobre la divergencia logarítmica de trayectorias cercanas ($\|\delta \mathbf{y}(t)\|$).
   - Estima el horizonte de predictibilidad ($t_h$) para distintos niveles de energía inicial ($\theta_0 \in \{0.3, 1.0, 1.5, 2.5\}\text{ rad}$).
4. **Visualización Espacial y Animación:**
   - Genera una animación comparativa (`animacion_pendulo_doble.gif`) entre un régimen regular ($\theta_0 = 0.3\text{ rad}$) y uno caótico ($\theta_0 = 2.5\text{ rad}$).
   - Traza las trayectorias completas de la segunda masa ($m_2$) codificadas por tiempo.
5. **Secciones de Poincaré:**
   - Construye mapas de Poincaré en el espacio de fases reducido $(\theta_2, p_2)$ usando la condición de cruce $\theta_1 = 0$ con $\dot{\theta}_1 > 0$ para múltiples condiciones iniciales a energía constante y el surgimiento del caos.
---
## Requisitos e Instalación

El código requiere **Python 3.8+** y la siguiente librería científica:

```bash
pip install numpy matplotlib pillow
