# Guía de Testing Manual

## Definición

El Testing Manual es un tipo de prueba de software donde los testers ejecutan casos de prueba paso a paso sin utilizar herramientas de automatización. El tester actúa como un usuario final para verificar todas las características del sistema bajo prueba.

## Tipos de Testing Manual

### 1. Testing Exploratorio

**Definición**: Pruebas donde el tester explora libremente la aplicación para encontrar defectos, aprendiendo sobre la aplicación mientras la prueba.

**Características**:
- No requiere planificación previa detallada
- Se basa en la experiencia del tester
- Es efectivo para encontrar defectos no obvios
- Útil cuando la documentación es limitada

**Ejemplo**:
```markdown
Sesión de Testing Exploratorio
Área: Módulo de Carrito de Compras
Duración: 60 minutos

Actividades realizadas:
1. Explorar diferentes formas de agregar productos
2. Intentar modificar cantidades de diferentes maneras
3. Probar límites de cantidad
4. Intentar acciones no convencionales

Hallazgos:
- Bug: El carrito no actualiza al modificar cantidad mediante teclado
- Mejora: No hay mensaje de confirmación al vaciar carrito
- Bug: Se permite agregar más productos que el stock disponible
```

### 2. Testing de Casos de Uso

**Definición**: Pruebas basadas en escenarios específicos de uso del sistema desde la perspectiva del usuario final.

**Características**:
- Sigue flujos de trabajo predefinidos
- Verifica requisitos funcionales
- Documenta paso a paso
- Incluye datos de prueba específicos

**Ejemplo**:
```markdown
Caso de Uso: Proceso de Checkout
ID: TC_CHECKOUT_001

Flujo Principal:
1. Usuario tiene productos en carrito
2. Usuario inicia proceso de checkout
3. Usuario completa información de envío
4. Usuario selecciona método de pago
5. Usuario confirma orden

Datos de Prueba:
- Productos: 2 items
- Dirección: Calle Principal 123
- Método de pago: Tarjeta de crédito

Criterios de Aceptación:
- Orden se crea correctamente
- Se envía email de confirmación
- Se actualiza el inventario
```

### 3. Testing de Usabilidad

**Definición**: Evaluación de qué tan fácil de usar y entender es la interfaz para los usuarios finales.

**Características**:
- Enfocado en la experiencia del usuario
- Evalúa la facilidad de uso
- Verifica la intuitividad de la interfaz
- Identifica problemas de navegación

**Ejemplo**:
```markdown
Prueba de Usabilidad
Tarea: Registro de nuevo usuario

Aspectos a evaluar:
1. Claridad de instrucciones
2. Facilidad de navegación
3. Mensajes de error comprensibles
4. Tiempo para completar registro

Observaciones:
- Los usuarios no encuentran fácilmente el botón de registro
- Mensajes de validación confusos
- Proceso requiere demasiados pasos
```

## Proceso de Testing Manual

### 1. Preparación

- Revisar requisitos
- Crear casos de prueba
- Preparar datos de prueba
- Configurar ambiente de pruebas

### 2. Ejecución

- Seguir casos de prueba paso a paso
- Documentar resultados
- Capturar evidencias
- Registrar defectos encontrados

### 3. Reporte

- Documentar resultados de pruebas
- Crear informes de defectos
- Realizar seguimiento
- Verificar correcciones

## Mejores Prácticas

### Documentación

1. **Casos de Prueba**:
   - Escribir pasos claros y concisos
   - Incluir precondiciones
   - Especificar resultados esperados
   - Mantener trazabilidad con requisitos

2. **Reporte de Defectos**:
   - Describir el problema claramente
   - Incluir pasos de reproducción
   - Adjuntar evidencias (screenshots)
   - Especificar severidad y prioridad

### Ejecución de Pruebas

1. **Ambiente**:
   - Usar datos de prueba controlados
   - Mantener el ambiente limpio
   - Documentar configuración
   - Verificar prerrequisitos

2. **Seguimiento**:
   - Mantener registro de pruebas ejecutadas
   - Actualizar estado de defectos
   - Realizar pruebas de regresión
   - Verificar correcciones

## Herramientas Comunes

1. **Gestión de Pruebas**:
   - TestRail
   - JIRA
   - Microsoft Test Manager
   - qTest

2. **Reporte de Defectos**:
   - JIRA
   - Bugzilla
   - Mantis
   - Azure DevOps

3. **Documentación**:
   - Confluence
   - SharePoint
   - Google Docs
   - Microsoft Office