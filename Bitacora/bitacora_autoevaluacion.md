# Bitácora de Autoevaluación — Unidad 2

**Estudiante:** José Valencia | **Grupo:** H

**Asignatura:** Teoría de la Distribución y Probabilidad

---

## Resumen del Aprendizaje

La Unidad 2 representó un salto importante desde la estadística
descriptiva hacia la **inferencia estadística paramétrica**. El hilo
conductor de todos los trabajos fue el dataset regional de
remuneraciones del Municipio de Loja, lo que permitió que cada
concepto teórico tuviera una aplicación concreta y verificable.

## Logros por APE

- **APE 06:** Comprendí cómo estimar parámetros de modelos discretos
  directamente desde datos reales y validar el ajuste visualmente.
  El reto mayor fue corregir el modelo B(1,p) a B(n,p).

- **APE 07:** El TLC dejó de ser un teorema abstracto para convertirse
  en algo observable: ver cómo 500 muestras de una distribución
  asimétrica producen una campana perfecta fue el momento más
  revelador de la unidad.

- **APE 08:** Aprendí que "asumir normalidad" sin verificarla es un
  error metodológico grave. El Q-Q plot y los coeficientes de
  asimetría/curtosis son herramientas concretas para ese diagnóstico.

- **APE 09:** Entendí la diferencia conceptual entre estimación puntual
  e intervalar, y la interpretación frecuentista correcta del IC que
  evita el error de decir "hay 95% de probabilidad de que μ esté aquí".

- **APE 10:** La distinción entre significancia estadística y práctica
  (valor-p vs Cohen's d) fue la lección más importante para aplicar
  estadística en ingeniería real.

- **APE 11:** El OverflowError al calcular C(10000, 4200) con
  factoriales nativos fue el ejemplo más claro de por qué la
  aproximación asintótica no es solo teoría sino una necesidad
  computacional real en Big Data.

## Dificultades Superadas

- **Elección entre Z y T:** al principio confundía cuándo usar cada
  distribución. La regla práctica que me quedó clara: si σ poblacional
  es desconocida, siempre T; si n es grande, T ≈ Z de todas formas.

- **T de Welch vs T clásica:** entender que el Test de Levene es un
  paso previo obligatorio antes de cualquier comparación de dos grupos
  fue un aprendizaje clave para evitar errores de Tipo I.

- **Interpretación del valor-p:** el error conceptual más común de
  la unidad. El valor-p no es la probabilidad de que H₀ sea cierta,
  sino la probabilidad de observar datos tan extremos si H₀ lo fuera.

## Autoevaluación

| Criterio | Calificación |
|---|---|
| Comprensión conceptual | 9/10 |
| Implementación en Python | 9/10 |
| Aplicación al dataset regional | 10/10 |
| Documentación y presentación | 9/10 |

**Nota estimada: 9.5/10**
