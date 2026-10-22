Práctica de SQL: Consultas Básicas y Alias de Columnas

1. Título y Objetivo

Título: Práctica de SQL: Consultas básicas y alias de columnas.
Objetivo: Aplicar sentencias SELECT y definir alias de columna (AS) para consultar, proyectar y renombrar atributos de las tablas de la base de datos de práctica, asegurando una salida clara, estructurada y estandarizada.

2. Tabla(s) Consultada(s)

Tabla: inventario (o productos)
Campos clave trabajados:
id_producto: Identificador único de cada artículo (Primary Key).
nombre_producto: Nombre descriptivo del producto.
precio: Valor monetario unitario del producto.
categoria: Categoría funcional a la que pertenece el producto.
stock_actual: Cantidad de unidades disponibles en almacén.

3. Preguntas Teórico-Prácticas Obligatorias

A. Razones técnicas para evitar SELECT * en entornos de producción
Rendimiento e I/O (Léctura de disco y transferencia de red): Al ejecutar SELECT *, la base de datos lee e impacta la red transmitiendo el 100% de los datos de todas las columna

Mantenibilidad y Fragilidad del Código: Si la estructura de la tabla cambia en la base de datos (por ejemplo, se añade, elimina o reordena una columna), las aplicaciones que dependan del orden estático de un SELECT * pueden sufrir fallos de mapeo de datos o romper la compatibilidad en sus interfaces/APIs.

Optimización de Índices (Covering Indexes): El motor de la base de datos no puede aprovechar al máximo los índices si se le exige devolver todas las columnas, forzando búsquedas adicionales en el almacenamiento principal (table scan o lookup) en lugar de responder directamente desde un índice secundario.

4. Consignas y Consultas Resueltas

Consigna 1: Selección básica de columnas

Descripción: Listar el identificador, nombre del producto y su precio unitario.

Consulta SQL:

SELECT 
    id_producto, 
    nombre_producto, 
    precio 
FROM inventario;

Consigna 2: Proyección y Renombrado con Alias (AS)

Descripción: Proyectar el catálogo con nombres estandarizados y amigables para reportes.

Consulta SQL:

SELECT 
    id_producto AS id,
    nombre_producto AS producto,
    precio AS precio_unitario,
    stock_actual AS stock
FROM inventario;

