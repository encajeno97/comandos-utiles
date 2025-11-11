# 🧠 Guía completa de Git

## 📌 ¿Qué es Git?

**Git** es un *sistema de control de versiones distribuido* creado por **Linus Torvalds** en 2005.  
Permite llevar un historial de los cambios realizados en un proyecto, colaborar con otras personas, y volver a versiones anteriores del código.

---

## 🎯 ¿Para qué sirve?

- **Registrar cambios** en los archivos (qué cambió, cuándo y quién).
- **Volver atrás** a versiones anteriores sin perder trabajo.
- **Colaborar** en equipo con ramas (branches).
- **Experimentar** sin afectar la rama principal.
- **Auditar** el historial del código.
- **Automatizar despliegues** (CI/CD) basados en versiones.

---

## 🧩 Conceptos básicos

| Concepto | Descripción |
|-----------|-------------|
| **Repositorio** | Carpeta del proyecto con un subdirectorio oculto `.git` donde se guarda el historial. |
| **Commit** | “Foto” de los archivos en un momento concreto. |
| **Branch (rama)** | Línea independiente de desarrollo. |
| **Merge / Rebase** | Maneras de integrar ramas. |
| **HEAD** | Puntero al commit o rama actual. |
| **Staging area** | Zona intermedia donde se preparan los cambios antes del commit. |
| **Remote** | Repositorio remoto (GitHub, GitLab…). |

---

## ⚙️ Configuración inicial

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@correo.com"
git config --global core.editor "code --wait"
git config --global color.ui auto
```

## 🧱 Flujo básico de trabajo

### 1. Crear o clonar un repositorio

```bash
git init                # Crear un nuevo repositorio
git clone <url>         # Clonar un repositorio existente
```

### 2. Ver estado

```bash
git status
```

### 3. Añadir archivos al área de staging

```bash
git add archivo.txt     # Añadir un archivo
git add .               # Añadir todos los cambios
git add -p              # Añadir por fragmentos
```

### 4. Hacer commit

```bash
git commit -m "Mensaje claro sobre el cambio"
```

### 5. Ver historial

```bash
git log
git log --oneline --graph --decorate --all
git show <commit>
```

### 6. Trabajar con ramas

```bash
git branch                      # Listar ramas
git switch nombre-rama          # Cambiar de rama
git switch -c nueva-rama        # Crear y cambiar
git branch -d nombre-rama       # Borrar rama
```

### 7. Combinar cambios

```bash
git merge feature-x             # Fusionar una rama
git rebase main                 # Reaplicar commits sobre otra rama
```

### 8. Sincronizar con remoto

```bash
git remote add origin <url>
git fetch origin
git pull origin main
git push origin main
```

---

## 🚫 Ignorar archivos

Archivo `.gitignore`:

```
node_modules/
dist/
*.log
.env
```

---

## 🔧 Comandos útiles

| Comando                                | Descripción                                       |
| -------------------------------------- | ------------------------------------------------- |
| `git diff`                             | Ver diferencias de cambios.                       |
| `git reset --soft <commit>`            | Mueve HEAD sin tocar archivos.                    |
| `git reset --hard <commit>`            | Vuelve completamente atrás (⚠️ destruye cambios). |
| `git revert <commit>`                  | Deshace un commit creando uno nuevo.              |
| `git stash`                            | Guarda cambios temporales.                        |
| `git cherry-pick <commit>`             | Aplica un commit específico en otra rama.         |
| `git tag -a v1.0.0 -m "Versión 1.0.0"` | Crear etiqueta (tag).                             |
| `git reflog`                           | Ver historial de movimientos de HEAD.             |
| `git blame archivo`                    | Ver quién modificó cada línea.                    |
| `git clean -f -d`                      | Eliminar archivos no rastreados.                  |

---

## ⚔️ Conflictos y resolución

Cuando Git no puede fusionar automáticamente:

1. Editar archivos marcados con:
2. Resolver el conflicto.
3. Ejecutar:

   ```bash
   git add archivo_resuelto
   git commit
   ```
4. Si deseas abortar:

   ```bash
   git merge --abort
   git rebase --abort
   ```

---

## 🧠 Buenas prácticas

* Escribe **mensajes de commit claros**.
* Haz commits **pequeños y atómicos**.
* Crea **ramas por feature** o bugfix.
* No uses `push --force` en ramas compartidas (usa `--force-with-lease`).
* Mantén `.gitignore` actualizado.
* Protege la rama `main` en el remoto.

---

## 💡 Casos comunes

### Iniciar y subir a GitHub

```bash
git init
git add .
git commit -m "Primer commit"
git branch -M main
git remote add origin git@github.com:usuario/mi-proyecto.git
git push -u origin main
```

### Crear una rama de feature

```bash
git switch -c feature/login
# trabajar...
git add .
git commit -m "Añade formulario de login"
git push -u origin feature/login
```

### Recuperar archivo borrado

```bash
git checkout HEAD -- ruta/al/archivo
```

### Deshacer último commit (manteniendo cambios)

```bash
git reset --soft HEAD~1
```

---

## 🚀 Recursos recomendados

* [Pro Git Book (oficial, gratuito)](https://git-scm.com/book/es/v2)
* [Git Cheat Sheet (GitHub)](https://education.github.com/git-cheat-sheet-education.pdf)
* [Learn Git Branching (interactivo)](https://learngitbranching.js.org/)

---

## 🧭 Qué aprender después

* Flujos de trabajo: **Git Flow**, **GitHub Flow**, **Trunk-based development**.
* Integración con CI/CD (GitHub Actions, GitLab CI).
* Git hooks y automatización.
* Herramientas GUI: **GitKraken**, **Sourcetree**, **VSCode Git**.

