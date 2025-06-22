Diccionario de datos para proyecto de Credit Scoring

Descripción General

Se detallan las columnas existentes en los dataset originales (train.csv y test.csv), las cuales fueron procesadas para el posterior entrenamiento de modelos.

1. Train.csv

Propósito: almacena datos de panel sobre clientes de una entidad finaciera. Los datos corresponden a información sociodemográfica básica y de comportamiento de crédito histórica.

Columnas:

| Columna | Tipo de Dato | Descripción |
| --- | --- | --- |
| ID | VARCHAR(20) | Código identificador del registro, distinto al Customer_ID. Similar a surrogate keys en SQL (ej: '0x160a'). |
| Customer_ID | VARCHAR(20) | Identificador único del cliente, que puede repetirse por mes (ej: 'CUS_0xd40'). |
| Month | VARCHAR(15) | Mes del registro (ej: 'August'). Útil para trabajar con datos de panel. |
| Name | VARCHAR(100) | Nombre completo del cliente. |
| Age | FLOAT | Edad del cliente. |
| SSN | VARCHAR(20) | Número de Seguridad Social del cliente. |
| Occupation | VARCHAR(50) | Ocupación u oficio del cliente. Contiene múltiples categorías laborales. |
| Annual_Income | FLOAT | Ingreso anual del cliente en dólares. |
| Monthly_Inhand_Salary | FLOAT | Ingreso mensual neto del cliente, en dólares. |
| Num_Bank_Accounts | INT | Número de cuentas bancarias que tiene el cliente. |
| Num_Credit_Card | INT | Número de tarjetas de crédito activas del cliente. |
| Interest_Rate | INT | Tasa de interés asignada al cliente. |
| Num_of_Loan | FLOAT | Número de créditos vigentes del cliente. |
| Delay_from_due_date | INT | Retraso en días desde la fecha de vencimiento de pago. |
| Num_of_Delayed_Payment | FLOAT | Número de pagos atrasados en el historial del cliente. |
| Changed_Credit_Limit | FLOAT | Cambios en el límite de crédito. Puede representar una variación relativa o pequeña en términos absolutos. |
| Num_Credit_Inquiries | FLOAT | Número de consultas de crédito realizadas por instituciones financieras. |
| Credit_Mix | VARCHAR(15) | Diversificación de tipos de crédito. Categorías: Good, Standard, Bad. |
| Outstanding_Debt | FLOAT | Saldo total de deuda pendiente del cliente, en dólares. |
| Credit_Utilization_Ratio | FLOAT | Ratio de utilización de crédito: (saldo pendiente / límite total) * 100. Normalmente entre 25% y 45%. |
| Credit_History_Age | FLOAT | Antigüedad del historial crediticio en meses (procesado desde su forma original texto con años y meses). |
| Payment_of_Min_Amount | VARCHAR(10) | Si el cliente paga el mínimo en sus tarjetas. Valores: Yes, No, NM (requiere análisis o limpieza). |
| Total_EMI_per_month | FLOAT | Cuotas mensuales totales pagadas por el cliente (capital + intereses). |
| Amount_invested_monthly | FLOAT | Monto ahorrado mensualmente por el cliente, en dólares. |
| Payment_Behaviour | VARCHAR(50) | Comportamiento de pago. Ej: 'Low_spent_Small_value_payments'. |
| Monthly_Balance | FLOAT | Saldo promedio mensual en cuenta corriente, en dólares. |
| Credit_Score | VARCHAR(10) | Etiqueta del puntaje crediticio. Clases: Poor, Standard, Good. (Variable objetivo). |

### Columnas derivadas del split de Type_of_loan:

| Columna | Tipo de Dato | Descripción |
| --- | --- | --- |
| Payday Loan | VARCHAR(5) | Indica si el cliente tiene este tipo de crédito. |
| Auto Loan | VARCHAR(5) | Indica si el cliente tiene este tipo de crédito. |
| Credit-Builder Loan | VARCHAR(5) | Indica si el cliente tiene este tipo de crédito. |
| Not Specified | VARCHAR(5) | Presencia de préstamos sin especificación clara. |
| Debt Consolidation Loan | VARCHAR(5) | Indica si el cliente tiene este tipo de crédito. |
| Student Loan | VARCHAR(5) | Indica si el cliente tiene este tipo de crédito. |
| Mortgage Loan | VARCHAR(5) | Indica si el cliente tiene este tipo de crédito. |
| Personal Loan | VARCHAR(5) | Indica si el cliente tiene este tipo de crédito. |
| Home Equity Loan | VARCHAR(5) | Indica si el cliente tiene este tipo de crédito. |
