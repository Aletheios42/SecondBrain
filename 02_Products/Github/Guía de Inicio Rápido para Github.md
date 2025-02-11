**Tags:** #_Todo
#ToTag #ToLink 
- - -
##  ¿Qué es GitHub?
GitHub es una plataforma de desarrollo colaborativo que permite alojar, versionar y compartir código. Cada repositorio contiene un directorio `.git` que gestiona el versionado local, que luego se sincroniza con el remoto (GitHub). Además de control de versiones, ofrece CI/CD mediante GitHub Actions, automatización con webhooks, y gestión de seguridad con pre-commit hooks.

1. Visita [github.com](https://github.com) y completa el registro con:
   - Username (será tu identificador público)
   - Email (verificable)
   - Contraseña segura (mínimo 8 caracteres, números y símbolos)
2. Verifica tu email a través del enlace recibido y ¡ya tienes tu cuenta lista para usar!
## Configuración del entorno de trabajo
Git almacena tu configuración global en `~/.gitconfig`
### Configuración local (.gitconfig)
```bash
# Estos comandos escriben automáticamente en ~/.gitconfig
# También puedes editar el archivo manualmente con los mismos resultados
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
git config --global init.defaultBranch main
```
### Estructura básica de .gitconfig
```ini
[user]
    # Identidad para commits y tags
    name = Tu Nombre
    email = tu@email.com
[init]
    # Nombre de la rama principal al iniciar repositorios
    defaultBranch = main
[credential]
    # Método de almacenamiento de credenciales
    helper = store
[core]
    # Editor predeterminado para commits y mensajes
    editor = vim
```
## Métodos de autenticación
### HTTPS
Utiliza usuario y token para autenticarte. Más simple pero requiere gestión de token.
1. Crear Personal Access Token:
   - Ve a Settings → Developer settings → Personal access tokens → Tokens (classic)
   - Click en "Generate new token"
   - Selecciona los permisos (mínimo: repo, workflow)
   - Guarda el token inmediatamente (solo visible una vez)
2. Configurar almacenamiento de credenciales:
```bash
# Configura Git para guardar credenciales permanentemente
git config --global credential.helper store
# La primera vez que hagas git push, te pedirá:
# Username: tu-usuario
# Password: tu-token
# Después se guardarán automáticamente
```
#### Comandos HTTPS
```bash
# Clonar repositorio
git clone https://github.com/usuario/repositorio.git
# Añadir remote
git remote add origin https://github.com/usuario/repositorio.git
```
### SSH
Utiliza par de llaves criptográficas. Más seguro y no requiere tokens.
1. Generar y configurar llaves:
```bash
# Genera par de llaves: privada (id_ed25519) y pública (id_ed25519.pub)
# -t ed25519: usa algoritmo Ed25519 (más seguro que RSA)
# -C: añade comentario/identificador (típicamente email)
ssh-keygen -t ed25519 -C "tu@email.com"

# Inicia el agente SSH en background
eval "$(ssh-agent -s)"
# Añade tu llave privada al agente (gestiona las llaves durante tu sesión)
ssh-add ~/.ssh/id_ed25519

# Muestra tu llave pública para copiarla a GitHub
cat ~/.ssh/id_ed25519.pub
```
2. Añadir llave a GitHub:
   - Settings → SSH and GPG keys → New SSH key
   - Pega el contenido de id_ed25519.pub
3. Comandos SSH:
```bash
# Clonar repositorio
git clone git@github.com:usuario/repositorio.git
# Añadir remote
git remote add origin git@github.com:usuario/repositorio.git
```
## Estados y Comandos básicos

### Estados de los archivos en Git
1. **Untracked**: Archivos nuevos que Git no está siguiendo
2. **Tracked**: Archivos que Git conoce y monitorea, pueden estar en:
   - **Modified**: Archivos modificados en el directorio de trabajo
   - **Staged**: Archivos en el área de preparación (staging area), listos para commit
   - **Committed**: Archivos guardados en el repositorio local

```
Directorio de trabajo   →   Staging Area (index)   →   Repositorio (.git)
    (modified)         git add     (staged)      git commit    (committed)
```
### Comandos y su efecto en estados

| Comando                       | Descripción                                                           | Estado resultante              |
| ----------------------------- | --------------------------------------------------------------------- | ------------------------------ |
| `git init`                    | Crea un repositorio local inicializando el directorio `.git`          | -                              |
| `git status`                  | Muestra archivos modified, staged y untracked                         | -                              |
| `git log`                     | Muestra historial de commits con hash, autor, fecha y mensaje         | -                              |
| `git add .`                   | Mueve TODOS los cambios al staging area. Los archivos quedan "staged" | Staged                         |
| `git add file.txt`            | Mueve solo los cambios del archivo especificado al staging            | Staged                         |
| `git commit -m "mensaje"`     | Crea commit con archivos staged                                       | Committed                      |
| `git push origin main`        | Envía commits locales al remoto (origin) en rama main                 | -                              |
| `git pull origin main`        | Obtiene y fusiona cambios del remoto                                  | -                              |
| `git branch`                  | Lista ramas locales (* marca la actual)                               | -                              |
| `git checkout -b nombre-rama` | Crea y cambia a nueva rama desde HEAD                                 | -                              |
| `git merge rama-origen`       | Fusiona rama-origen en la rama actual                                 | -                              |
| `git reset --hard HEAD^`      | Elimina último commit y sus cambios                                   | Modified/Untracked             |
| `git reset --hard <hash>`     | Revierte al commit específico                                         | Modified/Untracked             |
| `git stash`                   | Guarda cambios modified en la pila temporal                           | Committed (working dir limpio) |
## ".gitignore"
Archivo que indica a Git qué archivos y directorios debe ignorar (no trackear) en un proyecto git.

```bash
# Estructura básica de .gitignore
*.log        # Ignora todos los archivos .log
node_modules/  # Ignora el directorio completo
/dist        # Ignora dist en el directorio raíz
*.env        # Ignora archivos de variables de entorno
!prod.env    # No ignora prod.env específicamente
```

Casos comunes para ignorar:
- Archivos de dependencias (`node_modules/`, `vendor/`)
- Archivos compilados (`.class`, `.o`, `dist/`)
- Archivos de configuración local (`.env`, `config.local.json`)
- Archivos del sistema (`.DS_Store`, `Thumbs.db`)
- Directorios de IDE (`.idea/`, `.vscode/`)
## Notas importantes
- **origin**: Nombre por defecto del repositorio remoto (alias para la URL de GitHub)
- **blob** (Binary Large Object): Contenido de un archivo en un commit específico
- Siempre usar .gitignore para archivos sensibles
- Hacer commits frecuentes y descriptivos
- Verificar siempre el remote antes de push()
- - - 
## ***Sources:***