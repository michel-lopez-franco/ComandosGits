# Guía Esencial de Git y Colaboración con Forks

## Configuración Inicial

### Configurar identidad
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu.email@ejemplo.com"
```

### Verificar configuración
```bash
git config --list
```

## Comandos Básicos de Git

### Inicializar un repositorio
```bash
git init
```

### Clonar un repositorio
```bash
git clone https://github.com/usuario/repositorio.git
```

### Ver estado del repositorio
```bash
git status
```

### Agregar archivos al staging area
```bash
git add archivo.txt          # Archivo específico
git add .                    # Todos los archivos
git add *.js                 # Archivos con patrón
```

### Hacer commit
```bash
git commit -m "Mensaje descriptivo del commit"
git commit -am "Agregar y commitear archivos modificados"
```

### Ver historial de commits
```bash
git log
git log --oneline           # Versión compacta
git log --graph             # Con gráfico de ramas
```

### Ver diferencias
```bash
git diff                    # Cambios no staged
git diff --staged           # Cambios staged
git diff HEAD~1             # Comparar con commit anterior
```

## Trabajo con Ramas (Branches)

### Crear y cambiar ramas
```bash
git branch nueva-rama       # Crear rama
git checkout nueva-rama     # Cambiar a rama
git checkout -b nueva-rama  # Crear y cambiar en un comando
git switch nueva-rama       # Comando moderno para cambiar
git switch -c nueva-rama    # Crear y cambiar (moderno)
```

### Listar ramas
```bash
git branch                  # Ramas locales
git branch -r               # Ramas remotas
git branch -a               # Todas las ramas
```

### Fusionar ramas
```bash
git merge nombre-rama       # Fusionar rama en la rama actual
git merge --no-ff nombre-rama  # Fusión sin fast-forward
```

### Eliminar ramas
```bash
git branch -d nombre-rama   # Eliminar rama fusionada
git branch -D nombre-rama   # Forzar eliminación
```

## Trabajo con Repositorios Remotos

### Agregar repositorio remoto
```bash
git remote add origin https://github.com/usuario/repositorio.git
git remote add upstream https://github.com/usuario-original/repositorio.git
```

### Ver repositorios remotos
```bash
git remote -v
```

### Enviar cambios
```bash
git push origin main        # Enviar rama main
git push origin nueva-rama  # Enviar nueva rama
git push -u origin main     # Establecer upstream
```

### Obtener cambios
```bash
git fetch origin           # Descargar cambios sin fusionar
git pull origin main       # Descargar y fusionar
git pull --rebase origin main  # Pull con rebase
```

## Colaboración con Forks

### 1. Hacer Fork de un Repositorio
- Ve al repositorio en GitHub
- Haz clic en el botón "Fork"
- Clona tu fork localmente:
```bash
git clone https://github.com/tu-usuario/repositorio-forkeado.git
```

### 2. Configurar Upstream
```bash
cd repositorio-forkeado
git remote add upstream https://github.com/usuario-original/repositorio.git
git remote -v  # Verificar configuración
```

### 3. Mantener Fork Actualizado
```bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

### 4. Crear Feature Branch
```bash
git checkout -b feature/nueva-funcionalidad
# Hacer cambios y commits
git add .
git commit -m "Agregar nueva funcionalidad"
```

### 5. Enviar Pull Request
```bash
git push origin feature/nueva-funcionalidad
```
Luego crear Pull Request desde GitHub.

### 6. Flujo Completo de Colaboración
```bash
# 1. Actualizar fork
git fetch upstream
git checkout main
git merge upstream/main
git push origin main

# 2. Crear rama de trabajo
git checkout -b fix/corregir-bug

# 3. Hacer cambios y commit
git add .
git commit -m "Corregir bug en función X"

# 4. Enviar rama
git push origin fix/corregir-bug

# 5. Crear Pull Request en GitHub
# 6. Después de merge, limpiar
git checkout main
git branch -d fix/corregir-bug
git push origin --delete fix/corregir-bug
```

## Comandos Útiles Adicionales

### Deshacer cambios
```bash
git checkout -- archivo.txt    # Descartar cambios no staged
git reset HEAD archivo.txt     # Quitar archivo del staging
git reset --soft HEAD~1        # Deshacer último commit (mantener cambios)
git reset --hard HEAD~1        # Deshacer último commit (perder cambios)
```

### Stashing (guardar cambios temporalmente)
```bash
git stash                      # Guardar cambios
git stash pop                  # Recuperar últimos cambios guardados
git stash list                 # Ver stashes guardados
git stash apply stash@{0}      # Aplicar stash específico
```

### Tags
```bash
git tag v1.0.0                 # Crear tag
git tag -a v1.0.0 -m "Versión 1.0.0"  # Tag con mensaje
git push origin v1.0.0         # Enviar tag
git tag -d v1.0.0              # Eliminar tag local
```

### Buscar en el historial
```bash
git grep "texto"               # Buscar en archivos actuales
git log --grep="bug"           # Buscar en mensajes de commit
git log -S "función"           # Buscar cambios que agreguen/eliminen texto
```

## Mejores Prácticas

### Mensajes de Commit
- Usar presente imperativo: "Agregar" en vez de "Agregado"
- Primera línea: resumen en 50 caracteres
- Línea en blanco
- Descripción detallada si es necesario

### Flujo de Trabajo
1. Siempre trabajar en ramas separadas
2. Mantener commits pequeños y enfocados
3. Actualizar regularmente desde upstream
4. Probar antes de hacer commit
5. Revisar cambios antes de enviar PR

### Comandos de Emergencia
```bash
git reflog                     # Ver historial de referencias
git reset --hard HEAD@{1}     # Volver a estado anterior usando reflog
git fsck --lost-found          # Encontrar commits perdidos
```

Esta guía cubre los comandos esenciales para empezar con Git y colaborar efectivamente usando forks. La práctica regular de estos comandos te ayudará a dominar el control de versiones y la colaboración en proyectos de código abierto.