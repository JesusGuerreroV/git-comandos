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
| [documentacion](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) | |


## Iniciar repo

| Comando | Descripción |
|---------|-------------|
| git init | Inicia un repo local |
| git clone `git@github.com:[usuario-github]/[nombre-repo].git` | Crea una copia local de un repositorio remoto |

## Git basics
| Comando | Descripción |
|---------|-------------|
| git status | Muestra el estado actual del repositorio |
| git status --untracked-files | Muestra el estado actual del repositorio a nivel archivo|
| git add file | Agrega un archivo al staging area (puedes separar archivos con un espacio para agregar varios, ej: git add file1 file2) |
| git add . | Agrega todos los archivos al staging area |
| git commit -m "mensaje" | Realiza un commit |
| git commit -a -m "mensaje" o git commit -am "mensaje" | Agrega los archivos al staging area y realiza el commit simultaneamnente |
| git commit --amend | Permite rehacer tu commit previo |
| git log | Muestra el log de los commits en el repositorio |
| git log --oneline | Muestra el log simplificado |

## Git branching y merging
| Comando | Descripción |
|---------|-------------|
| git branch | Muestra una lista de las branch existentes en el repo |
| git branch -v | Muestra una lista de las branch existentes y la info del ultimo commit |
| git branch [nombre] | Crea una nueva branch [nombre] |
| git switch [nombre] | Cambia a la branch [nombre] |
| git switch -c [nombre] | Crea una branch nueva y cambia a ella |
| git checkout [nombre] | Cambia a la branch [nombre] |
| git checkout -b [nombre] | Crea una branch nueva y cambia a ella |
| git branch -d [nombre] | Elimina la branch [nombre] (si hiciste merge) (debes estar fuera de la rama [nombre]) |
| git branch -D [nombre] | Forza el eliminado de la branch [nombre] (debes estar fuera de la rama [nombre] |
| git branch -m [nuevoNombre] | Renombra una rama (debes estar en ella) a [nuevonombre] |
| git merge [nombreBranch] | Combina [nombreBranch] con la branch activa |

## Git diff
| Comando | Descripción |
|---------|-------------|
| git diff | Muestra los cambios entre el staging area y el directorio de trabajo |
| git diff [filename] | Muestra los cambios entre el staging area y el directorio de trabajo para [filename] (puedes separar filenames con espacios para corroborar varios archivos)|
| git diff HEAD | Muestra los cambios entre el ultimo commit y el directorio de trabajo |
| git diff HEAD [filename] | Muestra los cambios entre el ultimo commit y el directorio de trabajo para [filename] (puedes separar filenames con espacios para corroborar varios archivos) |
| git diff --staged, git diff --cached | Muestra los cambios entre staging area y el ultimo commit |
| git diff --staged [filename], git diff --cached [filename] | Muestra los cambios entre staging area y el ultimo commit para [filename] (puedes separar filenames con espacios para corroborar varios archivos) |
| git diff branch1..branch2, git diff branch1 branch2 | Muestra los cambios entre branch1 y branch2 |
| git diff commit1..commit2, git diff commit1 commit2 | Muestra los cambios entre commit1 y commit2 |

## Git stashing
| Comando | Descripción |
|---------|-------------|
| git stash, git stash save | Almacena los cambios en el repo (staged y no staged) revirtiendo los cambios en tu directorio de trabajo |
| git stash list | Ver la lista de staches que tenemos (los distintos cambios a los que les hemos aplicado git stash) |
| git stash pop | Recupera los cambios almacenados mas recientes y los reaplica a tu directorio de trabajo (elimina los cambios del stash) |
| git stash apply | Aplica los cambios almacenados en el stash pero no los elimina del stash. Util si quieres aplicar los cambios en diferentes lugares |
| git stash apply stash@{n} | aplica los cambios almacenados en stash n |
| git stash drop stash@{n} | Elimina el stash n |
| git stash clear | Elimina todo el stash |

## Git undoing and time traveling
| Comando | Descripción |
|---------|-------------|
| git checkout [hash commit] | Para posicionarnos en un commit en particular (el estado del repo cambia a como estaba en ese momento) |
| git checkout HEAD~1 | Para posicionarnos en el commit pasado (realmente puede ser HEAD~n y te posicionas en n commits antes de HEAD) |
| git switch - | Cambia a la rama donde estabas sacandote del estado "detached  HEAD" |
| git checkout HEAD [filename], git checkout -- [filename], git restore [filename] | Cambia el estado de [filename] a como estaba en HEAD (elimina los cambios que hiciste y los deja a tu ultimo commit) |
| git restore --source [HEAD~n, commit hash] [filename] | Cambia el estado de [filename] a como estaba en [HEAD~n] o [commit hash] |
| git restore --staged [filename] | Elimina [filename] del area de staging |
| git reset [commit hash] | Resetea el repositorio al momento que se hizo el commit [commit hash] mantiendo los cambios en el directorio de trabajo |
| git reset --hard [commit hash] | Resetea el repositorio al momento que se hizo el commit [commit hash] eliminando los cambios realizados |
| git revert [commit hash] | Resetea el repositorio al momento que se hizo el commit [commit hash] pero se hace hace un commit nuevo y los commits descartados en el nuevo commit quedan en la historia del repo |

## Collaboration
| Comando | Descripción |
|---------|-------------|
| git remote | Lista los "remote" actuales que tienes en el repo |
| git remote -v | Lista los "remote" actuales que tienes en el repo (verbose) |
| git remote add [nombre] [url] | Agrega un nuevo remote con nombre [name] (por convencion se nombra origin) apuntando a [url] en github |
| git remote rename [nombre] [nuevoNombre] | Renombra [nombre] a [nuevoNombre] |
| git remote remove [nombre] | Elimina el remote [nombre] |
| git push [remote] [branch] | Sube o actualiza los cambios de [branch] en [remote] |
| git push [remote] [localBranch]:[branch] | Sube o actualiza los cambios de [localBranch] a [branch] en [remote] |
| git push -u [remote] [branch] | Sube o actualiza los cambios de [branch] en [remote] pero al mismo tiempo vincula [branch] con su equivalente en origin permitiendo utilizar solo git push (en la rama a la que le quieres hacer push) ya que git recuerda ese vinculo |
| git branch -r | Enlista las ramas que existen en remote |
| git switch [remoteBranch] | Si quieres usar una branch en remote pudes utilizar el comando switch y automaticamente te crea una branch local que este trackeando a [remoteBranch] |
| git checkout --track origin/[branch] | Alternativa del comando anterior |
| git fetch, git fetch origin, git fetch [remote] | Descarga los cambios en remote a tu repositorio local sin afectar tu directorio de trabajo, solo actualiza las branches remotas. Si no se especifica [remote] el default es origin |
| git fetch [remote] [branch] | Descarga los cambios de la [branch] especifica sin afectar el directorio de trabajo |
