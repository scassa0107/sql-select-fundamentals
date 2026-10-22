# Práctica de SQL: Consultas básicas y alias de columnas

## 1. Título y objetivo
* **Título:** Práctica de SQL: Consultas básicas y alias de columnas.
* **Objetivo:** Aplicar sentencias `SELECT` y definir alias de columna (`AS`) para consultar, proyectar y renombrar atributos de las tablas de la base de datos de práctica, asegurando una salida clara y estandarizada.

---

## 2. Tabla(s) consultada(s)
* **`inventario` (o `productos`):** Tabla que almacena el catálogo e información de productos.
* **Campos clave trabajados:**
  * `id_producto`: Identificador único de cada artículo ( Primary Key ).
  * `nombre_producto` / `product_name`: Nombre descriptivo del producto.
  * `precio` / `price`: Valor monetario unitario del producto.
  * `categoria`: Categoría funcional a la que pertenece cada artículo[cite: 5].
  * `stock_actual`: Unidades disponibles en almacén[cite: 5].

---

## 3. Consignas y consultas resueltas

### Consigna 1: Selección básica de columnas
* **Qué pide la consulta:** Listar el identificador, nombre del producto y su precio unitario de la tabla de inventario.
* **Solución / Explicación:** Se seleccionan directamente las columnas requeridas utilizando la sentencia `SELECT` proyectando los datos originales.
  ```sql
  SELECT id_producto, nombre_producto, precio 
  FROM inventario;

  
