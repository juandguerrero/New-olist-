# Análisis de Ventas y Logística del Marketplace Olist

**SQL Server · SQL · Power BI · ETL · Data Warehousing · Star Schema**

## Descripción General del Proyecto

**Olist** es un marketplace brasileño de comercio electrónico que conecta vendedores independientes con clientes en todo Brasil.

En lugar de operar como un minorista tradicional, Olist permite que múltiples vendedores ofrezcan productos a través de su ecosistema de marketplace. Esto genera datos transaccionales y operativos sobre **clientes, pedidos, productos, vendedores, pagos, reseñas, ubicaciones geográficas y entregas**.

El objetivo de este proyecto fue transformar estos datos fragmentados en una solución analítica estructurada capaz de responder preguntas clave sobre **rendimiento de ventas, productos, clientes, vendedores, geografía y logística**.

Construí una solución end-to-end utilizando **SQL Server y Power BI**, que abarca:

**Data Profiling → Modelado de Datos → ETL → Validación de Datos → Análisis SQL → Power BI → Insights de Negocio**

---

## Principales Hallazgos de Negocio

- Olist generó **R$13.22M en ingresos por productos** a través de **96,478 pedidos entregados**, con un **valor promedio por pedido de R$137.04**.
- El volumen de pedidos creció significativamente: **ene–ago de 2018 registró 52,783 pedidos frente a 21,998 durante el mismo período de 2017**, un incremento de aproximadamente **140%**.
- **Noviembre de 2017** fue el mes con mayor volumen de pedidos, con **7,289 pedidos**.
- **Health & Beauty** generó los mayores ingresos con **R$1.23M**, mientras que **Bed, Bath & Table** tuvo el mayor volumen de ventas con **10,953 artículos vendidos**.
- Las cinco principales categorías de productos generaron aproximadamente **40% de los ingresos totales del marketplace**.
- **São Paulo generó R$5.07M**, representando aproximadamente **38.3% de los ingresos totales**.
- São Paulo, Rio de Janeiro y Minas Gerais generaron en conjunto aproximadamente **63.4% de los ingresos del marketplace**, mostrando una fuerte concentración geográfica.
- El vendedor individual más grande generó aproximadamente **R$227K**, solo alrededor de **1.7% de los ingresos totales**, lo que indica que los ingresos por vendedor están relativamente diversificados.
- El tiempo promedio de entrega fue de **12 días**, con **7,826 pedidos retrasados** y una **tasa de entregas tardías de 8.11%**.

---

## Recomendaciones de Negocio

1. **Proteger las categorías de alto rendimiento**  
   Health & Beauty, Watches & Gifts, Bed, Bath & Table, Sports & Leisure y Computers & Accessories generan aproximadamente el 40% de los ingresos del marketplace.

2. **Evaluar tanto los ingresos como el volumen de ventas**  
   Las categorías con alto volumen no son necesariamente las de mayor valor. La estrategia de productos debería considerar ambas métricas.

3. **Reducir la concentración geográfica**  
   Con 38.3% de los ingresos provenientes de São Paulo y 63.4% de los tres estados más importantes, Olist debería explorar oportunidades de crecimiento en mercados regionales menos desarrollados.

4. **Investigar las entregas tardías**  
   Analizar las entregas tardías por vendedor, región y período para identificar los principales factores detrás de la **tasa de entregas tardías de 8.11%**.

5. **Monitorear el crecimiento del marketplace**  
   El volumen de pedidos creció fuertemente entre 2017 y 2018, pero la estabilización alrededor de 6,000–7,000 pedidos mensuales durante gran parte de 2018 debería ser monitoreada.

---

## Preguntas de Negocio Respondidas

### ¿Cuántos ingresos genera Olist?

Olist generó aproximadamente **R$13.22M en ingresos por productos** provenientes de **96,478 pedidos entregados**, con un **valor promedio por pedido de R$137.04**.

---

### ¿Cómo han cambiado las ventas a lo largo del tiempo?

El volumen de pedidos aumentó significativamente durante el período analizado.

- **Ene–Ago 2017:** 21,998 pedidos
- **Ene–Ago 2018:** 52,783 pedidos
- **Crecimiento:** aproximadamente 140%

El mes más fuerte fue **noviembre de 2017**, con **7,289 pedidos**.

Durante gran parte de 2018, el volumen mensual de pedidos se estabilizó alrededor de **6,000–7,000 pedidos**, después de la rápida expansión observada durante 2017.

---

### ¿Qué categorías de productos tienen el mejor rendimiento?

Las categorías con mayores ingresos fueron:

| Categoría de Producto | Ingresos |
|---|---:|
| Health & Beauty | R$1.23M |
| Watches & Gifts | R$1.17M |
| Bed, Bath & Table | R$1.02M |
| Sports & Leisure | R$954.9K |
| Computers & Accessories | R$888.7K |

En conjunto, estas categorías generaron aproximadamente **40% de los ingresos totales del marketplace**.

Los ingresos y el volumen de ventas también muestran resultados diferentes.

**Bed, Bath & Table** tuvo el mayor volumen con **10,953 artículos vendidos**, mientras que **Watches & Gifts** ocupó el segundo lugar en ingresos a pesar de ocupar solo el séptimo lugar en volumen.

Esto sugiere que Watches & Gifts genera considerablemente más ingresos por artículo vendido que algunas categorías con mayor volumen.

---

### ¿Qué regiones generan más ventas?

Los ingresos están fuertemente concentrados en el sureste de Brasil.

| Estado del Cliente | Ingresos |
|---|---:|
| São Paulo | R$5.07M |
| Rio de Janeiro | R$1.76M |
| Minas Gerais | R$1.55M |
| Rio Grande do Sul | R$728.9K |
| Paraná | R$666.1K |

**São Paulo por sí solo generó aproximadamente 38.3% de los ingresos totales del marketplace.**

São Paulo, Rio de Janeiro y Minas Gerais representaron en conjunto aproximadamente **63.4% de los ingresos**, demostrando una concentración geográfica significativa.

---

### ¿Qué vendedores generan más ingresos?

Los cinco vendedores con mayores ingresos generaron aproximadamente:

| Vendedor | Ingresos |
|---|---:|
| Vendedor 1 | R$227.0K |
| Vendedor 2 | R$217.9K |
| Vendedor 3 | R$196.9K |
| Vendedor 4 | R$190.9K |
| Vendedor 5 | R$186.6K |

En conjunto, los cinco principales vendedores generaron aproximadamente **7.7% de los ingresos totales del marketplace**.

Incluso el vendedor más grande representó solo alrededor de **1.7% de los ingresos totales**, lo que sugiere que los ingresos de Olist están relativamente diversificados entre su base de vendedores en lugar de depender de unos pocos.

---

### ¿Qué tan eficientemente se entregan los pedidos?

El tiempo promedio de entrega fue de **12 días**.

De **96,478 pedidos entregados**:

- **7,826 fueron entregados tarde**
- **8.11% no cumplieron con su fecha estimada de entrega**
- Aproximadamente **91.9% fueron entregados a tiempo**

Aunque la mayoría de los pedidos llegaron dentro del período estimado de entrega, casi **1 de cada 12 pedidos llegó tarde**, lo que convierte la confiabilidad de las entregas en un KPI operativo importante.

---

## Dashboard de Power BI

El dashboard final de Power BI proporciona una vista interactiva del **rendimiento de ventas, productos, geografía, vendedores y logística**.

![Olist Marketplace Power BI Dashboard](dashboard/Dashboards.jpg)

### KPIs Principales

- Ingresos Totales
- Pedidos Totales
- Valor Promedio por Pedido
- Tiempo Promedio de Entrega
- Pedidos Retrasados
- Tasa de Entregas Tardías

### Análisis del Dashboard

El dashboard permite a los usuarios explorar:

- Pedidos a lo largo del tiempo
- Ingresos por categoría de producto
- Pedidos por categoría de producto
- Ingresos por estado del cliente
- Ingresos por vendedor
- Rendimiento de entregas

Los filtros interactivos permiten realizar análisis por **Año, Categoría de Producto, Estado del Cliente y Estado del Vendedor**.

### Archivo de Power BI

El reporte interactivo completo de Power BI está disponible aquí:

[`dashboard/Dashboards.pbix`](dashboard/Dashboards.pbix)

---

## Arquitectura de la Solución

Todo el procesamiento de datos y desarrollo analítico se realizó en **SQL Server**, incluyendo **data profiling, limpieza de datos, transformación, ETL, data warehousing, modelado dimensional, validación de datos y análisis SQL**.

**Power BI** se utilizó como la capa final de visualización y reporting.

```text
Datasets CSV de Olist
        │
        ▼
SQL Server
        │
        ├── Data Profiling
        │
        ├── Limpieza y Transformación de Datos
        │
        ├── Pipeline ETL
        │
        ├── Data Warehouse
        │
        ├── Star Schema
        │
        ├── Validación de Datos
        │
        └── Análisis SQL
        │
        ▼
Power BI
        │
        ▼
Insights de Negocio
```

---

## Data Warehouse

Se diseñó un **Star Schema** dimensional para proporcionar un modelo preparado para análisis en SQL y Power BI.

```text
                 DimDate
                    │
                    │
DimCustomer ─── FactSales ─── DimProduct
                    │
                    │
                 DimSeller
```

### Tablas de Dimensiones

- `DimDate`
- `DimProduct`
- `DimSeller`
- `DimCustomer`

### Tabla de Hechos

- `FactSales`

La tabla de hechos contiene más de **110,000 registros de artículos de pedidos entregados** y almacena medidas que incluyen:

- Precio del Producto
- Valor del Flete
- Días de Entrega
- Indicador de Entrega Tardía

---

## Pipeline ETL

El pipeline ETL en SQL transforma los datos operacionales de Olist en el data warehouse dimensional.

Las principales transformaciones incluyen:

- Limpieza y estandarización de datos
- Traducción de categorías de productos de portugués a inglés
- Estandarización de nombres de ciudades
- Manejo de duplicados
- Generación de claves de fecha
- Mapeo de business keys a surrogate keys
- Cálculo del tiempo de entrega
- Creación del indicador de entrega tardía
- Filtrado de pedidos entregados

---

## Validación de Datos

El data warehouse fue validado antes de ser utilizado para reporting.

La validación incluyó:

- Comparación de conteos de filas entre la fuente y el data warehouse
- Reconciliación de ingresos
- Reconciliación del conteo de pedidos
- Detección de duplicados
- Verificaciones de integridad referencial
- Verificaciones de claves de dimensiones faltantes
- Validación del tiempo de entrega
- Validación de entregas tardías

Esto creó una capa adicional de control de calidad entre el pipeline ETL y el reporting en Power BI.

---

## Análisis SQL

La capa analítica calcula KPIs de negocio en las siguientes áreas:

**Ventas**
- Ingresos Totales
- Valor Promedio por Pedido
- Pedidos por Mes
- Ingresos por Categoría
- Ingresos por Estado
- Ingresos por Vendedor

**Clientes y Productos**
- Pedidos por Categoría
- Clientes por Estado
- Clientes Recurrentes

**Logística**
- Tiempo Promedio de Entrega
- Pedidos Retrasados
- Tasa de Entregas Tardías

---

## Stack Tecnológico

| Área | Tecnología |
|---|---|
| Base de Datos | SQL Server |
| Análisis de Datos | SQL / T-SQL |
| ETL | SQL / T-SQL |
| Data Warehousing | SQL Server |
| Modelado de Datos | Star Schema |
| Validación de Datos | SQL |
| Business Intelligence | Power BI |
| Control de Versiones | Git & GitHub |

---

## Estructura del Repositorio

```text
Olist/
│
├── dashboard/
│   ├── Dashboards.jpg
│   └── Dashboards.pbix
│
├── data/
│   └── Datasets CSV de Olist
│
├── sql/
│   ├── 01_data_profiling/
│   ├── 02_data_modeling/
│   ├── 03_etl/
│   ├── 04_validation/
│   └── 05_analytics/
│
└── README.md
```

---

## Resultado del Proyecto

Este proyecto transformó los datos fragmentados del marketplace Olist en un **data warehouse validado en SQL Server y una solución analítica interactiva en Power BI**.

La solución proporciona una vista consolidada de:

**Ingresos → Pedidos → Productos → Clientes → Geografía → Vendedores → Logística**

Más importante aún, el proyecto demuestra el flujo de trabajo analítico completo, desde **datos sin procesar y desarrollo ETL hasta análisis de negocio, validación de datos y reporting orientado a la toma de decisiones en Power BI**.
