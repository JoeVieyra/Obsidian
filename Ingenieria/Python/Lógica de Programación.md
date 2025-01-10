# Fundamentos de Programación

## 1. Lógica de Programación

### Algoritmos básicos
**Definición:** Un algoritmo es una secuencia ordenada de pasos finitos y no ambiguos que resuelven un problema específico.

**Características principales:**
- Debe ser preciso
- Debe estar bien definido
- Debe ser finito
- Debe producir un resultado

**Ejemplo:**
Algoritmo para hacer un sándwich:
1. Inicio
2. Tomar dos rebanadas de pan
3. Tomar los ingredientes (jamón, queso, lechuga)
4. Colocar una rebanada de pan como base
5. Añadir el jamón
6. Añadir el queso
7. Añadir la lechuga
8. Colocar la segunda rebanada de pan encima
9. Fin

### Pseudocódigo
**Definición:** Es una forma de escribir algoritmos en un lenguaje informal que puede ser entendido por cualquier programador.

**Ejemplo:**
```
INICIO
   DEFINIR numero1, numero2, suma COMO ENTERO
   ESCRIBIR "Ingrese el primer número:"
   LEER numero1
   ESCRIBIR "Ingrese el segundo número:"
   LEER numero2
   suma = numero1 + numero2
   ESCRIBIR "La suma es:", suma
FIN
```

### Diagramas de Flujo
**Definición:** Representación gráfica de un algoritmo utilizando símbolos estandarizados conectados por flechas.

**Símbolos comunes:**
- Óvalo: Inicio/Fin
- Rectángulo: Proceso
- Rombo: Decisión
- Paralelogramo: Entrada/Salida

### Estructuras de Control

#### 1. Secuencial
**Definición:** Ejecución de instrucciones una después de otra.

**Ejemplo en Python:**
```python
nombre = input("Ingrese su nombre: ")
edad = int(input("Ingrese su edad: "))
print(f"Hola {nombre}, tienes {edad} años")
```

#### 2. Condicional (Selectiva)
**Definición:** Permite ejecutar diferentes bloques de código según una condición.

**Ejemplo en Python:**
```python
edad = int(input("Ingrese su edad: "))
if edad >= 18:
    print("Eres mayor de edad")
else:
    print("Eres menor de edad")
```

#### 3. Iterativa (Bucles)
**Definición:** Permite repetir un bloque de código mientras se cumpla una condición.

**Ejemplo en Python:**
```python
# Bucle while
contador = 1
while contador <= 5:
    print(f"Vuelta {contador}")
    contador += 1

# Bucle for
for i in range(5):
    print(f"Iteración {i+1}")
```

