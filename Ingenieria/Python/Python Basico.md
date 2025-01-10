## 2. Variables y Tipos de Datos

### Variables
**Definición:** Espacio en memoria que almacena un valor que puede cambiar durante la ejecución del programa.

**Reglas de nombrado:**
- Debe comenzar con letra o guion bajo
- No puede comenzar con números
- Solo puede contener caracteres alfanuméricos y guion bajo
- Es sensible a mayúsculas/minúsculas

### Tipos de Datos Básicos

#### Números
```python
# Enteros (int)
edad = 25

# Flotantes (float)
precio = 19.99

# Operaciones básicas
suma = 5 + 3
resta = 10 - 4
multiplicacion = 6 * 2
division = 15 / 3
```

#### Texto (String)
```python
nombre = "Ana"
apellido = 'García'
texto_largo = """
Este es un texto
de múltiples líneas
"""

# Operaciones con strings
nombre_completo = nombre + " " + apellido
repeticion = "Hola " * 3  # Imprime "Hola Hola Hola"
```

#### Booleanos
```python
es_verdadero = True
es_falso = False

# Operaciones lógicas
and_operacion = True and False  # False
or_operacion = True or False    # True
not_operacion = not True       # False
```

#### Listas
```python
frutas = ["manzana", "banana", "naranja"]
numeros = [1, 2, 3, 4, 5]

# Operaciones con listas
frutas.append("pera")           # Añadir elemento
primer_fruta = frutas[0]        # Acceder a elemento
frutas.remove("banana")         # Eliminar elemento
longitud = len(frutas)          # Obtener longitud
```

#### Diccionarios
```python
persona = {
    "nombre": "Juan",
    "edad": 30,
    "ciudad": "Madrid"
}

# Operaciones con diccionarios
nombre = persona["nombre"]      # Acceder a valor
persona["profesion"] = "Developer"  # Añadir nuevo par clave-valor
del persona["ciudad"]          # Eliminar par clave-valor
```

## 3. Operadores

### Operadores Aritméticos
```python
a = 10
b = 3

suma = a + b        # 13
resta = a - b       # 7
multiplicacion = a * b   # 30
division = a / b        # 3.333...
modulo = a % b         # 1
potencia = a ** b      # 1000
division_entera = a // b  # 3
```

### Operadores de Comparación
```python
a = 5
b = 10

igual = a == b          # False
diferente = a != b      # True
mayor = a > b           # False
menor = a < b           # True
mayor_igual = a >= b    # False
menor_igual = a <= b    # True
```

### Operadores Lógicos
```python
x = True
y = False

and_operador = x and y   # False
or_operador = x or y     # True
not_operador = not x     # False
```

## 4. Funciones

**Definición:** Bloque de código reutilizable que realiza una tarea específica.

```python
# Función simple
def saludar(nombre):
    return f"Hola, {nombre}!"

# Función con múltiples parámetros
def calcular_promedio(numeros):
    return sum(numeros) / len(numeros)

# Función con parámetros por defecto
def crear_perfil(nombre, edad=18, ciudad="Desconocida"):
    return {
        "nombre": nombre,
        "edad": edad,
        "ciudad": ciudad
    }

# Ejemplos de uso
print(saludar("María"))  # Imprime: Hola, María!
notas = [15, 18, 13, 20]
print(calcular_promedio(notas))  # Imprime el promedio
perfil = crear_perfil("Juan", 25, "Madrid")
print(perfil)
```
