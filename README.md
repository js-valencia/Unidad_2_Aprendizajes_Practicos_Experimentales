# 📊 Estadística — Unidad 2: Inferencia Estadística Paramétrica

**Universidad Nacional de Loja — FEIRNNR | Carrera de Ingeniería en Computación**

**Asignatura:** Teoría de la Distribución y Probabilidad

**Ciclo:** 2do "A" | **Grupo:** H

**Docente:** Cristian Ramiro Narváez Guillén

**Estudiante:** José Valencia

---

## 📁 Dataset Regional

Todos los análisis de este repositorio se aplican sobre el dataset oficial
de **Remuneraciones e Ingresos Adicionales del Municipio de Loja**,
obtenido del portal de transparencia institucional LOTAIP 2023.

| Característica | Valor |
|---|---|
| Registros | 2,883 empleados municipales |
| Variables | 12 |
| Variable principal de análisis | Remuneración Mensual Unificada |
| Regímenes laborales | LOSEP, Código de Trabajo, LOSEP-SOC, LOSEP-CONCEJAL |

📂 Archivo: [`dataset/3._remuneraciones_ingresos_adicionales.xlsx`](https://github.com/js-valencia/Unidad_2_Aprendizajes_Practicos_Experimentales/blob/main/Dataset_Regional/3._remuneraciones_ingresos_adicionales.xlsx)

---

## 📚 Contenido de la Unidad 2

### APE 06 — Ajuste de Modelo Discreto a Fenómeno Natural
📂 [`APE06_Distribuciones`](https://github.com/js-valencia/Unidad_2_Aprendizajes_Practicos_Experimentales/blob/main/Portafolio_APE_Unidad2/APE_006_Distribuciones.ipynb)

Se investigó si el fenómeno de **percepción de horas suplementarias**
por parte de los empleados municipales se ajusta a una distribución
**Binomial B(2883, 0.2109)**. Se estimaron los parámetros empíricos
directamente desde el dataset, se construyó la PMF teórica con
`scipy.stats` y se superpuso sobre el histograma empírico para
analizar visualmente el ajuste. Se verificaron las 4 condiciones del
modelo y los criterios de aproximación a la Normal (n·p = 608 ≥ 5,
n·q = 2275 ≥ 5). El valor observado k = 608 coincidió exactamente
con la media teórica del modelo.

**Librerías:** `pandas`, `numpy`, `scipy.stats`, `matplotlib`

---

### APE 07 — Identificación de Normalidad
📂 [`APE_007_Normal`](https://github.com/js-valencia/Unidad_2_Aprendizajes_Practicos_Experimentales/blob/main/Portafolio_APE_Unidad2/APE_007_Normal.ipynb)

Se sometió la variable **Remuneración Unificada Anual** a un análisis
riguroso de normalidad mediante métodos visuales y analíticos. Se
generó un histograma + KDE comparado con la curva Normal teórica,
y un gráfico Q-Q con `scipy.stats.probplot`. Se calcularon los
coeficientes de **Asimetría (skewness = 1.85)** y
**Curtosis (kurtosis = 9.08)**, concluyendo que la variable
**no sigue una distribución Normal**, con cola derecha pronunciada
generada por salarios altos de autoridades y directivos.

**Librerías:** `pandas`, `scipy.stats`, `seaborn`, `matplotlib`

---

### APE 08 — Distribuciones Muestrales y Teorema del Límite Central
📂 [`APE_008_TLC`](https://github.com/js-valencia/Unidad_2_Aprendizajes_Practicos_Experimentales/blob/main/Portafolio_APE_Unidad2/APE_008_TLC.ipynb)

Se demostró computacionalmente el **Teorema del Límite Central (TLC)**
mediante simulación estocástica de Monte Carlo sobre una población
exponencial asimétrica (λ=0.5, μ=2). Se extrajeron k=1000 muestras
de tamaño n=30 y se verificó que E[X̄] ≈ μ (diferencia de 0.0004).
Se aplicó bootstrapping sobre el dataset regional con 500 muestras
de n=40, observando la convergencia a la Normal. Se analizó el
decaimiento asintótico del Error Estándar para tamaños
n = [5, 10, 30, 50, 100, 500], validando que reducir el error a la
mitad requiere cuadruplicar la muestra.

**Librerías:** `numpy`, `matplotlib`, `seaborn`

---

### APE 09 — Intervalos de Confianza (Z y T de Student)
📂 [`APE_009_Intervalos`](https://github.com/js-valencia/Unidad_2_Aprendizajes_Practicos_Experimentales/blob/main/Portafolio_APE_Unidad2/APE_009_Intervalos.ipynb)

Se implementaron intervalos de confianza al 95% usando distribución
**Z** (n=100, consumo energético simulado) y **T de Student** (n=12,
sensores de calidad de agua). Se aplicó el IC al dataset regional
obteniendo un margen de error de **±$527.89** para la Remuneración
Unificada Anual. Se investigó el trade-off entre nivel de confianza
y precisión para niveles [80%, 90%, 95%, 99%], demostrando que
exigir 99% de certeza casi duplica el margen de error respecto al
95%, perdiendo utilidad práctica.

**Librerías:** `scipy.stats`, `numpy`, `matplotlib`

---

### APE 10 — Pruebas de Hipótesis Paramétricas
📂 [`APE_010_Pruebas_Hipotesis`](https://github.com/js-valencia/Unidad_2_Aprendizajes_Practicos_Experimentales/blob/main/Portafolio_APE_Unidad2/APE10_Pruebas_Hipotesis.ipynb)

Se implementaron pruebas de hipótesis Z y T de Student uni y
bimuestrales. Se validó que el consumo de sensores (t=3.54,
p=0.0004) difiere significativamente del valor declarado por el
fabricante, y que los tiempos de carga (t=2.91, p=0.011) superan
la meta de 2.6 segundos. Sobre el dataset regional se rechazó
H₀: μ=$1,200 con t=-98.47 y p≈0, evidenciando que la remuneración
media real ($713.81) dista ampliamente de ese valor referencial.
Se demostró el fenómeno de **significancia estadística vs práctica**:
con n=100,000 cualquier diferencia mínima se vuelve detectable.

**Librerías:** `scipy.stats`, `numpy`, `matplotlib`

---

### APE 11 — A/B Testing y Aproximación Asintótica
📂 [`APE_011_DosMuestras`](https://github.com/js-valencia/Unidad_2_Aprendizajes_Practicos_Experimentales/blob/main/Portafolio_APE_Unidad2/APE_011_DosMuestras.ipynb)

Se implementó la **aproximación de la Binomial a la Normal** para
escenarios de Big Data (N=10,000), documentando el
`OverflowError: int too large to convert to float` al intentar
calcular C(10000, 4200) con factoriales nativos. Se validó la
aproximación asintótica con corrección de continuidad de Yates,
obteniendo P(2050 ≤ X ≤ 2150) ≈ 0.7734 vs exacta 0.7737
(diferencia de 0.0003). Se demostró la ventaja computacional
de `norm.cdf()` O(1) frente al cálculo iterativo de PMF
discreta O(N) en entornos de Big Data.

**Librerías:** `scipy.stats`, `numpy`, `matplotlib`, `math`

---

### 🏆 Evaluación Sumativa — Unidad 2
📂 [`Evaluacion_Sumativa`](Evaluacion_Sumativa/)

Hito integrador de la Unidad 2 con dos componentes principales:

**Parte 1 — Prueba T Unimuestral:**
Se contrastó H₀: μ=$600 sobre la Remuneración Mensual Unificada.
Con t=23.05, gl=2882 y p≈0, se rechazó H₀ — la remuneración
media real ($713.81) supera significativamente el umbral de
referencia regional.

**Parte 2 — A/B Testing (T de Welch):**
Se compararon las remuneraciones entre régimen Código de Trabajo
(μ=$576.60, s=$44.26) y LOSEP (μ=$829.17, s=$303.95). El Test de
Levene (p≈0) detectó heterocedasticidad, justificando la T de Welch.
Resultado: t=-31.01, df=1489.70, p=2.47×10⁻¹⁶³, Cohen's d=1.14
(efecto grande). Existe una brecha salarial estructural de $252.57
mensuales (43.9%) entre regímenes.

**Librerías:** `scipy.stats`, `pandas`, `numpy`, `seaborn`, `matplotlib`

---

## 📝 Bitácora de Autoevaluación
📂 [`bitacora/bitacora_autoevaluacion.md`](https://github.com/js-valencia/Unidad_2_Aprendizajes_Practicos_Experimentales/blob/main/Bitacora/bitacora_autoevaluacion.md)

---

## 🔧 Tecnologías utilizadas

| Herramienta | Versión | Uso |
|---|---|---|
| Python | 3.10+ | Lenguaje base |
| pandas | 2.x | Manipulación del dataset |
| numpy | 1.x | Cálculos numéricos |
| scipy.stats | 1.x | Pruebas estadísticas |
| matplotlib | 3.x | Visualizaciones |
| seaborn | 0.x | Gráficos estadísticos |
| Google Colab | — | Entorno de desarrollo |

---

## 📖 Referencias

[1] R. E. Walpole, R. H. Myers, S. L. Myers, y K. Ye,
*Probabilidad y estadística para ingeniería y ciencias*,
9na ed. Pearson Educación, 2012.

[2] W. McKinney, *Python for Data Analysis*, 3ra ed.
O'Reilly Media, 2022.

[3] SciPy Developers, "scipy.stats Documentation," *SciPy.org*,
2024. [Online]. Disponible:
https://docs.scipy.org/doc/scipy/reference/stats.html.

[4] J. L. Devore, *Probability and Statistics for Engineering
and the Sciences*, 9th ed. Cengage Learning, 2016.

[5] D. C. Montgomery y G. C. Runger, *Applied Statistics and
Probability for Engineers*, 6th ed. Wiley, 2014.
