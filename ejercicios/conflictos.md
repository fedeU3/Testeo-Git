# Conflictos en Git

Un conflicto ocurre cuando dos ramas modificaron la misma linea de un archivo y Git no puede decidir cual version conservar.

## Como generar un conflicto (a proposito)

```bash
# 1. Partir de main con un archivo
echo "Linea original" > playground/archivo-prueba.txt
git add . && git commit -m "version original"

# 2. Crear rama-a y modificar la misma linea
git switch -c rama-a
echo "Cambio desde rama-a" > playground/archivo-prueba.txt
git add . && git commit -m "cambio en rama-a"

# 3. Volver a main y modificar la misma linea
git switch main
echo "Cambio desde main" > playground/archivo-prueba.txt
git add . && git commit -m "cambio en main"

# 4. Intentar mergear → CONFLICTO
git merge rama-a
```

## Como se ve un conflicto en el archivo

```
<<<<<<< HEAD
Cambio desde main
=======
Cambio desde rama-a
>>>>>>> rama-a
```

- `HEAD` es la version de la rama actual (main)
- Despues de `=======` esta la version que viene de la rama que se mergea

## Como resolverlo

1. Abrir el archivo conflictuado
2. Editar manualmente para dejar la version correcta (borrar los marcadores `<<<<`, `====`, `>>>>`)
3. Guardar el archivo
4. Agregar al stage y commitear:

```bash
git add playground/archivo-prueba.txt
git commit -m "resuelvo conflicto entre main y rama-a"
```

## Abortar un merge en curso

```bash
git merge --abort
```

## Ver que archivos tienen conflictos

```bash
git status   # Los archivos en conflicto aparecen como "both modified"
```

## Practica sugerida

1. Generar el conflicto siguiendo los pasos de arriba
2. Resolverlo manualmente editando el archivo
3. Repetir con tres ramas para practicar conflictos multiples
4. Probar `git merge --abort` antes de resolver para ver que pasa
