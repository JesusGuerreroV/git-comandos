# git-comandos
Lista de comandos git

### Nota:

Todo entre "[]" se debe reemplazar, por ejemplo: [filename] -> songs.txt

## Pre git (comandos basicos shell)

| Comando | Descripción |
|---------|-------------|
| ls [path] | list - Muestra el contenido de una carpeta (si no especificas path, muestra el contenido del directorio actual) |
| ls -a [path] | Muestra el contenido, incluyendo el contenito oculto, de una carpeta (si no especificas path, muestra el contenido del directorio actual) |
| start [., path] | (en windows) Abre el explorador en el directorio actual (.) o en [path] |
| pwd | Muestra el directorio actual |
| cd [path] | Cambia al directorio [path] |
| cd .. | Se mueve una carpeta atras (equivalente a <- en explorer) |
| touch [filename, path/filename] | Crea o actualiza un archivo (puedes crear varios separandolos con espacios, ej: touch file1.txt file2.txt ...) |
| mkdir [dir, path/dir] | Crea una carpeta (puedes crear varias separandolas con espacios, ej: mkdir dir dir2)|
| rm [filename, path/filename] | Elimina permanentemente el archivo [filename] (puedes eliminar varios archivos separandolos con espacios, ej: rm file file2) |
| rm -rf [dir, path/dir] | Elimina permanentemente un directorio y su contenido (puedes eliminar varios separandolos con espacios, ej: rm -rf dir dir2) |
| cat [filename] | Permite ver el contenido de [filename] |

## Config git

| Comando | Descripción |
|---------|-------------|
| git config --global user.name "nombre" | Configura el nombre de usuario |
| git config --global user.email "`email@ejemplo.com`" | Configura el email |
| git config --get user.name, git config user.name | Muestra el nombre de usuario configurado |
| git config --get user.email, git config user.email | Muestra el correo configurado |
| git config --global core.editor [editor] | Configura el editor de texto [tabla que muestra el comando especifico para configurar el editor](https://git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Setup-and-Config)|

## Config SSH

| Comando | Descripción |
|---------|-------------|
| ls ~/.ssh/id_ed25519.pub | Checar si ya tenemos un SSH |
| ssh-keygen -t ed25519 -C [tu-mail] | Genera el SSH (hacer esto si el comando anterior no mostró un SSH)|
| cat ~/.ssh/id_ed25519.pub | Muestra el SSH en consola | 

Copiamos al SSH de consola y lo agregamos a la cuenta de GitHub: Dentro GitHub click en el icono del perfil (desplegable) > Settings > SSH and GPG keys > New SSH Key > Pones mombre descriptivo y pegas el SSH > Add SSH key
|         |             |
|---------|-------------|
| ssh -T `git@github.com` | Checa si el proceso anterior fue correcto. Mostrando: "Hi USERNAME! You've successfully authenticated, but GitHub does not provide shell access" la configuración fue correcta. |

## Iniciar repo

| Comando | Descripción |
|---------|-------------|
| git init | Inicia un repo local |
| git clone `git@github.com:[usuario-github]/[nombre-repo].git` | Crea una copia local de un repositorio remoto |

## Git basics
| Comando | Descripción |
|---------|-------------|
| git status | Muestra el estado actual del repositorio |
| git add file | Agrega un archivo al staging area (puedes separar archivos con un espacio para agregar varios, ej: git add file1 file2) |
| git add . | Agrega todos los archivos al staging area |
| git commit -m "mensaje" | Realiza un commit |
| git commit -a -m "mensaje" | Agrega los archivos al staging area y realiza el commit simultaneamnente |
| git commit --amend | Permite rehacer tu commit previo |
| git log | Muestra el log de los commits en el repositorio |
| git log --oneline | Muestra el log simplificado |

## Git branching
| Comando | Descripción |
|---------|-------------|
| git branch | Muestra una lista de las branch existentes en el repo |
| git branch [nombre] | Crea una nueva branch [nombre] |
| git switch [nombre] | Cambia a la branch [nombre] |
| git switch -c [nombre] | Crea una branch nueva y cambia a ella |
| git checkout [nombre] | Cambia a la branch [nombre] |
| git checkout -b [nombre] | Crea una branch nueva y cambia a ella |
| git branch -d [nombre] | Elimina la branch [nombre] (si hiciste merge) (debes estar fuera de la rama [nombre]) |
| git branch -D [nombre] | Forza el eliminado de la branch [nombre] (debes estar fuera de la rama [nombre] |
| git branch -m [nuevoNombre] | Renombra una rama (debes estar en ella) a [nuevonombre] |