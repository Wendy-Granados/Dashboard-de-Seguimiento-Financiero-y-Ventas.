# Dashboard de Seguimiento Financiero y Ventas Power BI
Dashboard de Business Intelligence en Power BI para el análisis y seguimiento de ventas, facturación, pedidos, productos, tiendas y comisiones.

La solución integra información comercial y geográfica para facilitar el monitoreo del desempeño de las ventas y el análisis de resultados por período, tienda y producto.

# 📊 Seguimiento financiero y análisis de ventas

## 📌 Descripción

Desarrollo de un dashboard en Power BI orientado al seguimiento financiero y comercial de las ventas.

La solución permite consolidar información de pedidos, productos y tiendas para generar indicadores y visualizaciones que facilitan el análisis del desempeño comercial.

El tablero permite consultar información de ventas y facturación por diferentes dimensiones, principalmente:

- Tienda.
- Producto.
- Período.
- Pedidos.
- Comisiones.

También permite analizar la participación porcentual de las tiendas y productos dentro de la facturación.

---

## 🎯 Objetivo

Desarrollar una herramienta de Business Intelligence que permita:

- Monitorear el comportamiento de las ventas.
- Analizar las ventas por tienda.
- Identificar los productos con mayor participación.
- Dar seguimiento a la facturación por período.
- Analizar el porcentaje de facturación correspondiente a cada tienda y producto.
- Consultar el total de pedidos.
- Dar seguimiento a las comisiones.
- Facilitar la interpretación de información comercial mediante indicadores y visualizaciones interactivas.

El objetivo principal es transformar información operativa de ventas en información estructurada para facilitar el seguimiento y análisis del desempeño comercial.

---

## 💼 Problema de negocio

El seguimiento de información relacionada con ventas, productos, pedidos y tiendas puede requerir consultar diferentes conjuntos de datos para obtener una visión completa del desempeño comercial.

La dispersión de información dificulta:

- Consultar rápidamente las ventas.
- Comparar el desempeño entre tiendas.
- Identificar los productos con mayor participación.
- Analizar la evolución de la facturación.
- Consultar el volumen de pedidos.
- Dar seguimiento a las comisiones.
- Analizar la participación porcentual de tiendas y productos.

Por ello, se planteó la creación de un dashboard que concentrara los principales indicadores comerciales en una herramienta interactiva.

---

## 💡 Solución propuesta

Se desarrolló un modelo de datos en Power BI utilizando tres tablas principales:

### Productos

Contiene información relacionada con el catálogo de productos.

Campos principales:

- ID de producto.
- Descripción del producto.
- Link asociado al producto.

### RegistroVentas

Contiene el detalle de las operaciones de venta.

Campos principales:

- ID.
- Fecha del pedido.
- Código de tienda.
- ID de producto.
- Cantidad.
- Precio unitario.
- Ventas totales.

### Tiendas

Contiene información descriptiva y geográfica de las tiendas.

Campos principales:

- Código de tienda.
- Nombre de tienda.
- Ciudad.
- Nombre del estado.
- Siglas del estado.
- Latitud.
- Longitud.

La integración de estas tablas permite relacionar las operaciones de venta con la información descriptiva de los productos y las tiendas.

---

## 01. Proceso de análisis de datos

El desarrollo del dashboard contempla las siguientes etapas:

FUENTES DE DATOS  
↓  
EXTRACCIÓN  
↓  
PERFILAMIENTO  
↓  
LIMPIEZA Y TRANSFORMACIÓN  
↓  
VALIDACIÓN  
↓  
MODELADO  
↓  
CREACIÓN DE MÉTRICAS  
↓  
VISUALIZACIÓN  
↓  
VALIDACIÓN DE RESULTADOS  
↓  
ANÁLISIS E INSIGHTS

---

## 02. Perfilamiento inicial de los datos

Se realizó una revisión inicial de las fuentes de información para conocer su estructura y verificar que los campos fueran adecuados para el análisis.

El perfilamiento permitió identificar las principales características de las tablas y determinar la información necesaria para construir el modelo.

Se revisaron principalmente:

- Estructura de las tablas.
- Identificadores de productos.
- Identificadores de tiendas.
- Fechas de pedido.
- Cantidades.
- Precios unitarios.
- Ventas totales.
- Información geográfica de las tiendas.
- Campos utilizados para el análisis comercial.

---

## 03. Limpieza y transformación

### 3.1 Tipos de datos

Se revisaron los tipos de datos para garantizar que los campos pudieran utilizarse correctamente durante el modelado y la creación de métricas.

| Campo | Tipo esperado |
|---|---|
| ID_Producto | Texto / identificador |
| Fecha del pedido | Fecha |
| Cod-Tienda | Texto / identificador |
| Qte | Número |
| Precio_unitario | Decimal / moneda |
| Ventas_totales | Decimal / moneda |
| Latitud | Decimal |
| Longitud | Decimal |

La correcta definición de los tipos de datos permite realizar operaciones matemáticas, filtros y agrupaciones de manera consistente.

---

### 3.2 Valores nulos y vacíos

Se revisaron los valores nulos y vacíos presentes en las diferentes columnas.

La evaluación de estos valores debe considerar la función de cada campo dentro del modelo antes de eliminar registros o sustituir información.

Los identificadores de productos, tiendas y fechas requieren especial atención debido a su importancia para relacionar y analizar los registros.

---

### 3.3 Estandarización de nombres

Se revisaron y estandarizaron los nombres de los campos para facilitar su identificación y utilización durante el modelado y desarrollo de medidas.

Se utilizaron nombres descriptivos y consistentes para facilitar el mantenimiento del modelo.

---

### 3.4 Valores inconsistentes

Se revisaron los campos categóricos para detectar posibles diferencias de escritura, espacios, formatos o valores inconsistentes que pudieran afectar:

- Filtros.
- Agrupaciones.
- Relaciones.
- Visualizaciones.
- Cálculos.
- ---

## 04. Requerimientos de negocio

Los requerimientos del dashboard se enfocaron en proporcionar una visión consolidada del desempeño comercial y financiero.

| Requerimiento | Análisis |
|---|---|
| Seguimiento de ventas | Ventas totales y por dimensión |
| Análisis por tienda | Ventas y facturación por tienda |
| Análisis por producto | Ventas y facturación por producto |
| Seguimiento temporal | Facturación por mes/período |
| Participación | % de facturación por tienda y producto |
| Volumen comercial | Total de pedidos |
| Seguimiento financiero | Comisiones |

### Preguntas de negocio

El dashboard permite responder preguntas como:

- ¿Cuánto se ha vendido?
- ¿Qué tiendas concentran mayor volumen de ventas?
- ¿Qué productos tienen mayor participación?
- ¿Cómo evoluciona la facturación durante el período?
- ¿Qué porcentaje de la facturación corresponde a cada tienda?
- ¿Qué porcentaje corresponde a cada producto?
- ¿Cuántos pedidos se han registrado?
- ¿Qué monto de comisiones se ha generado?
---

## 05. Modelo de datos

El modelo está compuesto por tres tablas principales:

<img width="877" height="429" alt="image" src="https://github.com/user-attachments/assets/701d6d73-a70c-4bcc-84c8-91b03251e086" />


## 06. Métricas y KPIs

El dashboard contempla indicadores orientados al seguimiento comercial y financiero.

Facturación

Permite conocer el importe total generado por las operaciones de venta.

Facturación por período

Permite analizar el comportamiento de la facturación a través del tiempo, principalmente mediante una visualización mensual.

Tabla de visualización de Facturación por tienda y su %

Permite comparar el desempeño de las diferentes tiendas e identificar aquellas con mayor volumen de ventas.

Total de pedidos

Permite conocer el volumen de pedidos registrados durante el período analizado.

Comisiones

Permite realizar seguimiento a las comisiones asociadas a las operaciones comerciales.


### Filtros 

Producto
Permite seleccionar la participación de los diferentes productos dentro de las ventas.


## 07. Análisis y visualizaciones

El dashboard integra diferentes visualizaciones para facilitar el análisis de la información.

Ventas por tienda

La visualización permite comparar el desempeño de las tiendas y detectar diferencias en el volumen de ventas.

Ventas por producto

Permite identificar los productos que presentan mayor participación dentro de las ventas.

Facturación mensual

La evolución de la facturación se representa mediante una gráfica por período, permitiendo observar variaciones y tendencias en el comportamiento comercial.

Tabla de facturación

Se incorpora una tabla para complementar las visualizaciones y permitir una consulta más detallada de la información.

Participación porcentual

Se presentan indicadores de participación para analizar el porcentaje de facturación correspondiente a:

Tiendas.
Productos.
Pedidos

Se incorpora información relacionada con el total de pedidos para dimensionar el volumen de operaciones.

Comisiones

Se presenta información de las comisiones asociadas a las operaciones comerciales.

El campo Link permite conservar una referencia directa relacionada con el producto.

Información geográfica

La tabla de tiendas contiene:

Ciudad.
Estado.
Latitud.
Longitud.

Estos campos permiten incorporar una dimensión geográfica al análisis cuando se requiera.

## 08. Validación

Los resultados obtenidos mediante las métricas y visualizaciones deben ser contrastados con los registros de origen para verificar que los cálculos y agrupaciones correspondan con la información disponible.

La validación contempla principalmente:

Total de ventas.
Número de pedidos.
Facturación.
Ventas por tienda.
Ventas por producto.
Participación porcentual.
Información de las tiendas.
Información de los productos.

Casos de validación
Caso	Resultado esperado	Resultado Power BI	Validación
Total de ventas	Coincide con origen	Pendiente	⬜
Total de pedidos	Coincide con origen	Pendiente	⬜
Ventas por tienda	Coincide con origen	Pendiente	⬜
Ventas por producto	Coincide con origen	Pendiente	⬜
Facturación mensual	Coincide con origen	Pendiente	⬜
% por tienda	Cálculo correcto	Pendiente	⬜
% por producto	Cálculo correcto	Pendiente	⬜

Una vez realizadas las comprobaciones finales, esta tabla podrá completarse con los resultados reales.


## 09. Resultados e insights

El dashboard permite transformar los registros de pedidos en información útil para el seguimiento del desempeño comercial.

<img width="892" height="486" alt="image" src="https://github.com/user-attachments/assets/7aa1d3fc-cfc5-4a29-aa44-b85e8080f0ba" />

Entre los principales análisis que permite realizar se encuentran:

Identificación de tiendas con mayor volumen de ventas.
Identificación de productos con mayor participación.
Seguimiento de la evolución mensual de la facturación.
Análisis de la contribución porcentual de tiendas.
Análisis de la contribución porcentual de productos.
Seguimiento del volumen de pedidos.
Consulta de las comisiones asociadas a las operaciones.

Los resultados cuantitativos finales se incorporarán una vez concluida la validación de las métricas.

## 10. Limitaciones

La calidad y precisión del análisis dependen de la información disponible en las fuentes de origen.

Entre las principales consideraciones se encuentran:

Los resultados dependen de la calidad de los registros de pedidos.
Los identificadores de productos y tiendas deben mantenerse consistentes para garantizar las relaciones.
Los valores faltantes pueden afectar determinados análisis.
Las métricas dependen de la correcta definición de las reglas de cálculo.
La información disponible determina el nivel de detalle que puede analizarse.

El dashboard representa la información disponible en las fuentes utilizadas para el proyecto.

## 11. Mejoras futuras

Como posibles mejoras se consideran:

Automatización de la actualización de datos.
Incorporación de históricos de ventas.
Comparación contra períodos anteriores.
Indicadores de crecimiento.
Variación porcentual mensual.
Análisis de tendencias.
Incorporación de objetivos y cumplimiento.
Análisis geográfico de ventas.
Alertas para variaciones relevantes.
Integración con nuevas fuentes de información.
Automatización completa del proceso ETL.

## 12. Tecnologías
Power BI
Power Query
DAX
Modelado de datos
ETL
Análisis de ventas
Análisis financiero
KPIs
Visualización de datos
Business Intelligence





