# Testo Git

Repositorio de aprendizaje y laboratorio personal para practicar comandos de Git.

No es una aplicación real ni un proyecto productivo. Su único propósito es experimentar con Git sin miedo a romper nada.

---

## Objetivo

Tener un espacio seguro para practicar Git: hacer commits, crear ramas, resolver conflictos, usar stash, revertir cambios y explorar el historial sin consecuencias.

---

## Que se puede practicar

- Comandos basicos: `init`, `add`, `commit`, `status`, `log`, `diff`
- Trabajo con ramas: `branch`, `checkout`, `switch`, `merge`
- Resolucion de conflictos
- `stash`, `reset`, `revert`, `restore`
- `rebase` interactivo
- Flujo con repositorio remoto: `clone`, `push`, `pull`, `fetch`
- Tags, aliases y configuracion de Git

---

## Estructura del repositorio

```
testo-git/
├── README.md                   # Este archivo
├── ejercicios/
│   ├── comandos-basicos.md     # Guia de comandos esenciales
│   ├── ramas-y-merge.md        # Flujo de trabajo con ramas
│   ├── conflictos.md           # Como generar y resolver conflictos
│   └── stash-reset-revert.md   # Deshacer cambios de distintas formas
└── playground/
    ├── archivo-prueba.txt      # Archivo libre para experimentar
    └── notas.txt               # Espacio para tomar notas
```

- **ejercicios/**: Guias con explicaciones y ejemplos de comandos Git organizados por tema.
- **playground/**: Archivos de texto libres para modificar, commitear, borrar y restaurar sin preocupaciones.

---

## Como usarlo

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu-usuario/testo-git.git
cd testo-git
```

### 2. Ver el estado actual

```bash
git status
git log --oneline
```

### 3. Elegir un ejercicio

Abri cualquier archivo de la carpeta `ejercicios/` y seguí los pasos descritos.

### 4. Experimentar en playground/

Modifica los archivos de `playground/`, hacé commits, creá ramas, rompé cosas. Es para eso.

---

## Comandos utiles para empezar

```bash
# Ver el historial de commits
git log --oneline --graph --all

# Crear y cambiar a una rama nueva
git switch -c nombre-de-la-rama

# Guardar cambios temporalmente
git stash
git stash pop

# Deshacer el ultimo commit (sin perder los cambios)
git reset --soft HEAD~1

# Ver diferencias entre ramas
git diff main..nombre-de-la-rama
```

---

## Recomendaciones

- **Rompe cosas.** Este repo existe para eso. No hay nada importante que perder.
- Usa `git log --oneline --graph --all` seguido para ver como evoluciona el historial.
- Si queres empezar de cero, borra y volvé a clonar. Es parte del proceso.
- No hace falta internet para practicar la mayoria de los comandos.
- Experimentá con `git reflog` si "perdes" un commit: Git casi nunca borra nada realmente.

---

> Repositorio de aprendizaje personal. No contiene logica de negocio ni codigo de produccion.
