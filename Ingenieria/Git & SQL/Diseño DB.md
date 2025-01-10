## 2. Diseño de Bases de Datos

### Modelado de Datos

#### Entidades y Atributos
**Definición:** Una entidad representa un objeto o concepto del mundo real, y los atributos son sus características.

Ejemplo de entidad Usuario:
```sql
CREATE TABLE usuarios (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    edad INT,
    fecha_registro DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

#### Relaciones
**Definición:** Conexiones lógicas entre entidades.

**Tipos de Relaciones:**
1. **Uno a Uno (1:1)**
```sql
CREATE TABLE usuarios (
    id INT PRIMARY KEY,
    nombre VARCHAR(100)
);

CREATE TABLE perfiles (
    id INT PRIMARY KEY,
    usuario_id INT UNIQUE,
    biografia TEXT,
    FOREIGN KEY (usuario_id) REFERENCES usuarios(id)
);
```

2. **Uno a Muchos (1:N)**
```sql
CREATE TABLE categorias (
    id INT PRIMARY KEY,
    nombre VARCHAR(100)
);

CREATE TABLE productos (
    id INT PRIMARY KEY,
    nombre VARCHAR(100),
    categoria_id INT,
    FOREIGN KEY (categoria_id) REFERENCES categorias(id)
);
```

3. **Muchos a Muchos (N:M)**
```sql
CREATE TABLE estudiantes (
    id INT PRIMARY KEY,
    nombre VARCHAR(100)
);

CREATE TABLE cursos (
    id INT PRIMARY KEY,
    nombre VARCHAR(100)
);

CREATE TABLE estudiantes_cursos (
    estudiante_id INT,
    curso_id INT,
    fecha_inscripcion DATE,
    PRIMARY KEY (estudiante_id, curso_id),
    FOREIGN KEY (estudiante_id) REFERENCES estudiantes(id),
    FOREIGN KEY (curso_id) REFERENCES cursos(id)
);
```

### Normalización

#### Primera Forma Normal (1NF)
**Reglas:**
- Valores atómicos
- Sin grupos repetitivos
- Clave primaria única

```sql
-- Mal diseño
CREATE TABLE pedidos (
    id INT PRIMARY KEY,
    productos VARCHAR(200) -- "producto1, producto2, producto3"
);

-- Buen diseño (1NF)
CREATE TABLE pedidos (
    id INT PRIMARY KEY,
    producto_id INT,
    cantidad INT
);
```

#### Segunda Forma Normal (2NF)
**Reglas:**
- Debe estar en 1NF
- Sin dependencias parciales

```sql
-- Mal diseño
CREATE TABLE pedidos (
    producto_id INT,
    cliente_id INT,
    producto_nombre VARCHAR(100),
    PRIMARY KEY (producto_id, cliente_id)
);

-- Buen diseño (2NF)
CREATE TABLE productos (
    id INT PRIMARY KEY,
    nombre VARCHAR(100)
);

CREATE TABLE pedidos (
    id INT PRIMARY KEY,
    producto_id INT,
    cliente_id INT,
    FOREIGN KEY (producto_id) REFERENCES productos(id)
);
```

#### Tercera Forma Normal (3NF)
**Reglas:**
- Debe estar en 2NF
- Sin dependencias transitivas

```sql
-- Mal diseño
CREATE TABLE empleados (
    id INT PRIMARY KEY,
    departamento_id INT,
    departamento_nombre VARCHAR(100),
    departamento_ubicacion VARCHAR(100)
);

-- Buen diseño (3NF)
CREATE TABLE departamentos (
    id INT PRIMARY KEY,
    nombre VARCHAR(100),
    ubicacion VARCHAR(100)
);

CREATE TABLE empleados (
    id INT PRIMARY KEY,
    departamento_id INT,
    FOREIGN KEY (departamento_id) REFERENCES departamentos(id)
);
```

### Claves y Restricciones

```sql
-- Clave Primaria
CREATE TABLE usuarios (
    id INT PRIMARY KEY,
    email VARCHAR(100) UNIQUE
);

-- Clave Foránea
CREATE TABLE pedidos (
    id INT PRIMARY KEY,
    usuario_id INT,
    FOREIGN KEY (usuario_id) REFERENCES usuarios(id)
);

-- Restricciones
CREATE TABLE productos (
    id INT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2) CHECK (precio > 0),
    stock INT DEFAULT 0
);
```

### Índices
**Definición:** Estructuras que mejoran la velocidad de recuperación de datos.

```sql
-- Índice Simple
CREATE INDEX idx_nombre ON usuarios(nombre);

-- Índice Compuesto
CREATE INDEX idx_nombre_email ON usuarios(nombre, email);

-- Índice Único
CREATE UNIQUE INDEX idx_email ON usuarios(email);
```

### CRUD Operaciones
Ejemplo completo de operaciones CRUD:

```sql
-- Crear tabla
CREATE TABLE productos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nombre VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2),
    categoria_id INT,
    FOREIGN KEY (categoria_id) REFERENCES categorias(id)
);

-- Create (Crear)
INSERT INTO productos (nombre, precio, categoria_id)
VALUES ('Laptop', 999.99, 1);

-- Read (Leer)
SELECT p.*, c.nombre as categoria
FROM productos p
JOIN categorias c ON p.categoria_id = c.id
WHERE p.precio > 500;

-- Update (Actualizar)
UPDATE productos
SET precio = precio * 1.1
WHERE categoria_id = 1;

-- Delete (Eliminar)
DELETE FROM productos
WHERE id = 1;
```
