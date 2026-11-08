# Prompt de GitHub Copilot

Proyecto final · Econometría Financiera · Carlos Salvide (A01452194)

## Prompt principal

```
Escribe un notebook de R para Google Colab, comentado en español, que analice mi portafolio de
HowTheMarketWorks: COST (300 acciones), KOF (1000), GOOG (100), NVDA (100), TGT (50), BAC (150),
MSFT (10), AMZN (10) y AAPL (1).

1. Datos: precios de Yahoo Finance en frecuencia diaria (5 años), 60 minutos, 5 minutos y 1 minuto,
   más el S&P 500, SPY, VIX, ^TNX, MXN=X y CL=F, y los estados financieros trimestrales de cada empresa.
   Calcula valor, pesos y ganancia/pérdida del portafolio con el número de acciones y el precio pagado.
2. Regresión lineal simple (CAPM) por acción y para el portafolio con lm(), errores robustos HC1 (sandwich),
   Durbin-Watson, Breusch-Pagan (lmtest) y Jarque-Bera (tseries). Repite la beta con datos de 60, 5 y 1 minuto.
3. Regresión lineal múltiple con mercado, VIX, tasa a 10 años, USD/MXN y petróleo; VIF con car.
   Agrega variables dicótomas de hora del día para comparar la volatilidad en la apertura y el cierre.
4. Datos panel (plm) con crecimiento de ingresos, margen neto, ROE y apalancamiento contra el rendimiento
   trimestral: pooling, within, random; pFtest, plmtest y phtest (Hausman).
5. Metodología Box-Jenkins: ADF y KPSS, ACF y PACF, estimación de AR(1), AR(2), MA(1), MA(2), ARMA(1,1),
   ARMA(2,2) con forecast::Arima, comparación por AIC/BIC, Ljung-Box de los residuos, auto.arima y forecast
   a 10 días con intervalos de 80% y 95%. Valida contra el paseo aleatorio con los últimos 20 días.
   Pronostica también por hora y por minuto, y compara ARIMA, SARIMA y ETS.
6. GARCH(1,1) con distribución t usando rugarch, compara con GJR-GARCH y EGARCH, pronostica la volatilidad
   y calcula el VaR al 95%.
7. Estrategias de portafolio con quadprog (mínima varianza y máximo Sharpe, sin cortos, máximo 30% por acción),
   igual peso y momentum; backtest de los últimos 6 meses y órdenes de compra/venta en número de acciones.
8. Genera un reporte HTML autocontenido (imágenes en base64) y un Word con officer, con tablas, gráficas y conclusiones.
```

## Prompts de seguimiento

- `Explica cómo identificar el orden p y q de un ARMA a partir de la ACF y la PACF.`
- `¿Por qué la beta estimada con datos de 1 minuto es menor que la diaria? (efecto Epps)`
- `Agrega una descomposición STL del valor horario del portafolio y un periodograma con FFT para encontrar el periodo dominante de la volatilidad, siguiendo https://filippomb.github.io/python-time-series-handbook/notebooks/01/introduction_to_time_series.html`
- `Corrige la conversión de zona horaria de los datos intradía de Yahoo Finance.`
- `Escribe el README del repositorio con la tabla del portafolio y la lista de modelos.`
