# Guía esencial de Git y colaboración con forks

## Introducción

Esta guía te ayudará a dominar los comandos básicos de Git y aprender a colaborar efectivamente usando forks en plataformas como GitHub. Perfecto para estudiantes y desarrolladores que quieren trabajar en proyectos colaborativos.

## 1. Configuración inicial de Git

Antes de comenzar, configura tu identidad en Git:

```bash
git config --global user.name "Tu nombre completo"
git config --global user.email "tu.email@universidad.edu"
```

**Nota:** Solo necesitas hacer esto una vez por máquina.

## 2. Entendiendo los forks

### ¿Qué es un fork?

Un **fork** es una copia personal de un repositorio que te permite:

- Trabajar libremente sin afectar el proyecto original
- Experimentar con nuevas funcionalidades
- Contribuir al proyecto mediante pull requests

### Cómo hacer un fork

1. Ve al repositorio original en GitHub
2. Haz clic en el botón **"Fork"** (esquina superior derecha)
3. Selecciona tu cuenta como destino
4. ¡Listo! Ahora tienes tu propia copia

## 3. Clonando tu fork

Descarga tu fork a tu máquina local:

```bash
git clone https://github.com/TU_USUARIO/nombre-del-repo.git
cd nombre-del-repo
```

## 4. Comandos esenciales de Git

### Verificar el estado de tus archivos

```bash
git status
```

Muestra qué archivos han sido modificados, agregados o eliminados.

### Agregar archivos al staging area

```bash
# Agregar un archivo específico
git add nombre_del_archivo

# Agregar todos los archivos modificados
git add .

# Agregar archivos de forma interactiva
git add -p
```

### Crear un commit

```bash
git commit -m "Descripción clara de los cambios realizados"
```

**Consejo:** Usa mensajes descriptivos que expliquen qué cambios hiciste y por qué.

### Enviar cambios a tu fork

```bash
git push origin main
```

## 5. Manteniendo tu fork actualizado

### Agregar el repositorio original como upstream

```bash
git remote add upstream https://github.com/PROFESOR/nombre-del-repo.git
```

### Obtener los últimos cambios del profesor

```bash
# Descargar cambios sin fusionarlos
git fetch upstream

# Fusionar cambios en tu rama principal
git merge upstream/main

# O usar pull para hacer ambas cosas
git pull upstream main
```

## 6. Trabajando con ramas

### Crear una nueva rama

```bash
git checkout -b nombre-de-la-rama
```

### Cambiar entre ramas

```bash
git checkout nombre-de-la-rama
```

### Ver todas las ramas

```bash
git branch
```

### Fusionar una rama

```bash
git checkout main
git merge nombre-de-la-rama
```

## 7. Comandos útiles adicionales

### Ver el historial de commits

```bash
git log --oneline
```

### Ver diferencias entre versiones

```bash
git diff
```

### Deshacer cambios

```bash
# Deshacer cambios en archivos no commited
git checkout -- nombre_del_archivo

# Deshacer el último commit (manteniendo cambios)
git reset --soft HEAD~1

# Deshacer el último commit (eliminando cambios)
git reset --hard HEAD~1
```

## 8. Flujo de trabajo recomendado

1. **Antes de empezar:** `git pull upstream main`
2. **Crear rama:** `git checkout -b mi-tarea`
3. **Trabajar:** Edita tus archivos
4. **Verificar:** `git status` y `git diff`
5. **Agregar cambios:** `git add .`
6. **Commit:** `git commit -m "Descripción"`
7. **Subir:** `git push origin mi-tarea`
8. **Crear Pull Request:** Desde GitHub

## 9. Resolución de conflictos

Cuando hay conflictos al fusionar:

1. Git te mostrará los archivos conflictivos
2. Edita los archivos y resuelve los conflictos manualmente
3. Agrega los archivos resueltos: `git add nombre_del_archivo`
4. Completa la fusión: `git commit`

## 10. Mejores prácticas

- ✅ Haz commits frecuentes con mensajes claros
- ✅ Usa ramas para cada funcionalidad
- ✅ Mantén tu fork actualizado regularmente
- ✅ Revisa tus cambios antes de hacer push
- ✅ Coordina con tu equipo antes de fusionar

## 11. Comandos de referencia rápida

```bash
# Configuración
git config --global user.name "Tu nombre"
git config --global user.email "tu@email.com"

# Repositorio
git clone <url>
git remote add upstream <url-original>

# Trabajo diario
git status
git add .
git commit -m "mensaje"
git push origin main

# Actualizaciones
git fetch upstream
git merge upstream/main

# Ramas
git checkout -b nueva-rama
git checkout main
git branch
```

---

**Recuerda:** La práctica es la clave para dominar Git. ¡No tengas miedo de experimentar en tu fork personal!
