# Econometría Financiera · Proyecto final

**Modelos econométricos del portafolio en HowTheMarketWorks (R)**

Carlos Salvide · A01452194 · Prof. Raymundo Diaz · EGADE Business School, Tecnológico de Monterrey

[![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1ErHpG2S5Sf7DTRsmbjekwdNcrcA0cfZP?usp=sharing)

## Entregables

| Entregable | Archivo / link |
|---|---|
| Notebook en Google Colab (R) | [Abrir en Colab](https://colab.research.google.com/drive/1ErHpG2S5Sf7DTRsmbjekwdNcrcA0cfZP?usp=sharing) · [`Proyecto_Final_Carlos_Salvide_R.ipynb`](Proyecto_Final_Carlos_Salvide_R.ipynb) |
| Reporte HTML | [`Reporte_Final_Carlos_Salvide.html`](Reporte_Final_Carlos_Salvide.html) |
| Reporte Word / PDF | [`Reporte_Final_Carlos_Salvide.docx`](Reporte_Final_Carlos_Salvide.docx) · [`Reporte_Final_Carlos_Salvide.pdf`](Reporte_Final_Carlos_Salvide.pdf) |
| R Markdown | [`Proyecto_Final_Carlos_Salvide.Rmd`](Proyecto_Final_Carlos_Salvide.Rmd) |
| Prompt de GitHub Copilot | [`PROMPT_COPILOT.md`](https://github.com/CSalvide/econometria-financiera-portafolio/blob/main/PROMPT_COPILOT.md) |
| Capturas de HowTheMarketWorks | `HOWMARKETWORKS 1.png`, `HOWMARKETWORKS 2.png`, `HOWMARKETWORKS 3.png` |

## Portafolio (concurso «Econometría Financiera EGADE Oct 26»)

| Ticker | Empresa | Acciones | Precio pagado (USD) |
|---|---|---:|---:|
| COST | Costco | 300 | 988.12 |
| KOF | Coca-Cola FEMSA | 1,000 | 108.15 |
| GOOG | Alphabet | 100 | 340.32 |
| NVDA | NVIDIA | 100 | 241.74 |
| TGT | Target | 50 | 153.59 |
| BAC | Bank of America | 150 | 54.64 |
| MSFT | Microsoft | 10 | 531.86 |
| AMZN | Amazon | 10 | 251.55 |
| AAPL | Apple | 1 | 333.39 |

## Modelos

1. **Regresión lineal simple (CAPM)** con datos diarios, por hora (60 min) y por minuto (5 y 1 min); pruebas de Durbin-Watson, Breusch-Pagan y Jarque-Bera, y errores robustos HC1.
2. **Regresión lineal múltiple**: mercado, VIX, tasa del Tesoro a 10 años, USD/MXN y petróleo; VIF. Variables dicótomas para las horas seleccionadas (apertura 9:30-10:30 y cierre 15:00-16:00).
3. **Datos panel** con reportes trimestrales (crecimiento de ingresos, margen neto, ROE y apalancamiento): MCO agrupado, efectos fijos, efectos aleatorios; pruebas F, Breusch-Pagan LM y Hausman.
4. **Series de tiempo (Box-Jenkins)**: ADF/KPSS, descomposición STL, FFT, exponente de Hurst, ACF/PACF, estimación de AR, MA, ARMA y ARIMA, diagnóstico Ljung-Box y **forecast** a 10 días, 7 horas, 60 minutos (5 min) y 30 minutos (1 min). Comparación ARIMA vs. SARIMA vs. ETS vs. paseo aleatorio.
5. **GARCH**: GARCH(1,1)-t, GJR-GARCH y EGARCH; pronóstico de volatilidad y VaR 95%.
6. **Estrategias**: igual peso, mínima varianza, máximo Sharpe y momentum; backtest fuera de muestra, frontera eficiente y órdenes de rebalanceo.

## Ejecución

- **Colab:** abrir `Proyecto_Final_Carlos_Salvide_R.ipynb` (entorno R), subir `datos_portafolio.zip` y las capturas a la carpeta de trabajo y ejecutar todo. El reporte HTML y Word queda en `salidas/`.
- **RStudio:** abrir `Proyecto_Final_Carlos_Salvide.Rmd` y hacer *Knit*.
- Sin `datos_portafolio.zip`, los datos se descargan de Yahoo Finance.

## Paquetes de R

`forecast`, `tseries`, `lmtest`, `sandwich`, `car`, `plm`, `rugarch`, `quadprog`, `zoo`, `httr`, `jsonlite`, `base64enc`, `officer`.

## Referencias

- Gujarati, D. N. y Porter, D. C. *Econometría*. McGraw-Hill.
- Box, G. E. P., Jenkins, G. M., Reinsel, G. C. y Ljung, G. M. *Time Series Analysis: Forecasting and Control*. Wiley.
- Hyndman, R. J. y Athanasopoulos, G. *Forecasting: Principles and Practice*. https://otexts.com/fpp3/
- Bianchi, F. M. *Time series analysis with Python*. https://filippomb.github.io/python-time-series-handbook/
- Bollerslev, T. (1986). Generalized autoregressive conditional heteroskedasticity. *Journal of Econometrics*, 31(3), 307–327.
