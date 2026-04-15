# Portfolio-Meta-Learning-Engine

Portfolio Meta-Learning Engine es un sistema cuantitativo de nivel institucional diseñado para adaptar dinámicamente la asignación de portafolio mediante la selección inteligente de estrategias. Al combinar detección de regímenes de mercado, técnicas avanzadas de optimización y un enfoque de meta-learning probabilístico, el modelo identifica y aplica continuamente la estrategia de inversión más efectiva según las condiciones actuales del mercado.

El proyecto demuestra la integración de machine learning con finanzas cuantitativas para construir sistemas de inversión adaptativos y basados en datos. Incluye ingesta de datos en tiempo real, evaluación multi-estrategia y analítica visual avanzada, como la evolución tridimensional del portafolio y el seguimiento del desempeño condicionado por regímenes de mercado.

Este trabajo refleja una implementación práctica de enfoques modernos de inversión sistemática utilizados en hedge funds, con énfasis en robustez, adaptabilidad y toma de decisiones escalable bajo incertidumbre.

🧠 ¿Qué hace este código?

Este sistema es un dashboard cuantitativo en tiempo real que:

👉 Descarga datos de mercado
👉 Analiza el comportamiento de los activos
👉 Detecta el régimen del mercado
👉 Prueba varias estrategias
👉 Elige automáticamente la mejor
👉 Ajusta tu portafolio dinámicamente

En pocas palabras:

Es un sistema que decide cómo invertir tu dinero según las condiciones del mercado.

⚙️ Cómo funciona paso a paso (simplificado pero real)
1. 📊 Obtiene datos del mercado

Usa yfinance para traer precios históricos de activos como:

Nasdaq (^NDX)
Acciones (MSFT, ADBE)
ETFs
Cripto si quieres

👉 Esto es tu input real de mercado

2. 📈 Calcula variables clave (features)

Convierte precios en información útil:

Retornos → cuánto sube/baja el precio
Volatilidad → qué tan riesgoso es
Correlación → cómo se mueven entre sí
Tendencia → si el mercado sube o baja

👉 Esto es como “leer el estado del mercado”

3. 🧩 Detecta el régimen del mercado

Aquí es donde se pone interesante:

Usa:

Gaussian Mixture Model (GMM) → separa mercado en alta/baja volatilidad
PCA → detecta si los activos se mueven juntos
Trend filter → mide fuerza de tendencia

Resultado:

Hoy el mercado está:
- Alta volatilidad
- Alta correlación
- Tendencia fuerte

👉 Esto define el contexto de inversión

4. 🧠 Prueba múltiples estrategias

El sistema simula varias formas de invertir:

Mean-Variance → balance riesgo/retorno
Risk Parity → iguala el riesgo
Minimum Variance → busca estabilidad
Momentum → sigue lo que sube
Defensive → protege en mercados volátiles

👉 Cada una genera un portafolio diferente

5. 🧪 Meta-Learning (la clave del sistema)

Aquí está lo más importante:

Para cada ventana de tiempo:

Aplica TODAS las estrategias
Calcula su rendimiento (Sharpe ratio)
Elige la mejor
Calcula qué tan confiable es esa decisión

👉 Es como tener un “gestor de fondos automático” que elige estrategias

6. 🔄 Ajusta el portafolio (rebalanceo)

El sistema cambia tu inversión cuando:

cambia la mejor estrategia
cambia el régimen del mercado

👉 No hace overtrading, solo se adapta cuando es necesario

7. 📊 Mide resultados

Te muestra:

Rentabilidad total
Drawdown (pérdidas)
Sharpe ratio
PnL
Equity curve

👉 Esto es lo que usarías para evaluar si sirve o no

8. 🎥 Visualización avanzada

Incluye:

Curva de capital
Estrategias activas en el tiempo
Asignación actual
Sharpe dinámico
Regímenes de mercado
Evolución 3D del portafolio

👉 Esto es nivel dashboard de fondo cuantitativo

💰 ¿Cómo funcionaría en tus inversiones?

Aquí viene lo importante: cómo lo usarías tú en la vida real

🟢 Caso 1: Simulación (lo que hace ahora)

Actualmente el sistema:

No ejecuta trades reales
Solo simula decisiones

👉 Sirve para:

probar ideas
validar estrategias
hacer research
🟡 Caso 2: Apoyo para decisiones reales

Podrías usarlo así:

Ejemplo:

Hoy el modelo dice:

Estrategia: Momentum
Asignación:
- MSFT: 40%
- NDX: 30%
- MELI: 30%

👉 Tú manualmente replicas eso en tu broker

🔴 Caso 3: Automatización (nivel pro)

Si lo conectas con un broker (ej: Alpaca, Interactive Brokers):

👉 El sistema podría:

decidir estrategia automáticamente
calcular pesos
ejecutar órdenes
rebalancear solo
