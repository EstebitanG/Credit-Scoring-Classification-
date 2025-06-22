Diccionario de datos para proyecto de Credit Scoring

Descripción General

Se detallan las columnas existentes en los dataset (train.csv y test.csv), las cuales fueron procesadas para el posterior entrenamiento de modelos.

1. Train.csv

Propósito: almacena datos de panel sobre clientes de una entidad finaciera. Los datos corresponden a información sociodemográfica básica y de comportamiento de crédito histórica.

Columnas:

| Columna | Tipo de Dato (Python) | Descripción |
| --- | --- | --- |
| ID | object | Código identificador del registro, distinto al Customer_ID (ej: '0x160a'). |
| Customer_ID | object | Identificador único del cliente, que puede repetirse por mes (ej: 'CUS_0xd40'). |
| Month | object | Mes del registro (ej: 'August'). Útil para trabajar con datos de panel. |
| Name | object | Nombre completo del cliente. |
| Age | float64 | Edad del cliente. |
| SSN | object | Número de Seguridad Social del cliente. |
| Occupation | object | Ocupación u oficio del cliente. Contiene múltiples categorías laborales. |
| Annual_Income | float64 | Ingreso anual del cliente en dólares. |
| Monthly_Inhand_Salary | float64 | Ingreso mensual neto del cliente, en dólares. |
| Num_Bank_Accounts | int64 | Número de cuentas bancarias que tiene el cliente. |
| Num_Credit_Card | int64 | Número de tarjetas de crédito activas del cliente. |
| Interest_Rate | int64 | Tasa de interés asignada al cliente. |
| Num_of_Loan | float64 | Número de créditos vigentes del cliente. |
| Delay_from_due_date | int64 | Retraso en días desde la fecha de vencimiento de pago. |
| Num_of_Delayed_Payment | float64 | Número de pagos atrasados en el historial del cliente. |
| Changed_Credit_Limit | float64 | Cambios en el límite de crédito. Puede representar una variación relativa o pequeña en términos absolutos. |
| Num_Credit_Inquiries | float64 | Número de consultas de crédito realizadas por instituciones financieras. |
| Credit_Mix | object | Diversificación de tipos de crédito. Categorías: Good, Standard, Bad. |
| Outstanding_Debt | float64 | Saldo total de deuda pendiente del cliente, en dólares. |
| Credit_Utilization_Ratio | float64 | Ratio de utilización de crédito: (saldo pendiente / límite total) * 100. Normalmente entre 25% y 45%. |
| Credit_History_Age | float64 | Antigüedad del historial crediticio en meses (procesado desde su forma original texto con años y meses). |
| Payment_of_Min_Amount | object | Si el cliente paga el mínimo en sus tarjetas. Valores: Yes, No, NM (Not Mentioned). |
| Total_EMI_per_month | float64 | Cuotas mensuales totales pagadas por el cliente (capital + intereses). |
| Amount_invested_monthly | float64 | Monto ahorrado mensualmente por el cliente, en dólares. |
| Payment_Behaviour | object | Comportamiento de pago. Ej: 'Low_spent_Small_value_payments'. |
| Monthly_Balance | float64 | Saldo promedio mensual en cuenta corriente, en dólares. |
| Credit_Score | object | Etiqueta del puntaje crediticio. Clases: Poor, Standard, Good. (Variable objetivo). |

### Columnas derivadas del split de Type_of_loan

Dentro del proyecto, es necesario hacer una subdivisión de la columna 'Type_of_Loan', la cual es multivalor. Sin embargo, las nuevas columnas creadas no corresponden a una variable binaria (bool), más bien es object, para incluir los casos desconocidos ('Unknown'). Cada nombre de la columna especifica el tipo de crédito.

| Columna | Tipo de Dato (Python) | Descripción |
| --- | --- | --- |
| Payday Loan | object | Indica si el cliente tiene este tipo de crédito. |
| Auto Loan | object | Indica si el cliente tiene este tipo de crédito. |
| Credit-Builder Loan | object | Indica si el cliente tiene este tipo de crédito. |
| Debt Consolidation Loan | object | Indica si el cliente tiene este tipo de crédito. |
| Student Loan | object | Indica si el cliente tiene este tipo de crédito. |
| Mortgage Loan | object | Indica si el cliente tiene este tipo de crédito. |
| Personal Loan | object | Indica si el cliente tiene este tipo de crédito. |
| Home Equity Loan | object | Indica si el cliente tiene este tipo de crédito. |
| Not Specified | object | Presencia de préstamos sin especificación clara. |

### Test.csv

Las columnas de test.csv son exactamente las mismas que train.csv, a excepción de una: 'Credit_Score', la cual es inexistente en este dataset, justamente al ser la variable objetivo (y) que buscamos predecir.
