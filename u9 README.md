# RetailPro – Análisis de Ventas con SQL

Proyecto desarrollado en el curso de Data Analytics. A partir de la base de datos de ventas de una tienda de tecnología, se crean las tablas, se responden preguntas de negocio con SQL y se arma la vista que después alimenta el dashboard de Power BI.

## Herramientas utilizadas

- **SQL Server** + **SQL Server Management Studio (SSMS)**
- Power BI Desktop
- Git y GitHub

## Modelo de datos

Base de datos: `TechStoreU3`

| Tabla | Contenido | Clave |
|---|---|---|
| `categorias` | 4 categorías de producto | `id_categoria` |
| `clientes` | 5 clientes con ciudad y fecha de registro | `id_cliente` |
| `productos` | 6 productos con precio y stock | `id_producto` (FK a `categorias`) |
| `ventas` | 10 ventas de marzo 2024 | `id_venta` (FK a `clientes` y `productos`) |

## Scripts del proyecto

Los scripts SQL están en el repositorio [crmaronna/entrega4](https://github.com/crmaronna/entrega4):

| Archivo | Módulo | Descripción |
|---|---|---|
| `ventas_tech_db.sql` | M3 | Crea la base `TechStoreU3`, las 4 tablas (DROP / CREATE) e inserta los datos |
| `m4_consultas_negocio..sql` | M4 | Resumen mensual, ranking de productos, clientes recurrentes y comparación contra el promedio |
| `m5_consultas_joins.sql` | M5 | Vista base con INNER JOIN, clientes y productos sin ventas (LEFT JOIN) y consolidado con UNION ALL |

## Cómo ejecutar los scripts

Los scripts usan sintaxis de SQL Server (`USE`, `GO`, `TOP`, `dbo.`), por lo que **no corren en MySQL ni PostgreSQL** sin adaptarlos.

1. Descargá los scripts desde [crmaronna/entrega4](https://github.com/crmaronna/entrega4).
2. Abrí **SSMS** y conectate a tu instancia de SQL Server.
3. Abrí y ejecutá `ventas_tech_db.sql` (F5). Este script **ya crea la base `TechStoreU3`**, no hace falta crearla antes.
4. Después ejecutá, en este orden, `m4_consultas_negocio..sql` y `m5_consultas_joins.sql`.

El orden importa: las tablas tienen claves foráneas, así que las consultas fallan si la base no fue creada y cargada primero.

## Autor

Martín Maronna – Data Analytics, 2026
