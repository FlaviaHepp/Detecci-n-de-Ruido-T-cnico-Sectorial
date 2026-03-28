# 🧩Detección de Ruido Técnico Sectorial

Alta Volatilidad sin Dirección

Este proyecto implementa una consulta SQL que identifica sectores con riesgo extremo y baja direccionalidad, combinando métricas de distribución de retornos (kurtosis) y fuerza de tendencia (ADX).

La señal apunta a detectar entornos donde el mercado se mueve mucho, pero no va a ningún lado.

## 🧠Idea central

- No toda la volatilidad es una oportunidad.

Un sector puede mostrar:
- movimientos violentos
- retornos extremos
- alta incertidumbre

…pero sin una tendencia clara que los justifique.

Este proyecto responde a la pregunta:
- ¿Qué sectores son puro ruido técnico y, por lo tanto, difíciles y peligrosos de operar?

## ⚠️Valor de negocio

Identifica zonas de alto riesgo operativo

Útil para:
- evitar sectores intradeables
- ajustar sizing y stops
- filtrar señales falsas
- Mejora la gestión de riesgo a nivel sectorial

## 🗄️Estructura de datos esperada

- tickers
- campo	descripción
- ticker_id	Identificador del activo
- sector	Sector económico
- indicadores_tecnicos
- campo	descripción
- ticker_id	Identificador
- fecha	Fecha
- kurtosis	Kurtosis de retornos
- adx_14	ADX de 14 períodos

## ⚙️ Lógica de la consulta

- Analiza el último mes de datos

Calcula por sector:
- kurtosis promedio (riesgo de cola)
- ADX promedio (direccionalidad)

Filtra sectores con:
- kurtosis alta (ej. > 5)
- ADX bajo (ej. < 20)
- Ordena por riesgo extremo descendente

## 🔎Interpretación de resultados

- Kurtosis alta → retornos extremos frecuentes
- ADX bajo → ausencia de tendencia

Resultado:
- movimientos erráticos
- stops frecuentes
- falsas rupturas

Son sectores donde:
- el riesgo no está compensado por direccionalidad.

## 🚀Posibles extensiones

- Comparar con volatilidad implícita
- Analizar rolling windows
- Usar percentiles en vez de umbrales fijos
- Clasificar sectores por noise score

## 📝Notas finales

- Excelente filtro de qué NO operar
- Complemento ideal de análisis de fortaleza sectorial
- Aporta una capa de market regime detection

## 👤Autora
Flavia Hepp Proyecto de SQL aplicó un análisis de riesgo basado en eventos.

***
🚨 **¿Estás operando en sectores “ruidosos” sin darte cuenta?**

En el análisis técnico solemos buscar tendencias claras… pero, ¿qué pasa cuando el mercado hace exactamente lo contrario?

Hay sectores donde ocurre algo particularmente peligroso:
👉 Alta volatilidad (kurtosis elevada)
👉 Baja direccionalidad (ADX bajo)

📊 Esto se traduce en lo que llamo **“ruido técnico sectorial”**:
Movimientos bruscos, impredecibles y sin una tendencia definida.

⚠️ ¿Por qué es importante?
Porque estos sectores:

* Generan falsas señales constantemente
* Castigan estrategias tendenciales
* Aumentan el riesgo de sobreoperar

💡 En este análisis busqué:
Sectores con **kurtosis promedio > 5** (eventos extremos frecuentes)
y **ADX promedio < 20** (ausencia de tendencia clara) en el último mes.

📉 Resultado:
Identificación de sectores donde el riesgo no viene solo de la volatilidad… sino de la **falta de dirección**.

🧠 Insight clave:
No toda volatilidad es oportunidad.
A veces, es simplemente *ruido*.

---

🔍 Este tipo de análisis es parte de un enfoque más amplio que combina métricas estadísticas con indicadores técnicos para entender mejor el comportamiento del mercado.

#DataScience #Quant #Trading #AnálisisTécnico #Finanzas #MachineLearning #RiskManagement
