# primeros-pasos-mac

0. [Instalar una terminal, `iTerm2`](#schema0)
1. [Instalación de Homebrew](#schema1)
2. [Instalación de Git con Homebrew](schema2)
3. [Configurar GITHUB](schema3)
4. [Instalar Visual Studio Code](#schema4)
5. [Añadir el comando code manualmente al PATH](#schema5)


<hr>
<a name='schema0'></a>

## 1. Instalar una terminal, `iTerm2`
1. Descargar iTerm2
- Abre tu navegador web y visita la [página oficial de iTerm](https://iterm2.com/)
- Haz clic en el botón "Download" para descargar la última versión estable de iTerm2.
2. Instalar iTerm2
- Una vez que se complete la descarga, abre el archivo .zip que descargaste. Debería estar en tu carpeta de "Descargas" o en la ubicación que hayas especificado.
- Esto descomprimirá un archivo .app. Arrastra este archivo a la carpeta "Aplicaciones" en Finder.
3.  Abrir iTerm2
- Abre Finder y navega a la carpeta "Aplicaciones".
- Encuentra iTerm2 y haz doble clic en él para abrirlo.


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
<hr>
<a name='schema4'></a>


## 4. Instalar Visual Studio Code

1. Descargar Visual Studio Code
    - Abre tu navegador web y visita [la página oficial de descarga de Visual Studio Code.](https://code.visualstudio.com/)
    - Haz clic en el botón "Download for macOS" para descargar el archivo .dmg.
2. Instalar Visual Studio Code
    - Una vez que se complete la descarga, abre el archivo `.dmg` descargado haciendo doble clic en él.
    - Se abrirá una ventana con el ícono de Visual Studio Code y una carpeta de `"Aplicaciones"`.
    - Arrastra el ícono de Visual Studio Code a la carpeta de `"Aplicaciones"`.

3. Si has descargado un archivo comprimido (como un .zip o .dmg) para Visual Studio Code y, al descomprimirlo, se abre directamente en lugar de permitirte moverlo a la carpeta de `"Aplicaciones"`, es posible que necesites realizar algunos pasos manualmente para moverlo a la ubicación adecuada. Aquí tienes los pasos a seguir para cada tipo de archivo:

    - Archivos .zip

        Descargar y Descomprimir:

        - Si has descargado un archivo `.zip`, localízalo en tu carpeta de `"Descargas"` o donde lo hayas guardado.

        - Haz doble clic en el archivo `.zip` para descomprimirlo. Deberías ver una nueva carpeta o un archivo de Visual Studio Code.

        Mover Visual Studio Code a la carpeta de Aplicaciones:
        - Abre Finder.
        - Navega a la carpeta donde se descomprimió Visual Studio Code (probablemente en "Descargas").
        - Busca el archivo o la carpeta de Visual Studio Code (probablemente un archivo .app).
        - Arrastra el archivo o carpeta de Visual Studio Code a la carpeta "Aplicaciones" en Finder. 
    - Archivos .dmg
        
        Descargar y Abrir:

        - Si has descargado un archivo .dmg, localízalo en tu carpeta de "Descargas" o donde lo hayas guardado.
        - Haz doble clic en el archivo .dmg para montarlo y abrir la ventana del instalador.
        
        Mover Visual Studio Code a la carpeta de Aplicaciones:
        - Debería aparecer una ventana con el ícono de Visual Studio Code y una carpeta de "Aplicaciones".
        - Arrastra el ícono de Visual Studio Code a la carpeta de "Aplicaciones".



4. Ejecutar Visual Studio Code
    - Abre la carpeta de `"Aplicaciones"` desde `Finder`.
    - Encuentra Visual Studio Code y haz doble clic en él para abrirlo.
    - La primera vez que abras VS Code, es posible que veas un mensaje advirtiendo que se descargó de Internet. Haz clic en "Abrir" para continuar.

<hr>
<a name='schema5'></a>

## 5. Añadir el comando code manualmente al PATH
1. Crear un enlace simbólico

    Puedes crear un enlace simbólico manualmente para que el comando code funcione en la terminal. Para hacer esto:

    - Abrir la Terminal:

        Abre la aplicación Terminal en tu Mac (puedes buscar "Terminal" en Spotlight).
    - Crear el enlace simbólico:

        Escribe el siguiente comando en la Terminal y presiona Enter:
        ```bash
        sudo ln -s /Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code /usr/local/bin/code
        ````
        Esto solicitará tu contraseña de administrador. Ingresa la contraseña y presiona Enter.
2. Verificar la instalación
    - Verificar el comando:
        Escribe code --version en la Terminal y presiona Enter.

        Deberías ver la versión de Visual Studio Code, lo que indica que el comando code ahora está funcionando correctamente.

3. Alternativa: Añadir a `.zshrc` o `.bash_profile`
        
    Si prefieres o necesitas añadir el comando a tu archivo de configuración de shell, puedes hacerlo añadiendo la ruta de Visual Studio Code al PATH.

    - Editar el archivo de configuración
        - Abrir el archivo de configuración:

            - Para Zsh (macOS Catalina y posteriores), escribe:
            ```bash
            nano ~/.zshrc
            ```
            - Para Bash, escribe:
            ```bash
            nano ~/.bash_profile
            ```
        - Añadir Visual Studio Code al PATH:

            - Añade la siguiente línea al final del archivo:
            ```bash
            export PATH="$PATH:/Applications/Visual Studio Code.app/Contents/Resources/app/bin"
            ```
            - Guardar y cerrar el archivo:

                - Presiona Ctrl + O para guardar el archivo y luego Ctrl + X para salir de nano.
            
            - Recargar el archivo de configuración:

                - Para Zsh, escribe:
                ```bash
                source ~/.zshrc
                ```
                - Para Bash, escribe:
                ```bash
                source ~/.bash_profile
                ```
    - Verificar la instalación
        - Verificar el comando:
            - Escribe `code --version` en la Terminal y presiona Enter.
            - Deberías ver la versión de Visual Studio Code, indicando que el comando code está funcionando correctamente.







