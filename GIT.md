
### Índice
* [Configuración](#configuración)
* [Crear](#crear)
* [Cambios locales](#cambios-locales)
* [Ramas & Etiquetas](#ramas--etiquetas)
* [Actualizar & Publicar](#actualizar--publicar)
* [Fusionar & Rebasar](#fusionar--rebasar)
* [Deshacer](#deshacer)

<hr>

## Configuración

##### Mostrar la cofiguración actual:
```
$ git config --list
```

##### Mostrar la configuración local:
```
$ git config --local --list
```

##### Mostrar la configuración global:
```
$ git config --global --list
```

##### Mostrar la configuración del sistema:
```
$ git config --system --list
```

##### Establecer un nombre que es identificable de crédito cuando se revise el historial de versiones:
```
$ git config --global user.name “[nombre apellido]”
```

##### Establecer una dirección de email que será asociada con cada marca histórica:
```
$ git config --global user.email “[email-válido]”
```

##### Establecer coloreado automático de la línea de comandos de Git para una fácil revisión:
```
$ git config --global color.ui auto
```

##### Establecer el editor global para commits:
```
$ git config --global core.editor vi
```

<hr>

## Crear

##### Clonar un repositorio existente:

Existen dos maneras:

Vía SSH (usar clave generada en la pc)

```
$ git clone ssh://usuario@dominio.com/repo.git
```

Vía HTTP (usar usuario y contraseña del servicio de GIT, ej: github, bitbucket, gitlab)

```
$ git clone http://dominio.com/usuario/repo.git
```

##### Crea un nuevo repositorio local:
```
$ git init
```

<hr>

## Cambios Locales

##### Cambios en el directorio de trabajo:
```
$ git status
```

##### Cambios en archivos rastreados:
```
$ git diff
```

##### Agregar todos los cambios actuales (dentro de la carpeta en la que lo ejecuto):
```
$ git add .
```

##### Realizar un commit de todos los cambios locales en los archivos:
```
$ git commit -a
```

##### Realizar un commit de los cambios previamente almacenados en el área de pruebas:
```
$ git commit
```

##### Realizar un commit con un mensaje:
```
$ git commit -m 'aquí el mensaje'
```

<hr>

## Ramas & Etiquetas

##### Listar todas las ramas locales:
```
$ git branch
```

##### Listar todas las ramas remotas:
```
$ git branch -r
```

##### Cambiar rama HEAD:
```
$ git checkout <rama>
```

##### Crear nueva rama y cambiar a esta:
```
$ git checkout -b <rama>
```

##### Eliminar una rama local:
```
$ git branch -d <rama>
```

##### Forzar eliminación de una rama local:
<em><sub>¡Perderás los cambios sin fusionar!</sub></em>
```
$ git branch -D <branch>
```

<hr>

## Actualizar & Publicar

##### Descargar todos los cambios de &lt;remoto&gt;(origin), pero no integrarlos al HEAD:
```
$ git fetch <remoto>
```

##### Descargar cambios y fusionarlos/integrarlos directamente al HEAD:
```
$ git remote pull <remote> <url>
```

##### Obtener todos los cambios del HEAD al repositorio local:
```
$ git pull origin master
```

##### Publicar cambios locales en un remoto:
```
$ git push remote <remoto> <rama>
```

<hr>

## Fusionar & Rebasar

##### Fusionar <rama> en tu HEAD actual:
```
$ git merge <rama>
```

##### Usar tu editor para manualmente resolver conflictos y (después de resueltos) marcar el archivo como resuelto:
```
$ git add <archivo-resuelto>
```

## Deshacer

##### Descartar todos los cambios locales en tu directorio de trabajo:
```
$ git reset --hard HEAD
```

##### Sacar todos los archivos del área de pruebas (es decir, deshacer el último `git add`):
```
$ git reset .
```

##### Descartar cambios locales de un archivo específico:
```
$ git checkout <archivo>
```

##### Remover los archivos que fueron accidentalmente agregados al commit antes de ser añadidos al .gitignore:
```
$ git rm -r --cached .
$ git add .
$ git commit -m "remove xyz file"
```