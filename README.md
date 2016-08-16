#Deploy de una aplicacion .NET Core con Azure
Esta es una guia rapida de como hacer el deploy de una aplicacion .NET CORE en Mac y hacer su deploy con Azure, aun cuando se incluye la creacion de una aplicacion simple como ejemplo este workshop no se enfoca en la creacion de la aplicacion .NET CORE ni en los detalles de su funcionamiento, para detalles de la creacion de una aplicacion .NET CORE consulte el siguiente repositorio

---
Antes de comenzar necesitas:

##Instalar Git
Configuraremos nuestro 'Continuous Deployment' con Git por lo que es necesario tenerlo instalado.  
Para instalar Git ir a [git downloads](https://git-scm.com/downloads)

##Instalar .NET Core
Instalar pre-requisitos
Para poder utilizar .NET Core, primero necesitamos la ultima version de OpenSSL.  
La manera mas facil de obtenerlo es desde [Homebrew] (http://brew.sh/) Despues de instalar brew, hacer lo siguiente:

```sh
~$ brew update
~$ brew install openssl
~$ ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
~$ ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Instalar .NET Core SDK
La mejor manera de instalar .NET Core en macOS is descargando el [instalador oficial] (https://go.microsoft.com/fwlink/?LinkID=809124)  
Este instalador instalara los tools y los pondra en tu PATH para que puedan ejecutar .NET desde tu consola.  
Nota. Si tienes algun problema con la instalacion en macOS, consultar la pagina de [problemas conocidos] (https://github.com/dotnet/core/blob/master/cli/known-issues.md)  

Para verificar la instalacion exitosa puedes usar el siguiente comando en tu terminal
```sh
~$ dotnet --version
```

[.NET Framework Downloads] (https://www.microsoft.com/net/download#core):
* Windows https://www.microsoft.com/net/core#windows
* Docker https://www.microsoft.com/net/core#docker
* Linux RHEL https://www.microsoft.com/net/core#redhat
* Linux Ubuntu, Linux Mint https://www.microsoft.com/net/core#ubuntu
* Linux Debian https://www.microsoft.com/net/core#debian
* Linux Fedora https://www.microsoft.com/net/core#fedora
* Linux CentOS, Oracle Linux https://www.microsoft.com/net/core#centos
* Linux openSUSE https://www.microsoft.com/net/core#opensuse


##Instalar un editor de texto
Visual Studio Code corre en macOS y tiene soporte completo para .NET Core  
Puedes descargarlo en Visual Studio Code <https://code.visualstudio.com/> gratis e instalar la [extension para C#]   (https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp) si deseas tener una mejor experiencia.  

##Crear cuenta de Azure
Selecciona la opcion 'Start free' en [Azure Start Free] (https://azure.microsoft.com/en-us/free/)

---

##Crear una aplicacion .NET Core

#### Crear un folder
```sh
mkdir folderName
cd folderName
```

#### Consultar las opciones de templates disponibles
```sh
dotnet new -t –h
```

#### Generar los archivos del proyecto para un template de WebApp
```sh
dotnet new -t web
```

#### Restore de los paquetes
```sh
dotnet restore
```

#### Compilar el código
```sh
dotnet build
```

#### Correr la aplicacion localmente
```sh
dotnet run
```

#### Ir al sitio local, http://localhost:5000, debes ver algo similar a la sigueinte imagen

![localhost](/localhost.png?raw=true "localhost")

---

##Deploy .NET Core App con 
#### Crear una nueva WebApp en Azure
[https://tryappservice.azure.com/](https://tryappservice.azure.com/)

Cuando te pida seleccionar un tipo elige Web App 
![webapp](/webapp.png?raw=true "webapp")

Cuando te pida seleccionar un template elige ASP.NET Core 1, preferencialmente configura el lenguage con C#  
![ASP .NET Core 1](/aspnetcore1.png?raw=true "ASP .NET Core 1")

#### En el portal de Azure, configurar 'Continuous deployment' con Git
Luego de elegir crear, veras una opcion de 'Manage in Azure Portal'  
![Mange Azure](/manageazure.png?raw=true "Manage Azure")

En la seccion ![Deployment Source](/deploymentsource.png?raw=true "Deployment Source") 
En la seccion de 'Setup' ve a 'Choose Source' y elige 'Local Git Repository'  
![Local Git Repository](/localgitrepository.png?raw=true "Local Git Repository") 
Si es la primera vez que lo configras te pedira tus credenciales

#### Copiar Git URL para la WebApp desde el portal de Azure
Lo encontraras en la seccion de overview bajo el tag de 'Git Clone URL'  
![Git URL](/giturl.png?raw=true "git URL")


#### Agregar un remoto con la Git URL, desde la terminal

```sh
git remote add remoteName GitURL
```

#### Push a master para hacer el deploy

```sh
git push remoteName master
```

#### Ir al sitio actualizado
Puedes navegar a la URL del sitio o desde el portal de Azure elegir 'Browse'

---
##Referencias adicionales:

Para mas ejemplos visita .NET Core en [GitHub] (https://github.com/dotnet/core/)  
Consulta la [Documentacion de .NET] (http://docs.microsoft.com/dotnet) para aprender mas acerca de .NET Core  
Participa en nuestra [comunidad] (https://dotnet.github.io/support)  
