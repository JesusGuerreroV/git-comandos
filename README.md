# git-comandos
Lista de comandos git

### Nota:

Cuando se presenten comandos entre corchetes "[]", por ejemplo [tu-mail] se debe colocar el mail solamente (sin corchetes). 
Ejemplo: ssh-keygen -t ed25519 -C [tu-mail] -> ssh-keygen -t ed25519 -C `correo@ejemplo.com`

## Config git

| Comando | Descripción |
|---------|-------------|
| git config --global user.name "nombre" | Configura el nombre de usuario |
| git config --global user.email "`email@ejemplo.com`" | Configura el email |
| git config --get user.name | Muestra el nombre de usuario configurado |
| git config --get user.email | Muestra el correo configurado |

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
| git clone `git@github.com:[usuario-github]/[nombre-repo].git` | Crea una copia local de un repositorio remoto|