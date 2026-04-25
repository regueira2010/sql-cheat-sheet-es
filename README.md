# 📊 SQL Quick Reference Guide

¡Bienvenido a esta guía rápida de SQL! Este repositorio sirve como un manual de referencia esencial para desarrolladores y analistas de datos. Cubre desde funciones avanzadas hasta los comandos fundamentales del lenguaje.

---

## ⚡ 1. Window Functions
Las funciones de ventana permiten realizar cálculos a través de un conjunto de filas que están relacionadas con la fila actual.

| Función | Descripción |
| :--- | :--- |
| `OVER()` | Define la ventana (partición y orden) sobre la cual se aplica la función. |
| `ROW_NUMBER()` | Asigna un número secuencial único a cada fila. |
| `RANK()` | Asigna un rango con huecos si hay valores duplicados. |
| `DENSE_RANK()` | Asigna un rango sin huecos si hay valores duplicados. |
| `NTILE(n)` | Divide el resultado en `n` grupos iguales. |
| `LAG()` | Accede a datos de una fila anterior. |
| `LEAD()` | Accede a datos de una fila posterior. |

> **💡 Buena práctica:** Usa `PARTITION BY` dentro de `OVER()` para segmentar tus cálculos sin necesidad de un `GROUP BY`.

---

## 📈 2. Funciones de Agregación
Utilizadas para realizar cálculos matemáticos sobre múltiples filas y devolver un único valor.

* `AVG()`: Promedio.
* `SUM()`: Suma total.
* `COUNT()`: Conteo de registros.
* `MIN()`: Valor mínimo.
* `MAX()`: Valor máximo.

---

## 🔍 3. WHERE (Filtros Avanzados)
Controla qué registros son afectados o seleccionados.

### Operadores Lógicos y de Comparación
* **Básicos:** `<`, `>`, `<=`, `>=`, `=`, `<>` (o `!=`).
* **Lógicos:** `AND`, `OR`, `NOT`.
* **Rangos:** `BETWEEN valor1 AND valor2`.
* **Patrones:** `LIKE` (ej: `LIKE 'A%'` para empezar con A).
* **Listas:** `IN (valor1, valor2)`.
* **Subconsultas:** `ANY`, `ALL`, `EXISTS`.

---

## 🛠️ 4. Sub-lenguajes SQL

### DML (Data Manipulation Language)
* `SELECT`: Recupera datos.
* `INSERT`: Inserta nuevos registros.
* `UPDATE`: Modifica registros existentes.
* `DELETE`: Elimina registros.

### DCL (Data Control Language)
* `GRANT`: Concede privilegios de acceso al usuario.
* `REVOKE`: Retira los privilegios de acceso.

### TCL (Transaction Control Language)
* `COMMIT`: Guarda permanentemente los cambios.
* `ROLLBACK`: Revierte los cambios desde el último COMMIT.
* `SAVEPOINT`: Crea puntos intermedios dentro de una transacción.

### DDL (Data Definition Language)
* `CREATE`: Crea tablas, bases de datos o índices.
* `DROP`: Elimina objetos de la base de datos (estructura completa).
* `TRUNCATE`: Vacía el contenido de una tabla pero mantiene la estructura.
* `ALTER`: Modifica la estructura de un objeto (agregar columnas, cambiar tipos).

---

## 🔒 5. Constraints (Restricciones)
Aseguran la integridad de los datos en nuestras tablas.

* `PRIMARY KEY`: Identificador único de la fila.
* `FOREIGN KEY`: Enlace entre dos tablas.
* `NOT NULL`: No permite valores nulos.
* `UNIQUE`: Asegura que todos los valores sean distintos.
* `CHECK`: Valida que los valores cumplan una condición específica.
* `DEFAULT`: Asigna un valor predeterminado si no se especifica uno.

---

## 📑 6. Otros Comandos y Clausulas
* **ALIAS (`AS`):** Renombrar columnas o tablas temporalmente para mejorar legibilidad.
* **GROUP BY:** Agrupa filas que tienen los mismos valores en columnas específicas.
* **HAVING:** Similar a `WHERE`, pero se aplica a grupos creados por `GROUP BY`.
* **ORDER BY:** Ordena los resultados (`ASC` por defecto, `DESC` para descendente).
* **JOINS:** * `INNER JOIN`: Registros con valores coincidentes en ambas tablas.
    * `LEFT JOIN`: Todos los de la tabla izquierda + coincidencias de la derecha.
    * `RIGHT JOIN`: Todos los de la tabla derecha + coincidencias de la izquierda.
    * `FULL JOIN`: Todos los registros cuando hay una coincidencia en cualquiera de las tablas.

---

## ✅ Buenas Prácticas Generales
1.  **Escribe las palabras clave en MAYÚSCULAS** y los nombres de tablas/columnas en minúsculas (ej: `SELECT name FROM users`).
2.  **Usa Alias** para que tus consultas sean más legibles, especialmente en JOINs.
3.  **Evita el `SELECT *`**: Selecciona solo las columnas que realmente necesitas para optimizar el rendimiento.
4.  **Formatea tu código**: Usa indentación para separar las cláusulas (`SELECT`, `FROM`, `WHERE`).
5.  **Comenta tu código**: Usa `--` para comentarios de una línea y `/* ... */` para bloques.
6.  **Usa Transacciones**: Antes de un `UPDATE` o `DELETE` masivo, usa `BEGIN TRANSACTION` y verifica antes de hacer `COMMIT`.

---
