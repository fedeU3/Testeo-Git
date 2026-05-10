# Comandos basicos de Git

## Configuracion inicial

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
git config --list
```

## Iniciar un repositorio

```bash
git init          # Iniciar un repo nuevo en la carpeta actual
git clone <url>   # Clonar un repo existente
```

## Ver estado y cambios

```bash
git status                  # Ver archivos modificados, en stage, sin trackear
git diff                    # Ver cambios no staged
git diff --staged           # Ver cambios en el area de stage
git log                     # Historial de commits
git log --oneline           # Historial compacto
git log --oneline --graph --all   # Historial con ramas en grafico
```

## Agregar y commitear

```bash
git add archivo.txt         # Agregar un archivo al stage
git add .                   # Agregar todos los cambios
git commit -m "mensaje"     # Crear un commit
git commit -am "mensaje"    # Add + commit en un paso (solo archivos ya trackeados)
```

## Deshacer antes de commitear

```bash
git restore archivo.txt     # Descartar cambios en working directory
git restore --staged archivo.txt   # Sacar del stage (sin perder cambios)
```

## Practica sugerida

1. Modifica `playground/archivo-prueba.txt`
2. Usa `git status` y `git diff` para ver los cambios
3. Agrega el archivo con `git add`
4. Usa `git diff --staged` para ver lo que va a entrar al commit
5. Hace el commit y revisa el historial con `git log --oneline`
6. Repeti el proceso varias veces para construir un historial
