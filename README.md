# SQL Select Fundamentals

Este repositorio contiene la solución al ejercicio práctico de consultas fundamentales en SQL (`SELECT`, `DISTINCT`, filtros y alias).

## Estructura del Proyecto
- `consultas_basicas.sql`: Fichero con los scripts y consultas SQL desarrolladas[cite: 4].
- `README.md`: Documentación y explicación del proyecto[cite: 4].

## Contenido de las Consultas
1. **Países de envío únicos:** Consulta realizada sobre el campo `pais_envio` mediante `DISTINCT`[cite: 4].
2. **Categorías y métodos de pago únicos:** Combinaciones únicas para análisis operacional[cite: 4].

-- =========================================================
-- REPOSiTORIO: sql-select-fundamentals
-- FICHERO: consultas_basicas.sql
-- =========================================================

-- Consulta 1: Valores Únicos de País de Envío
SELECT DISTINCT pais_envio 
FROM ventas;

-- Consulta 2: Combinaciones Únicas de Categoría y Método de Pago
SELECT DISTINCT categoria, metodo_pago 
FROM ventas;
