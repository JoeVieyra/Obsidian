# Control de Versiones con Git

## 1. Conceptos Básicos

### ¿Qué es el Control de Versiones?
**Definición:** Sistema que registra los cambios realizados en un archivo o conjunto de archivos a lo largo del tiempo, permitiendo recuperar versiones específicas más adelante.

**Beneficios:**
- Historial completo de cambios
- Trabajo colaborativo
- Respaldo de código
- Gestión de versiones
- Resolución de conflictos

### Tipos de Sistemas de Control de Versiones
1. **Locales:** Almacenan cambios en la computadora local
2. **Centralizados:** Un servidor central almacena los cambios (SVN)
3. **Distribuidos:** Cada usuario tiene una copia completa del repositorio (Git)

## 2. Git Básico

### Configuración Inicial
```bash
# Configurar nombre de usuario
git config --global user.name "Tu Nombre"

# Configurar email
git config --global user.email "tu@email.com"

# Ver configuración actual
git config --list
```

### Estados de Git
1. **Working Directory:** Archivos en tu directorio de trabajo
2. **Staging Area:** Área de preparación para los cambios
3. **Repository:** Almacén de cambios confirmados

### Comandos Básicos

#### Iniciar un Repositorio
```bash
# Crear nuevo repositorio
git init

# Clonar repositorio existente
git clone https://github.com/usuario/repositorio.git
```

#### Gestionar Cambios
```bash
# Ver estado de archivos
git status

# Añadir archivos al staging area
git add archivo.txt          # Archivo específico
git add .                    # Todos los archivos

# Confirmar cambios (commit)
git commit -m "Mensaje descriptivo del cambio"

# Ver historial de commits
git log
git log --oneline           # Formato resumido
```

## 3. Branches (Ramas)

### Conceptos de Branching
**Definición:** Una rama representa una línea independiente de desarrollo.

**Usos comunes:**
- Desarrollo de nuevas funcionalidades
- Corrección de bugs
- Experimentos
- Versiones de producción

### Comandos de Branches
```bash
# Ver ramas existentes
git branch

# Crear nueva rama
git branch nueva-rama

# Cambiar a otra rama
git checkout otra-rama
# o
git switch otra-rama

# Crear y cambiar a nueva rama
git checkout -b nueva-rama
# o
git switch -c nueva-rama

# Eliminar rama
git branch -d rama-a-eliminar

# Fusionar ramas
git merge rama-a-fusionar
```

## 4. Trabajo Remoto

### Repositorios Remotos
**Definición:** Versiones de tu proyecto alojadas en Internet o red.

### Comandos para Trabajo Remoto
```bash
# Ver repositorios remotos
git remote -v

# Añadir repositorio remoto
git remote add origin https://github.com/usuario/repositorio.git

# Obtener cambios del remoto
git fetch origin
git pull origin main

# Enviar cambios al remoto
git push origin main
```

## 5. Pull Requests

### ¿Qué es un Pull Request?
**Definición:** Propuesta de cambios que un usuario hace a un repositorio, permitiendo la revisión de código antes de fusionar los cambios.

### Proceso de Pull Request
1. Fork del repositorio (si es necesario)
2. Crear rama para nuevos cambios
3. Realizar cambios y commits
4. Crear Pull Request
5. Revisión de código
6. Discusión y ajustes
7. Merge o cierre del PR

### Ejemplo de Flujo de Trabajo
```bash
# Fork y clon del repositorio
git clone https://github.com/tu-usuario/repositorio.git

# Crear rama para nueva característica
git checkout -b nueva-caracteristica

# Realizar cambios
git add .
git commit -m "Añade nueva característica"

# Subir cambios
git push origin nueva-caracteristica

# Crear Pull Request desde GitHub
```

## 6. Resolución de Conflictos

### ¿Qué es un Conflicto?
**Definición:** Situación que ocurre cuando Git no puede resolver automáticamente las diferencias entre dos commits.

### Resolución Manual
```bash
# Cuando ocurre un conflicto, el archivo mostrará:
<<<<<<< HEAD
código de tu rama actual
=======
código de la rama que intentas fusionar
>>>>>>> rama-a-fusionar

# Pasos para resolver:
1. Abrir archivos con conflictos
2. Decidir qué cambios mantener
3. Eliminar marcadores de conflicto
4. Hacer commit de los cambios resueltos
```

### Comandos Útiles para Conflictos
```bash
# Ver estado durante un conflicto
git status

# Abortar merge en caso de conflicto
git merge --abort

# Continuar merge después de resolver conflictos
git add .
git commit -m "Resuelve conflictos de merge"
```

## 7. Buenas Prácticas

### Commits
- Usar mensajes descriptivos
- Hacer commits pequeños y frecuentes
- Seguir convenciones de commit (conventional commits)

### Branches
- Mantener main/master limpia y estable
- Usar ramas para features/bugs
- Eliminar ramas después de merge
- Nombrar ramas descriptivamente

### Trabajo en Equipo
- Pull antes de push
- Revisar código antes de merge
- Documentar cambios importantes
- Mantener comunicación con el equipo
