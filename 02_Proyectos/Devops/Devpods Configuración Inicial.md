**MetaTags:** #_Done
**Tags:** #Devops #Contenedores #Desarrollo 
- - -
#### Prerequisito
  - Tener un repo de dotfiles (a poder ser ligerito)
  - docker
  - git
  - ssh

#### Instalar 
``` bash
yay -S devpod
```

#### Puesta a punto Deshabititas el IDE
``` bash
  ln -sf /usr/bin/devpod-cli /usr/bin/devpod
  devpod ide user none
  devpod provider list 
  devpod provider add docker
```

#### Construir el Archivo .devcontainers/devcontainers.json
Docs: https://containers.dev/implementors/spec/
y meterlo en el proyecto que quieras contenerizar
mirar: https://github.com/devcontainers/images/tree/main/src
para elegir una imagen base adecuada a tu proyecto

## Construye un devpod (docker build)

### Construye el contendor desde repo de github 
inspecciona por defector un script -> setup.sh

además de ssh tambien se puede usar https como metodo de validacion
``` bash
devpod up https://github.com/example/repo --ide none --dotfiles https://github.com/my-user/my-dotfiles-repo
```

### Construye el contenedor desde repo local

```bash
devpod up . --ide none --dotfiles git@github.com:Aletheios42/Devpod-Dotfiiles.git
```

## Entra el contenedor con shh(docker run)

``` bash
devpod ssh
```

## Eficiencia
``` bash
devpod context set-options -o DOTFILES_URL=git@github.com:Aletheios42/Devpod-Dotfiles.git
```

asi solo tienes que especificar el repo fuente no el de configuracion
(los dotfiles se quedan establecidos)

``` bash
devpod up .
devpod up https://gihub.com/usuario/repositorio-bin
``` 
```
```

## Higiene
-- recreate para actualizar la imagen
```bash
devpod stop
devpod delete
```

## Privacidad
``` bash
devpod context set-options -o TELEMETRY=false
```

## Instalar chezmoi 
chezmoi maneja tus dotfiles con programacion declarativa, es compatible con scripts.

Descarga el paquete en el proyecto a contenerizar:
``` bash
sh -c "$(curl -fsLS get.chezmoi.io)" -- -b $HOME/.local/bin
```

https://www.chezmoi.io/quick-start/
``` bash
chezmoi init
```

crea un repo en ~/.local/share/chezmoi que guardara el estado del repo para añadir archivos al estado deseado,  y parchear

```bash
chezmoi diff
chezmoi -v apply

```
## Reflejar los cambios locales del devpod en la configuracion general
``` bash
chezmoi cd   # Te lleva el directorio donde se gestionan los dotfiles
git add .
git commit -m "Initial commit"

git remote add origin git@github.com:$GITHUB_USERNAME/dotfiles.git
git branch -M master
git push -u origin master
```

- - - 
#### ***Sources:***
- https://www.chezmoi.io/quick-start/
- https://devpod.sh/docs/what-is-devpod
- https://containers.dev/
