# Ramas y Merge

## Crear y moverse entre ramas

```bash
git branch                      # Listar ramas locales
git branch nombre-rama          # Crear una rama nueva
git switch nombre-rama          # Cambiar a una rama
git switch -c nombre-rama       # Crear y cambiar en un paso
git branch -d nombre-rama       # Eliminar una rama (merged)
git branch -D nombre-rama       # Eliminar una rama (forzado)
```

## Ver ramas

```bash
git branch -a                   # Ramas locales y remotas
git log --oneline --graph --all # Ver historial con todas las ramas
```

## Merge

```bash
git switch main
git merge nombre-rama           # Fusionar nombre-rama en main

# Tipos de merge:
# - Fast-forward: cuando no hubo divergencia (no crea commit extra)
# - Merge commit: cuando hubo divergencia (crea un commit de fusion)
```

## Rebase (alternativa al merge)

```bash
git switch feature
git rebase main                 # Reaplica los commits de feature sobre main
```

## Practica sugerida

### Flujo basico de feature branch

```bash
# 1. Crear una rama para una "feature"
git switch -c mi-feature

# 2. Hacer cambios y commits en esa rama
# (modifica playground/archivo-prueba.txt)
git add .
git commit -m "agrego cambios en mi-feature"

# 3. Volver a main y mergear
git switch main
git merge mi-feature

# 4. Ver el resultado
git log --oneline --graph --all
```

### Probar fast-forward vs merge commit

- Merge sin commits nuevos en main desde que se creo la rama → fast-forward
- Merge con commits en ambas ramas → merge commit con `--no-ff` o automaticamente
