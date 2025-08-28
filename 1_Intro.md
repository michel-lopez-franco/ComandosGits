# 1. Configuración inicial

Primero, configura tu identidad en Git (solo necesitas hacerlo una vez):

```bash
git config --global user.name "Tu nombre"
git config --global user.email "tu.email@ejemplo.com"
```

# 2. Clonar el repositorio del profesor

```bash
git clone https://github.com/Michel/Robot1.git
cd Robot1
```

# 3. Seguir las actualizaciones del profesor

Para estar al tanto de los cambios del profesor:

```bash

# Ver el estado actual
git status

# Obtener los últimos cambios del repositorio remoto
git pull origin main
```

Te recomiendo hacer git pull regularmente para mantener tu copia actualizada.

# 4. Flujo de trabajo para tus tareas

# Guía básica de Git y cómo hacer un fork

## 1. Configuración inicial de Git

Antes de empezar, configura tu nombre y correo para que tus cambios queden registrados correctamente:

```bash
git config --global user.name "Tu nombre"
git config --global user.email "tu.email@ejemplo.com"
```

## 2. ¿Qué es un fork y cómo hacerlo?

Un **fork** es una copia personal de un repositorio. Así puedes trabajar en tu propia versión sin afectar el original.

1.  Ve al repositorio del profesor en GitHub (por ejemplo: `https://github.com/Michel/Robot1`).
2.  Haz clic en el botón **Fork** (arriba a la derecha).
3.  El repositorio aparecerá en tu cuenta de GitHub.

## 3. Clonar tu fork

Clona tu copia (fork) a tu computadora:

```bash
git clone https://github.com/TU_USUARIO/Robot1.git
cd Robot1
```

## 4. Comandos básicos de Git

### Ver el estado de tus archivos

```bash
git status
```

### Agregar archivos al área de preparación (staging)

```bash
git add nombre_del_archivo
```

### Guardar los cambios (commit)

```bash
git commit -m "Descripción de los cambios"
```

### Enviar tus cambios a GitHub

```bash
git push origin main
```

## 5. Mantener tu fork actualizado con el repositorio del profesor

Para obtener los últimos cambios del profesor:

1.  Agrega el repositorio original como remoto adicional:
    ```bash
    git remote add upstream https://github.com/Michel/Robot1.git
    ```
2.  Descarga los cambios del profesor:
    ```bash
    git fetch upstream
    ```
3.  Fusiona los cambios en tu rama principal:
    ```bash
    git merge upstream/main
    ```

## 6. Buenas prácticas: trabajar en ramas

Crear una rama para cada tarea o funcionalidad:

```bash
git checkout -b mi-tarea
```

Cuando termines, puedes fusionar tu rama a `main` y subir los cambios:

```bash
git checkout main
git merge mi-tarea
git push origin main
```

## 7. Comandos útiles

### Ver diferencias con respecto a la última versión

```bash
git diff
```

### Ver historial de commits

```bash
git log
```

### Ver ramas existentes

```bash
git branch
```

### Cambiar entre ramas

```bash
git checkout nombre-rama
```

## 8. Resolución de conflictos

Si hay conflictos al hacer `git pull`:

1.  Git te indicará los archivos con conflictos.
2.  Edita esos archivos para resolver las diferencias.
3.  Marca los conflictos como resueltos:
    ```bash
    git add nombre_archivo
    ```
4.  Completa la fusión:
    ```bash
    git commit
    ```

## Recomendaciones

- Siempre haz `git pull` antes de empezar a trabajar.
- Usa ramas separadas para cada tarea.
- Escribe mensajes de commit claros y descriptivos.
- Si es un proyecto colaborativo, coordínate con tus compañeros.

---

Esta guía cubre los comandos esenciales para empezar a trabajar con Git y colaborar usando forks. Si tienes dudas, consulta la documentación oficial.
