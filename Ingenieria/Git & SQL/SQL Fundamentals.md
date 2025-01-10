 

## 1. SQL Fundamentals


### SELECT Queries
**Definición:** Comando usado para recuperar datos de una o más tablas.

```sql
-- Selección básica
SELECT * FROM usuarios;

-- Seleccionar columnas específicas
SELECT nombre, email FROM usuarios;

-- Usar WHERE para filtrar
SELECT * FROM usuarios WHERE edad > 18;

-- Ordenar resultados
SELECT * FROM usuarios ORDER BY nombre ASC;

-- Limitar resultados
SELECT * FROM usuarios LIMIT 10;

-- Funciones de agregación
SELECT 
    COUNT(*) as total_usuarios,
    AVG(edad) as edad_promedio,
    MAX(edad) as edad_maxima
FROM usuarios;
```

### INSERT Operaciones
**Definición:** Comando para agregar nuevos registros a una tabla.

```sql
-- Insertar un registro
INSERT INTO usuarios (nombre, email, edad) 
VALUES ('Juan', 'juan@email.com', 25);

-- Insertar múltiples registros
INSERT INTO usuarios (nombre, email, edad) VALUES 
    ('Ana', 'ana@email.com', 28),
    ('Carlos', 'carlos@email.com', 32);
```

### UPDATE Operaciones
**Definición:** Comando para modificar registros existentes.

```sql
-- Actualizar un registro
UPDATE usuarios 
SET email = 'nuevo@email.com' 
WHERE id = 1;

-- Actualizar múltiples campos
UPDATE usuarios 
SET 
    email = 'nuevo@email.com',
    edad = 26
WHERE nombre = 'Juan';
```

### DELETE Operaciones
**Definición:** Comando para eliminar registros.

```sql
-- Eliminar registros específicos
DELETE FROM usuarios WHERE id = 1;

-- Eliminar con condiciones múltiples
DELETE FROM usuarios 
WHERE edad < 18 AND status = 'inactivo';
```

### JOIN Operaciones
**Definición:** Permite combinar registros de dos o más tablas.

```sql
-- INNER JOIN
SELECT u.nombre, p.nombre as producto
FROM usuarios u
INNER JOIN pedidos p ON u.id = p.usuario_id;

-- LEFT JOIN
SELECT u.nombre, p.nombre as producto
FROM usuarios u
LEFT JOIN pedidos p ON u.id = p.usuario_id;

-- RIGHT JOIN
SELECT u.nombre, p.nombre as producto
FROM usuarios u
RIGHT JOIN pedidos p ON u.id = p.usuario_id;

-- FULL JOIN (no disponible en MySQL)
SELECT u.nombre, p.nombre as producto
FROM usuarios u
FULL JOIN pedidos p ON u.id = p.usuario_id;
```

