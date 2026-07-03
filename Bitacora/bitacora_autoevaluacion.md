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

- **APE 06:** Aprendí a modelar distribuciones discretas (Binomial y
  Poisson) sobre escenarios de ingeniería reales. En la Binomial simulé
  fallos en microservicios (n=20, p=0.15) y en Poisson modelé peticiones
  erróneas a servidores (λ=4.5). El punto más interesante fue aplicar
  Poisson sobre el dataset regional con λ=30.13 y comparar visualmente
  si los datos de horas suplementarias seguían ese modelo. También
  demostré la aproximación Binomial→Poisson cuando n→∞ y p→0,
  verificando que la diferencia entre ambos modelos es menor a 6.3×10⁻⁴.

- **APE 07:** Comprendí que identificar normalidad no es una suposición
  sino una verificación obligatoria. Aplicé histograma + KDE, gráfico
  Q-Q y calculé skewness=1.85 y kurtosis=9.08 sobre la Remuneración
  Unificada Anual del dataset regional, concluyendo que la variable no
  es normal por la cola derecha generada por salarios altos de
  autoridades. El Q-Q plot fue la herramienta más visual para detectar
  esa desviación en las colas.

- **APE 08:** El TLC dejó de ser un teorema abstracto para convertirse
  en algo observable: ver cómo 500 muestras de una distribución
  asimétrica producen una campana perfecta fue el momento más
  revelador de la unidad. Verifiqué que E[X̄] ≈ μ con una diferencia
  de apenas 0.0004, y demostré que reducir el error estándar a la
  mitad requiere cuadruplicar el tamaño de muestra — una implicación
  directa en el costo de recolección de datos en ingeniería.

- **APE 09:** Entendí la diferencia conceptual entre estimación puntual
  e intervalar, y la interpretación frecuentista correcta del IC que
  evita el error de decir "hay 95% de probabilidad de que μ esté aquí".
  Sobre el dataset regional obtuve un margen de ±$527.89, y el
  trade-off entre confianza y precisión quedó claro: pasar del 95%
  al 99% casi duplica el margen de error, sacrificando utilidad
  práctica por certeza adicional.

- **APE 10:** La distinción entre significancia estadística y práctica
  fue la lección más importante para aplicar estadística en ingeniería
  real. Con n=100,000 cualquier diferencia mínima de 0.01V se vuelve
  estadísticamente detectable aunque sea irrelevante en la práctica.
  Sobre el dataset regional rechacé H₀: μ=$1,200 con t=-98.47 y p≈0,
  evidenciando que la remuneración media real ($713.81) dista
  ampliamente del valor hipotético.

- **APE 11:** Aprendí la diferencia fundamental entre muestras
  independientes y muestras pareadas, y cuándo aplicar cada prueba.
  El caso del firewall (muestras pareadas) fue el más revelador:
  entender que usar T para muestras independientes en ese escenario
  sería un error metodológico grave porque ignora la correlación
  entre mediciones del mismo servidor. Con t=12.34 y p=3.28×10⁻⁹
  la reducción de latencia quedó demostrada contundentemente.

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
