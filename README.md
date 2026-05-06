# ConnectaTel — Análisis de Clientes y Uso

## Descripción del Proyecto

Este proyecto analiza el comportamiento de los clientes de ConnectaTel, con foco en la relación entre segmentación de usuarios, patrones de uso (mensajes, llamadas y minutos) y tipo de plan (Básico vs Premium).

El objetivo es generar insights accionables que apoyen la toma de decisiones en producto, pricing y estrategia comercial.

---

## Objetivos

- Limpiar y preparar datos con problemas de calidad
- Identificar patrones de uso por cliente
- Segmentar usuarios por comportamiento y edad
- Detectar outliers relevantes
- Traducir resultados en recomendaciones de negocio


---

## Problemas detectados en los datos

- Valores faltantes en `city` (~11.7%)
- Valores faltantes en `churn_date` (~88%), interpretados como usuarios activos
- Nulos estructurales en `duration` y `length` dependiendo de `type`
- Valores inválidos en `age` (por ejemplo, -999)
- Fechas fuera de rango (por ejemplo, 2026)

Estrategias aplicadas:
- Conversión de tipos (numéricos y fechas)
- Reemplazo de valores sentinela
- Imputación con mediana
- Validación de consistencia
- Tratamiento de nulos según contexto del negocio

---

## Metodología

1. Data Cleaning
   - Conversión de tipos
   - Manejo de nulos y valores inválidos
   - Validación de consistencia

2. Feature Engineering
   - Agregación de uso por usuario
   - Creación de variables:
     - `cant_mensajes`
     - `cant_llamadas`
     - `cant_minutos_llamada`
     - `grupo_uso`
     - `grupo_edad`

3. Exploratory Data Analysis (EDA)
   - Análisis de distribuciones
   - Comparación por tipo de plan
   - Segmentación de usuarios

4. Detección de Outliers
   - Visualización con boxplots
   - Método IQR
   - Evaluación de impacto en el negocio

---

## Insights Clave

- La edad no explica de forma significativa la elección de plan
- El nivel de uso es el principal factor diferenciador entre usuarios
- El plan Premium concentra proporcionalmente más usuarios intensivos
- Existe una cola larga de usuarios con alto consumo
- Los outliers representan comportamiento real, no errores de datos

---

## Segmentación

Por nivel de uso:
- Bajo uso
- Uso medio
- Alto uso

Por edad:
- Joven
- Adulto
- Mayor

---

## Recomendaciones

- Mantener planes simples y económicos para usuarios de bajo uso
- Diseñar estrategias de upgrade hacia Premium para usuarios de uso medio
- Crear planes o beneficios adicionales para usuarios de alto consumo
- Analizar a los usuarios intensivos como segmento de alto valor
- Implementar estrategias de retención y upsell basadas en comportamiento

---

## Tecnologías utilizadas

- Python
- Pandas
- NumPy
- Seaborn
- Matplotlib
