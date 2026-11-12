# Proyecto_SQL_Caso_Cancelaciones_Hotel_BQH

Proyecto final del curso **SQL for Data Analyst** (Data Academy), desarrollado en Databricks (SQL) y versionado en GitHub.

**Autor:** Brandon Quispe

**Docente:** Christian Condori Nina

## Contexto del caso

El holding hotelero DataAndino (caso de estudio) descubrió que los contratos con agencias de marketing no contemplan las cancelaciones: el hotel paga USD 1.5 por cada reserva generada por la agencia (canal TA/TO), incluso si el huésped luego cancela. Además, cada cancelación con menos de 3 días de anticipación genera un costo operativo de USD 120.

**Objetivo:** cuantificar esta fuga de dinero y analizar el perfil de las reservas canceladas para ayudar a renegociar los contratos.

## Herramientas

- Databricks (SQL Editor y notebooks, cómputo Serverless)
- SQL (sintaxis Databricks): CTAS, INSERT, UPDATE, DELETE, CASE WHEN, funciones de fecha y texto, JOINs, agregaciones
- Python: carga del CSV y creación de la tabla
- Databricks Jobs: orquestación de las 4 notebooks
- Git / GitHub: control de versiones

## Hallazgos

- La fuga es grande y el mayor peso no es la comisión: las cancelaciones de último momento (USD 384,480) cuestan 6.4 veces más que las comisiones pagadas por reservas canceladas (USD 60,228).
- El canal TA/TO concentra las cancelaciones: 40,152 de las 44,224 (90.8%).
- El compromiso del cliente predice el riesgo: sin solicitudes especiales cancela el 47.72%, con 1 baja a 22.02% y con 3 a 17.86%. Sin cambios en la reserva cancela el 40.85%, con 1 a 3 cambios el 15.59%.
- Los hijos y el precio no son buenas señales: con hijos cancela 34.92% frente a 37.22% sin hijos, y el precio promedio de las canceladas es casi igual entre hoteles (USD 105.79 vs 104.69).
- El City Hotel concentra 3 veces más cancelaciones que el Resort Hotel (33,102 contra 11,122).

## Recomendaciones

- Renegociar el contrato con las agencias: pagar comisión solo por reservas efectivas, o exigir la devolución cuando la reserva se cancela.
- Endurecer la política de cancelación tardía: depósito o tarifa no reembolsable en reservas de último momento (USD 120 por caso).
- Gestionar de forma proactiva las reservas de mayor riesgo: las que no tienen solicitudes especiales ni cambios.
- Priorizar el City Hotel, donde se concentra la mayor cantidad de cancelaciones.
