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
11. [Instalar AWS CLI usando Homebrew](#schema11)
12. [Instalar Terraform usando Homebrew](#schema12)
13. [Instalar OpenJDK con Homebrew](#schema13)
14. [Instalar Docker en macOS](#schema14)

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

<hr>
<a name='schema11'></a>

## 11. Instalar AWS CLI usando Homebrew
1. Instalación AWS CLI

Ejecuta el siguiente comando en la Terminal:

```bash
brew install awscli
```

2. Verificar la instalación
Para asegurarte de que la AWS CLI se haya instalado correctamente, verifica la versión instalada:

```bash
aws --version
```
3. Configurar AWS CLI
Después de instalar la AWS CLI, necesitas configurarla con tus credenciales de AWS. Puedes hacerlo usando el comando aws configure. Ejecuta el siguiente comando en la Terminal:

```bash
aws configure
```
Se te pedirá que ingreses tu `AWS Access Key ID`, `AWS Secret Access Key`, `región` predeterminada y `formato de salida` predeterminado. Puedes obtener tus claves de acceso desde la consola de administración de AWS.

```bash
AWS Access Key ID [None]: YOUR_ACCESS_KEY
AWS Secret Access Key [None]: YOUR_SECRET_KEY
Default region name [None]: YOUR_PREFERRED_REGION
Default output format [None]: json
```

4. Verificar la configuración
Para asegurarte de que la configuración se haya realizado correctamente, puedes ejecutar un comando sencillo como listar tus buckets de S3:

```bash
aws s3 ls
```
Si todo está configurado correctamente, deberías ver una lista de tus buckets de S3 (si tienes alguno).

5. Paso adicional: Actualizar la AWS CLI
Si necesitas actualizar la AWS CLI en el futuro, puedes hacerlo con Homebrew usando el siguiente comando:

```bash
brew upgrade awscli
```
### Problemas Comunes y Soluciones
- **Permisos insuficientes:** Si encuentras problemas de permisos durante la instalación de Homebrew o AWS CLI, puedes necesitar agregar sudo antes de los comandos para ejecutarlos como administrador.

- **Problemas de red:** Si la instalación falla debido a problemas de red, asegúrate de que tu conexión a internet esté funcionando correctamente y vuelve a intentarlo.

<hr>
<a name='schema12'></a>

## 12. Instalar Terraform usando Homebrew
Ejecuta el siguiente comando en la Terminal:

```bash
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
```
2. Verificar la instalación
Para asegurarte de que Terraform se haya instalado correctamente, verifica la versión instalada:

```bash
terraform -v
```

<hr>
<a name='schema13'></a>



## 13. Instalar OpenJDK con Homebrew
1. Instalar OpenJDK
    Para instalar OpenJDK, usa el siguiente comando:

        ```bash
        brew install openjdk
        ```
2. Configurar el Entorno
    
    - Después de la instalación, necesitas configurar el entorno para usar OpenJDK. Esto implica actualizar tu archivo` ~/.zshrc` (o ~/.bash_profile si usas bash) para incluir las rutas de OpenJDK en tu `PATH` y establecer la variable `JAVA_HOME`.

    - Editar el Archivo ~/.zshrc
        1. Abre el archivo ~/.zshrc en un editor de texto:

            ```bash
            code ~/.zshrc
            ```
        2. Añade o actualiza las siguientes líneas para configurar el PATH y JAVA_HOME:

            ```bash
            # Configura el PATH para incluir Homebrew, Visual Studio Code y OpenJDK
            export PATH="/opt/homebrew/bin:/usr/local/bin:/Applications/Visual Studio Code.app/Contents/Resources/app/bin:/opt/homebrew/opt/openjdk/bin:$PATH"

            # Configura JAVA_HOME para que apunte a OpenJDK instalado con Homebrew
            export JAVA_HOME="/opt/homebrew/opt/openjdk/libexec/openjdk.jdk/Contents/Home"
            ```
            - La primera línea asegura que las rutas necesarias están incluidas en el `PATH`.
            - La segunda línea establece `JAVA_HOME` para apuntar a la ubicación de OpenJDK.
        3. Guarda y cierra el archivo (Ctrl+O para guardar y Ctrl+X para salir si usas nano).

3. Recargar la Configuración del Shell.

    Para aplicar los cambios realizados en ~/.zshrc, recarga la configuración:

        ```bash
        source ~/.zshrc
        ```
4. Verificar la Instalación

    Verifica que Java esté correctamente instalado y configurado:

    - Verificar la Versión de Java:

        ```bash
        java --version
        ```
        Deberías ver la versión de OpenJDK que instalaste.

    - Verificar la Configuración de JAVA_HOME:

        ```bash
        echo $JAVA_HOME
        ```
        Debería mostrar /opt/homebrew/opt/openjdk/libexec/openjdk.jdk/Contents/Home.

    - Verificar el PATH:

        ```bash
        echo $PATH
        ```
        Asegúrate de que las rutas incluyan las ubicaciones necesarias, como /opt/homebrew/opt/openjdk/bin.
5. Reinicio de la Terminal:

    Reinicia la terminal para aplicar completamente los cambios y asegurarte de que la configuración del entorno se haya cargado en todas las sesiones de terminal.

<hr>
<a name='schema14'></a>



## 14. Instalar Docker en macOS:
1. Verifica los Requisitos del Sistema:

    - Asegúrate de que tu MacBook Air con chip M3 esté ejecutando macOS 14 o una versión compatible.
2. Descargar Docker Desktop:
    - Ve a la página oficial de Docker para descargar Docker Desktop para Mac: [Descargar Docker Desktop](https://docs.docker.com/desktop/install/mac-install/).
    - En la página de descargas, selecciona la versión adecuada para "Apple Silicon" (M1, M2, M3, etc.), ya que el chip M3 es parte de esta arquitectura.

3. Instalar Docker Desktop:

    - Abre el archivo .dmg descargado.
    - Arrastra el ícono de Docker a la carpeta "Aplicaciones" para instalarlo.

4. Iniciar Docker Desktop:

    - Abre la carpeta "Aplicaciones" y haz doble clic en el ícono de Docker para iniciarlo.
    - Es posible que se te pida que aceptes algunos permisos de seguridad. Acepta estos permisos para que Docker pueda funcionar correctamente.

5. Configurar Docker Desktop:

    - La primera vez que abras Docker, es posible que se te pida que completes una serie de pasos de configuración inicial.
    - Docker puede requerir que inicies sesión con tu cuenta Docker Hub. Si no tienes una cuenta, puedes crear una gratuitamente.
6. Verificar la Instalación:

    - Abre una Terminal en tu MacBook Air.
    - Ejecuta el siguiente comando para asegurarte de que Docker esté funcionando correctamente:
        ```bash
        docker --version
        ```
    - También puedes probar con el siguiente comando para verificar que Docker está corriendo:
        ```bash
        docker run hello-world
        ```
    - Esto descargará una imagen de prueba y ejecutará un contenedor que imprimirá un mensaje de bienvenida si todo está funcionando correctamente.
7. Actualizar Docker Desktop:

    - Docker Desktop se actualiza automáticamente, pero puedes verificar manualmente si hay actualizaciones disponibles en la aplicación Docker Desktop, yendo a Docker Desktop en la barra de menús y seleccionando Check for Updates.


## 15. Instalar FWCrawler

1. Visitar el [Tutorial](https://fscrawler.readthedocs.io/en/latest/user/tutorial.html)
2. Descargar fscrawler del [sitio web](https://fscrawler.readthedocs.io/en/latest/installation.html#installation)
    - Descargar la imagen con docker
        ```bash
        docker pull dadoonet/fscrawler
        ```
    - Este comando descarga la imagen de Docker de FSCrawler desde Docker Hub. Es el primer paso necesario para poder ejecutar FSCrawler en un contenedor.

3. Ejecutar FSCrawler con un trabajo específico
```bash
docker run -it --rm \
     -v ~/.fscrawler:/root/.fscrawler \
     -v ~/tmp:/tmp/es:ro \
     dadoonet/fscrawler fscrawler job_name
```
- Este comando ejecuta FSCrawler en un contenedor de Docker con las siguientes opciones:

    - -it: Inicia el contenedor en modo interactivo.
    - --rm: Elimina el contenedor automáticamente cuando se detiene.
    - -v ~/.fscrawler:/root/.fscrawler: Monta el directorio de configuración local de FSCrawler (~/.fscrawler) en el contenedor. Aquí es donde se almacenarán las configuraciones de FSCrawler.
    - -v ~/tmp:/tmp/es:ro: Monta la carpeta local ~/tmp en el contenedor como read-only en /tmp/es. Esta es la carpeta que FSCrawler rastreará.
    - dadoonet/fscrawler: Especifica la imagen de Docker a usar.
    - fscrawler job_name: Indica a FSCrawler que ejecute un trabajo específico (job_name).
4. Ejecutar FSCrawler con configuraciones y archivos adicionales
```bash
docker run -it --rm \
     -v ~/.fscrawler:/root/.fscrawler \
     -v ~/tmp:/tmp/es:ro \
     -v "$PWD/external:/usr/share/fscrawler/external" \
     dadoonet/fscrawler fscrawler job_name
```
- Este comando es similar al anterior, pero incluye una opción adicional:

    - -v "$PWD/external:/usr/share/fscrawler/external": Monta el directorio external desde tu directorio de trabajo actual en el contenedor. Este directorio puede contener configuraciones o archivos adicionales que FSCrawler necesita.
5. Configuración del Trabajo (job_name)
    - Cuando ejecutas FSCrawler por primera vez, se creará un archivo de configuración para el trabajo especificado (job_name). Podrás encontrar este archivo en `~/.fscrawler/job_name/_settings.yaml` en tu sistema. Puedes editar este archivo para ajustar la configuración de FSCrawler.
    
6. Ejecutar y Verificar
- Una vez que todo esté configurado, FSCrawler debería empezar a procesar los archivos en la carpeta montada `~/tmp` y enviar los datos a tu instancia de Elasticsearch.

    - Consideraciones
        - Elasticsearch: Asegúrate de que tienes una instancia de Elasticsearch corriendo y accesible para que FSCrawler pueda enviar los datos. Si no tienes una instancia de Elasticsearch, puedes levantar una utilizando Docker también.
        - Permisos: Si tienes problemas de permisos, asegúrate de que las carpetas que estás montando sean accesibles por el usuario bajo el cual Docker se está ejecutando.
