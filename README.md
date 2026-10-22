# TechStore — Práctica de SQL: Consultas Básicas y Alias de Columnas

## 1. Título y Objetivo
- **Título:** Práctica de SQL: Consultas Básicas y Alias de Columnas.
- **Objetivo:** Aplicar sentencias `SELECT` y definir alias de columna (`AS`) para consultar, proyectar y renombrar atributos de la base de datos de práctica, asegurando una salida clara y estandarizada para equipos técnicos y de negocio.

---

## 2. Tabla Consultada (`sales`)
La tabla **`sales`** almacena el registro de transacciones comerciales de TechStore. Sus principales campos son:

| Campo | Tipo de Dato | Descripción |
| :--- | :--- | :--- |
| `order_id` | INT | Identificador único de la orden (*Primary Key*). |
| `order_date` | DATE | Fecha en que se realizó la venta. |
| `customer_id` | INT | Identificador del cliente. |
| `product_id` | INT | Identificador único del producto. |
| `product_name` | VARCHAR | Nombre comercial del producto. |
| `quantity` | INT | Cantidad de unidades vendidas. |
| `total_amount` | DECIMAL | Monto total de la transacción. |

---

## 3. Preguntas Teóricas Obligatorias

### ¿Por qué es mala práctica usar `SELECT *` en producción?
Utilizar `SELECT *` en entornos de producción se considera una mala práctica por las siguientes razones técnicas:

1. **Rendimiento e Impacto en I/O:** Recupera todas las columnas de la tabla, incluyendo campos grandes o innecesarios. Esto incrementa la carga en la red, el consumo de memoria y la lectoescritura en disco (I/O).
2. **Mantenibilidad y Acoplamiento:** Si el esquema de la tabla cambia (por ejemplo, si se agregan, renombran o eliminan columnas), las aplicaciones backend o reportes dependientes pueden fallar al recibir una estructura de datos inesperada.
3. **Incapacidad de Aprovechar Índices (*Covering Indexes*):** Impide que el motor de la base de datos resuelva la consulta leyendo únicamente un índice secundario, forzando un acceso completo a la tabla (*Table Scan* / *Clustered Index Scan*).

---

### ¿Por qué son importantes los alias para un stakeholder no técnico?
Los alias (`AS`) permiten traducir identificadores técnicos o nombres de columnas en inglés hacia terminología clara y relevante para el negocio.

**Ejemplo concreto:**
Un usuario del área de finanzas que consulta un reporte o dashboard prefiere ver etiquetas comprensibles en lugar de nombres de base de datos:

```sql
-- Sin alias (Técnico / BD):
SELECT total_amount FROM sales; 
-- Resultado en la interfaz: total_amount

-- Con alias (Comprensible para Finanzas):
SELECT total_amount AS monto_total FROM sales;
-- Resultado en la interfaz: monto_total
