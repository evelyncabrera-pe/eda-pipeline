# Dataset Description Guide — Delinquency Prediction Dataset

## Dataset Overview

Dataset financiero y de comportamiento de clientes bancarios para predecir riesgo de morosidad. Combina atributos crediticios, historial de pagos e información de empleo.

**500 registros · 19 variables · Variable objetivo: `Delinquent_Account`**

---

## Descripción de variables

| Variable | Tipo | Descripción |
|---|---|---|
| `Customer_ID` | Categórica | Identificador único del cliente |
| `Age` | Numérica | Edad del cliente en años |
| `Income` | Numérica | Ingreso anual en USD *(contiene nulos ~8%)* |
| `Credit_Score` | Numérica | Score crediticio (300–850) *(contiene nulos <1%)* |
| `Credit_Utilization` | Numérica | % de crédito disponible en uso (0–100%) |
| `Missed_Payments` | Numérica | Total de pagos perdidos en los últimos 12 meses |
| `Loan_Balance` | Numérica | Saldo total de préstamos pendientes en USD *(contiene nulos ~6%)* |
| `Debt_to_Income_Ratio` | Numérica | Ratio deuda/ingreso expresado como porcentaje (0–100%) |
| `Employment_Status` | Categórica | Estado laboral: Employed / Unemployed / Self-Employed / Retired |
| `Account_Tenure` | Numérica | Años con cuenta activa |
| `Credit_Card_Type` | Categórica | Tipo de tarjeta: Student / Standard / Gold / Platinum / Business |
| `Location` | Categórica | Región del cliente: New York / Los Angeles / Chicago / Houston / Phoenix |
| `Month_1` a `Month_6` | Categórica | Historial de pagos últimos 6 meses: `On-time` / `Late` / `Missed` |
| `Delinquent_Account` | Binaria | **Variable objetivo** — 0 = Al día · 1 = Moroso |

---

## Observaciones de calidad

- `Employment_Status` contiene inconsistencias de texto (`EMP`, `employed`, `Employed`) → estandarizar
- `Month_1`–`Month_6` almacenadas como texto en lugar de valores ordinales numéricos → convertir
- Dataset desbalanceado: ~84% no morosos vs ~16% morosos

---

## Fuente del glosario

Tata Data Analytics Glossary — términos clave utilizados en este análisis:

- **EDA (Exploratory Data Analysis):** Análisis de datasets para resumir características principales y descubrir patrones antes del modelamiento formal
- **Data Imputation:** Reemplazo de datos faltantes por valores estimados para mantener la integridad del dataset
- **Credit Utilization:** Ratio entre el saldo actual de tarjetas y los límites de crédito disponibles
- **Delinquency:** Incumplimiento en pagos de deuda en los plazos establecidos
- **Imbalanced Data:** Situación en la que una clase es significativamente más frecuente que otra en la variable objetivo
