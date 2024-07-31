# primeros-pasos-mac


1. [Instalación de Homebrew](#schema1)
2. [Instalación de Git con Homebrew](schema2)
3. [Configurar GITHUB](schema3)

<hr>
<a name='schema1'></a>


## 1. Instalación de Homebrew

1. Instalación de Homebrew
    Si no has instalado Homebrew, sigue estos pasos:

    - Abre la Terminal.

    - Ejecuta el siguiente comando para instalar Homebrew:

    ```sh
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
    Sigue las instrucciones en pantalla. Una vez completada la instalación, deberías ver un mensaje de éxito.
2. Configuración del PATH
    Es posible que Homebrew se haya instalado correctamente pero no esté en tu `PATH`, lo que significa que tu terminal no sabe dónde encontrar el comando brew.

    Abre tu archivo de configuración de shell para editarlo. Si estás usando zsh (que es el shell predeterminado en macOS Catalina y versiones posteriores), abre el archivo .zshrc con tu editor de texto favorito. Por ejemplo:

    ```sh
    nano ~/.zshrc
    ```
    Añade la siguiente línea al final del archivo:

    ```sh
    export PATH="/opt/homebrew/bin:$PATH"
    ```
    Guarda el archivo y cierra el editor de texto (en nano, puedes hacerlo presionando CTRL+X, luego Y, y finalmente Enter).

    Recarga el archivo de configuración del shell para aplicar los cambios:

    ```sh
    source ~/.zshrc
    ```

3. Verificación de la Instalación
    Después de realizar los pasos anteriores, verifica que Homebrew esté instalado y configurado correctamente ejecutando:

    ```sh
    brew --version
    ````
    Si Homebrew está correctamente instalado, deberías ver la versión de Homebrew.

<hr>
<a name='schema2'></a>

## 2. Instalación de Git con Homebrew
1. Istalación de Git
    Una vez que Homebrew esté funcionando, puedes instalar Git:

    ```sh
    brew install git
    ```
    Y verifica la instalación de Git con:

    ```sh
    git --version
    ```
    Si sigues teniendo problemas, házmelo saber y podemos investigar más a fondo.

2. Configuración de Git
    Después de instalar Git, es recomendable configurarlo con tu nombre y correo electrónico:

    ```sh
    git config --global user.name "Tu Nombre"
    git config --global user.email "tu.email@ejemplo.com"
    ```
<hr>
<a name='schema3'></a>

## 3. Configurar GITHUB

1. Crear una Cuenta en GitHub
    - Visita GitHub y haz clic en "Sign up".
    - Sigue las instrucciones para crear una nueva cuenta.
2. Generar y Añadir una Clave SSH (Opcional pero recomendado)
    Usar una clave SSH te permite conectarte a GitHub sin necesidad de ingresar tu nombre de usuario y contraseña cada vez que interactúas con un repositorio.

    Generar una Clave SSH
    - Abre la Terminal.

    - Ejecuta el siguiente comando, reemplazando tu correo electrónico de GitHub:

        ```sh
        ssh-keygen -t ed25519 -C "tu.email@ejemplo.com"
        ```
    - Cuando se te pregunte dónde guardar la clave, presiona Enter para aceptar la ubicación predeterminada.

    - Se te pedirá que ingreses una frase de contraseña opcional. Puedes presionar Enter si no quieres establecer una.

3. Añadir la Clave SSH al Agente SSH
    - Inicia el agente SSH:

    ```sh
    eval "$(ssh-agent -s)"
    ```
    - Añade tu clave SSH al agente:
    ```sh
    ssh-add ~/.ssh/id_ed25519
    ```
4. Añadir la Clave SSH a tu Cuenta de GitHub
    - Copia el contenido de tu clave pública en el portapapeles:

    ```sh
    pbcopy < ~/.ssh/id_ed25519.pub
    ```
    - Ve a GitHub, cofiguración y haz clic en "New SSH key".

    - Pega la clave en el campo "Key" y da un nombre descriptivo en "Title".

    - Haz clic en "Add SSH key".

5. Configurar Git para GitHub.

    Si lo hizo en el paso de instalar GIT se puede saltar este punto, sino hay que realizarlo.  

    Configura tu nombre de usuario y correo electrónico para Git:

    ```sh
    git config --global user.name "Tu Nombre"
    git config --global user.email "tu.email@ejemplo.com"
    ```