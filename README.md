# primeros-pasos-mac

0. [Instalar una terminal, `iTerm2`](#schema0)
1. [Instalación de Homebrew](#schema1)
2. [Instalación de Git con Homebrew](#schema2)
3. [Configurar GITHUB](#schema3)
4. [Instalar Visual Studio Code](#schema4)
5. [Añadir el comando code manualmente al PATH](#schema5)
6. [Extensiones para Visual Studio Code](#schema6)
7. [Aplicaciones](#schema7)
8. [Instalación de Python](#schema8)
9. [Crear y Usar Entornos Virtuales](#schema9)
10. [Instalar Jupyter Notebook en tu entorno virtual](#schema10)
11. [Instalar AWS CLI usando Homebrew](#schema11)
12. [Instalar Terraform usando Homebrew](#schema12)
13. [Instalar OpenJDK con Homebrew](#schema13)
14. [Guía para Instalar y Configurar IntelliJ IDEA en tu Mac Air M3 (para Scala y Spark)
](#schema14)
15. [Instalar Docker en macOS](#schema15)
16. [Instalar FSCrawler](#schema16)
17. [Instalar Scala](#schema17)
18. [Instalar Pyspark](#schema18)
19. [Instalar PostgreSQL](#schema19)
20. [Cómo usar DBeaver con PostgreSQL](#schema20)
21. [Instalación de dbt](#schema21)
22. [Notas](#schemanotas)


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
- Manejo y control de la bataría mientras está el cargador enchufado: [AlDente](https://apphousekitchen.com/)

- Configuración de la terminal [Oh My Zsh](https://ohmyz.sh/)

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
Con esta instalación se instala la última versión de java, si la quieres para trabjar con scala mejor es la versión 11, salta es capítulo y ve al siguiente punto, [14](#schema14). 
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

## 14 Guía para Instalar y Configurar IntelliJ IDEA (para Scala y Spark)
Yo ya tengo instalado el java 21, van a convivir las dos version, si solo quieres la version 11 salta el paso anterior, [13](#schema13).
1. Instalar IntelliJ IDEA
    - Ve a [IntelliJ IDEA](https://www.jetbrains.com/es-es/idea/download/download-thanks.html?platform=macM1&code=IIC)
    - Descarga la versión Community (es gratuita y suficiente para Scala y Spark).
    - Abre el archivo .dmg descargado y arrastra IntelliJ IDEA a la carpeta de Aplicaciones.
    - Ejecuta IntelliJ IDEA y acepta los términos de uso.


2. Instalar el Plugin de Scala
    - En IntelliJ IDEA, ve a "Preferences" (Cmd + ,).
    - En el menú lateral, selecciona "Plugins".
    - Busca "Scala" en la barra de búsqueda.
    - Haz clic en "Install" y reinicia IntelliJ IDEA si lo solicita.

3. Instalar JDK 11 usando Homebrew:
    1. Abre la terminal de tu Mac.
    2. Ejecuta:
    ```bash
    brew install openjdk@11
    ``` 
    3. Verificar la instalación: Una vez completada la instalación, verifica la ubicación de Java 11:

    ```bash
        brew --prefix openjdk@11
    ```
    Esto debería devolver una ruta similar a:

    ```bash
    /opt/homebrew/opt/openjdk@11
    ```
    4. Crear enlaces simbólicos para que el sistema reconozca Java 11:

    ```bash
    sudo ln -sfn /opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-11.jdk
    ```
    5. Agregar Java 11 al PATH:
    ```bash
    # Configuración para Java (Java 21 y Java 11)
    export JAVA_HOME_21=$(/usr/libexec/java_home -v 21)
    export JAVA_HOME_11="/opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk/Contents/Home"

    # Seleccionar la versión de Java (por defecto Java 21)
    export JAVA_HOME=$JAVA_HOME_21
    export PATH="$JAVA_HOME/bin:$PATH"
    ```
    6. Actualizar la configuración:

    ```bash
    source ~/.zshrc
    ```

    7. Verificar la instalación:

    ```bash
    java -version
    ```
    8. Alternar Entre Java 21 y Java 11
    Para usar Java 11 temporalmente en una sesión:

    ```bash
    export JAVA_HOME=$JAVA_HOME_11
    export PATH="$JAVA_HOME/bin:$PATH"
    java -version
    ```
4. Configurar Java 11 en IntelliJ IDEA
- Abre IntelliJ IDEA:
    - Abre IntelliJ IDEA en tu Mac.
- Ve a Preferencias:
    - En el menú de IntelliJ IDEA, ve a "IntelliJ IDEA" → "Preferences" (Cmd + ,).
- Configura el JDK:
    - En el panel izquierdo, navega a:
    `Build, Execution, Deployment → Build Tools → SBT`
- En la sección JDK, haz clic en el menú desplegable y selecciona:
    - Si Java 11 ya aparece, selecciona Java 11.
    - Si Java 11 no aparece, haz clic en "Add JDK", navega a:
    `/opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk/Contents/Home`
    Luego haz clic en "Open" para agregarlo.
- Haz clic en "Apply" y luego en "OK" para guardar los cambios.

5. Crear un Proyecto Nuevo en IntelliJ IDEA y Configurarlo para Java 11:

    1. Crear un Nuevo Proyecto en IntelliJ IDEA:
        - Abre IntelliJ IDEA y selecciona "New Project" desde la pantalla principal.
        - En el asistente de creación de proyectos, selecciona "Scala" como el tipo de proyecto si vas a trabajar con Spark (si no ves "Scala", asegúrate de tener el plugin de Scala instalado).
        - En el siguiente paso, selecciona la opción "JDK 11" si ya lo has configurado, o si no, selecciona el JDK correcto. Si no aparece, puedes agregarlo manualmente como lo hicimos antes. Para Java 11, busca la ruta de instalación de OpenJDK:
        `/opt/homebrew/opt/openjdk@11/libexec/openjdk.jdk/Contents/Home`

        - Elige "SBT" como herramienta de construcción si quieres trabajar con SBT (Scala Build Tool), o si prefieres Maven o Gradle, selecciona la opción adecuada.

    2. Configurar el SDK de Java 11 para el Proyecto:
    Si en el paso anterior no seleccionaste el JDK correcto (Java 11), puedes hacerlo ahora en las configuraciones del proyecto:
    - Haz clic derecho en el nombre del proyecto y selecciona "Open Module Settings" (F4).
    - En la pestaña "Project", en la opción "Project SDK", selecciona "Java 11".
    - También puedes configurar el "Project language level" a "11 - Local variable syntax for lambda parameters".
    3. Agregar Dependencias de Spark en el Proyecto:
    - Si estás trabajando con Spark en un proyecto Scala, necesitarás agregar la dependencia de Spark. Si estás usando SBT, agrega lo siguiente a tu archivo build.sbt:
    ```scala
    name := "TestSparkJava11"

    version := "0.1"

    scalaVersion := "2.12.10" // o cualquier versión de Scala compatible

    libraryDependencies += "org.apache.spark" %% "spark-core" % "3.4.0"
    libraryDependencies += "org.apache.spark" %% "spark-sql" % "3.4.0"
    ```
    4. Escribir el Código de Prueba:
    - Una vez que el proyecto esté configurado, puedes escribir un archivo para probar que todo esté funcionando correctamente. Por ejemplo, crea un archivo de Scala con el siguiente código:

    ```scala
        import org.apache.spark.sql.SparkSession

    object TestSparkJava11 {
    def main(args: Array[String]): Unit = {
        val spark = SparkSession.builder()
        .appName("Test Java 11 with Spark")
        .master("local[*]")
        .getOrCreate()

        val data = Seq(("Scala", 2.12), ("Spark", 3.4), ("Java", 11))
        val df = spark.createDataFrame(data).toDF("Tecnología", "Versión")

        df.show()

        spark.stop()
    }
    }
    ```
    5. Ejecutar el Proyecto:
        - Haz clic derecho en el archivo de prueba y selecciona "Run 'TestSparkJava11'".











<hr>
<a name='schema15'></a>



## 15. Instalar Docker en macOS:
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


<hr>
<a name='schema16'></a>

## 16. Instalar FSCrawler

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

<hr>
<a name='schema167></a>

## 17. Instalar Scala

1. Verifica que Java esté instalado correctamente ejecutando:

    ```bash
    java -version
    ```
    - Si no está instalado ir a: 13. [Instalar OpenJDK con Homebrew](#schema13)


2. Instalar Scala.
- En la Terminal, ejecuta el siguiente comando para instalar Scala:

    ```bash
    brew install scala
    ```
- Verifica la instalación ejecutando el siguiente comando:

    ```bash
    scala -version
    ```
3. Instalar sbt (opcional, pero recomendado)
- `sbt` es la herramienta de construcción y administración de proyectos de Scala.

- Para instalar sbt, ejecuta el siguiente comando:

    ```bash
    brew install sbt
    ```
- Verifica la instalación con:

    ```bash
    sbt sbtVersion
    ```


<hr>
<a name='schema18'></a>

## 18. Instalar Pyspark

1. Instalar Java Development Kit (JDK), spark run on java 8, 11, or 17
    - https://www.oracle.com/java/technologies/downloads/#jdk21-mac

2. Instalar Apache Spark
    - https://spark.apache.org/downloads.html

3. Renombar la descarga anterior a por ejemplo `spark` y moverla a alguna carpeta por ejemplo `Apps` para saber donde esta Apache Spark.
Ahora toca de configurar  las variables de entorno para que PySpark pueda encontrar tu instalación de Spark.
- Abre tu archivo de configuración de shell (como `.zshrc` o .bash_profile) y añade estas líneas al final del archivo:
```bash

# Configuración para PySpark
export SPARK_HOME="/Users/patricia/Apps/spark"  
export PATH="$SPARK_HOME/bin:$PATH"

# Configuración para usar Python correcto con PySpark
export PYSPARK_PYTHON="/opt/homebrew/bin/python3"  
# Configuración para Java
export JAVA_HOME=$(/usr/libexec/java_home -v 21)
export PATH=$JAVA_HOME/bin:$PATH

```
<hr>
<a name='schema19'></a>

## 19. Instalar PostgreSQL

1. Instala PostgreSQL:

```bash
brew install postgresql
```
2. Una vez instalado, inicia el servicio:

```bash
brew services start postgresql
```
3. Verifica que PostgreSQL está instalado correctamente:

```bash
psql --version
```
4. (Opcional, pero útil) Crea un usuario con tu nombre de macOS si no existe:

```bash
createuser -s $(whoami)
```
5. Conéctate a PostgreSQL:

```bash
psql postgres
```
<hr>
<a name='schema20'></a>

## 20. Cómo usar DBeaver con PostgreSQL

1. Descargar e instalar DBeaver
    1. Ve a la web oficial de DBeaver:
        https://dbeaver.io/download/

    2. Haz clic en el botón de descarga para macOS (dmg installer).

    3. Abre el archivo .dmg descargado y arrastra DBeaver a tu carpeta de Aplicaciones como con cualquier app de Mac.

    4. Abre DBeaver. Si te pide permiso porque es de un desarrollador no identificado:

        - Ve a Preferencias del sistema > Seguridad y privacidad > General.

        - Haz clic en "Abrir de todos modos".

2. Crear una conexión a PostgreSQL
    1. En la pantalla principal de DBeaver, haz clic en:

        - "Nueva conexión" o el ícono de plug ➕ en la barra superior.

    2. Aparecerá una ventana con muchas bases de datos.

        - Elige PostgreSQL (puedes buscarlo en la barra superior).

    3. Haz clic en "Siguiente".

3. Configurar los datos de conexión
    1. Aquí introduces los detalles para conectarte a tu servidor PostgreSQL local:


        - Host	-> localhost
        - Puerto ->	5432
        - Base de datos ->	dbt_tutorial (o postgres si aún no la creaste)
        - Usuario ->	tu usuario de macOS (por ejemplo, patricia)
            - ¿No sabes cuál es tu usuario?
                Puedes ver tu usuario actual ejecutando en la terminal:

                ```bash
                whoami
                ```
        - Contraseña	déjalo en blanco si no configuraste una, o escribe la que hayas definido



5. ¿Y si aún no has creado la base de datos dbt_tutorial?
    1. Puedes hacerlo desde el cliente psql en terminal:

    ```bash
    createdb dbt_tutorial
    ```
    2. O también desde DBeaver:

        - Conéctate a postgres.

        - Haz clic derecho > "Create new database".
<hr>
<a name='schema21'></a>

21. [Instalación de dbt](#schema21)


<hr>
<a name='schema1'></a>

## 1. Instalación de dbt
1. Crear un entorno virtual en la carpeta actual
```bash
python3 -m venv venv-dbt
```
2. Activa el entorno virtual
```bash
source venv-dbt/bin/activate
```
3. Instala dbt-core y el adaptador de tu base de datos (ej: PostgreSQL):
```bash
pip install dbt-core dbt-postgres
```
4. Verifica la instalación:

```bash
dbt --version
```

<hr>
<a name='schemanotas'></a>

# Notas 
A tener en cuenta lo cambios necesarios para el archivo `.~/.zshrc` que los path que yo pongo son en mi configuración a lo mejor debes hacer algún cambio.