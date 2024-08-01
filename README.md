# primeros-pasos-mac

0. [Instalar una terminal, `iTerm2`](#schema0)
1. [Instalación de Homebrew](#schema1)
2. [Instalación de Git con Homebrew](schema2)
3. [Configurar GITHUB](schema3)
4. [Instalar Visual Studio Code](#schema4)
5. [Añadir el comando code manualmente al PATH](#schema5)
6. [Extensiones para Visual Studio Code](schema6)
7. [Aplicaciones](schema7)
8. [Instalación de Python](#schema8)
9. [Crear y Usar Entornos Virtuales](#schema9)
10. [Instalar Jupyter Notebook en tu entorno virtual](#schema10)


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


<hr>
<a name='schema6'></a>

## 6. Extensiones para Visual Studio Code

- Prettier - Code formatter
- Scala (Metals)
- HashiCorp Terraform
- Rainbow CSV
- Python
- Python Debugger
- Docker



<hr>
<a name='schema7'></a>

## 7. Aplicaciones 

- Descomprimidor: [The Unarchiver](https://apps.apple.com/es/app/the-unarchiver/id425424353?mt=12)

- Capturas de pantallas: [xnip](https://apps.apple.com/es/app/xnip-screenshot-annotation/id1221250572?mt=12)

- Mover y redimensionar ventanas: [Rectagle](https://rectangleapp.com/)

- Iniciar aplicaciones y buscar archivos: [Alfred](https://www.alfredapp.com/)

- Control de rato Logitech: [MX Master](https://www.logitech.com/es-es/software/logi-options-plus.html)


<hr>
<a name='schema8'></a>

## 8. Instalación de Python

1. Instalar Python con Homebrew

    - Abre la Terminal y ejecuta:

        ```sh
        brew install python
        ```
        Esto instala la última versión de Python 3, junto con pip3.

        El comando `brew` install python instala la versión más reciente de Python disponible a través de Homebrew, que generalmente es `Python 3`. Sin embargo, debido a la coexistencia histórica de `Python 2` y `Python 3`, el comando python puede referirse a `Python 2` en algunos sistemas. Para evitar cualquier ambigüedad, es mejor usar python3 y pip3 cuando trabajes con Python 3.
2. Verificar la Instalación de Python

    Para asegurarte de que la instalación se realizó correctamente y estás utilizando la versión correcta de Python, ejecuta:

    ```sh
    python3 --version
    ```
3. Verificar la Instalación de pip3

    También verifica que pip3 esté instalado:

    ```sh
    pip3 --version
    ```

<hr>
<a name='schema9'></a>

## 9.Crear y Usar Entornos Virtuales
Después de instalar `Python 3` y `pip3`, puedes proceder a crear y usar entornos virtuales para tus proyectos. 

### Crear un Entorno Virtual
1. Navega al directorio de tu proyecto:

2. Crea un entorno virtual usando `venv`, que **viene integrado con Python 3**:

    ```sh
    python3 -m venv nombre_del_entorno
    ```
### Activar el Entorno Virtual
Para activar el entorno virtual, ejecuta:

```sh
source nombre_del_entorno/bin/activate
```

Cuando el entorno virtual esté activado, verás el nombre del entorno en tu línea de comandos.

### Instalar Dependencias
Una vez activado el entorno virtual, instala las dependencias necesarias para tu proyecto:

```sh
pip install nombre_del_paquete
```
### Guardar Dependencias
Para guardar las dependencias en un archivo `requirements.txt`:

```sh
pip freeze > requirements.txt
```
### Desactivar el Entorno Virtual
Cuando termines de trabajar en tu proyecto, desactiva el entorno virtual ejecutando:

```sh
deactivate
```

<hr>
<a name='schema10'></a>

## 10. Instalar Jupyter Notebook en tu entorno virtual

1. Activar tu Entorno Virtual
Primero, asegúrate de que tu entorno virtual esté activado. Si no lo está, actívalo siguiendo estos pasos:

    ```sh
    source nombre_del_entorno/bin/activate
    ```

2. Instalar Jupyter Notebook
Una vez que tu entorno virtual esté activado, instala Jupyter Notebook usando pip:

    ```sh
    pip install jupyter
    ```

    La razón por la cual se usa pip en lugar de pip3 es que, una vez que estás dentro de un entorno virtual, el comando pip se refiere automáticamente al pip correspondiente a la versión de Python usada para crear el entorno virtual

3. Verificar la instalación de Jupyter Notebook:

    ```sh
    jupyter --version
    ```
4. Iniciar Jupyter Notebook:

    ```sh
    jupyter notebook
    ```