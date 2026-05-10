# Stash, Reset y Revert

## Stash — guardar cambios temporalmente

Util cuando necesitas cambiar de rama pero no queres commitear cambios a medio terminar.

```bash
git stash                   # Guarda cambios del working directory y stage
git stash push -m "mensaje" # Stash con nombre descriptivo
git stash list              # Ver todos los stashes guardados
git stash pop               # Aplicar el ultimo stash y eliminarlo
git stash apply stash@{0}   # Aplicar un stash sin eliminarlo
git stash drop stash@{0}    # Eliminar un stash especifico
git stash clear             # Eliminar todos los stashes
```

## Reset — deshacer commits

`reset` mueve el puntero HEAD. Hay tres modos:

```bash
git reset --soft HEAD~1     # Deshace el commit, mantiene cambios en stage
git reset --mixed HEAD~1    # Deshace el commit, mantiene cambios en working dir (default)
git reset --hard HEAD~1     # Deshace el commit y BORRA los cambios (cuidado)
```

> `HEAD~1` significa "un commit antes del actual". Podes usar `HEAD~2`, `HEAD~3`, etc.

## Revert — deshacer un commit de forma segura

A diferencia de `reset`, `revert` no reescribe el historial: crea un nuevo commit que deshace los cambios.

```bash
git revert HEAD             # Revertir el ultimo commit
git revert abc1234          # Revertir un commit especifico por su hash
git revert HEAD --no-commit # Revertir sin crear el commit todavia
```

## Restore — descartar cambios en archivos

```bash
git restore archivo.txt             # Descartar cambios en working directory
git restore --staged archivo.txt    # Sacar del stage sin perder cambios
git restore --source=HEAD~2 archivo.txt   # Restaurar a una version anterior
```

## Reflog — el historial oculto

`reflog` registra todos los movimientos de HEAD, incluso commits "perdidos" con reset --hard.

```bash
git reflog                  # Ver historial completo de movimientos
git reset --hard abc1234    # Recuperar un commit "perdido"
```

## Comparacion rapida

| Comando              | Reescribe historial | Conserva cambios | Uso tipico                     |
|----------------------|--------------------|-----------------:|-------------------------------|
| `reset --soft`       | Si                 | En stage         | Rehacer el ultimo commit       |
| `reset --mixed`      | Si                 | En working dir   | Deshacer y reestructurar       |
| `reset --hard`       | Si                 | No               | Descartar todo (con cuidado)   |
| `revert`             | No                 | N/A              | Deshacer en rama compartida    |
| `stash`              | No                 | En stash         | Cambio de contexto rapido      |

## Practica sugerida

```bash
# Practica stash
# 1. Modifica un archivo sin commitear
# 2. git stash
# 3. git switch otra-rama (o cualquier operacion)
# 4. git stash pop

# Practica reset
# 1. Hace 3 commits en playground/
# 2. git reset --soft HEAD~1  (ver que pasa)
# 3. git reset --mixed HEAD~1 (ver la diferencia)
# 4. git reset --hard HEAD~1  (ver que los cambios desaparecen)
# 5. git reflog para recuperar lo "perdido"

# Practica revert
# 1. Hace un commit con un "error"
# 2. git revert HEAD para deshacerlo de forma segura
# 3. Compara el historial con git log --oneline
```
