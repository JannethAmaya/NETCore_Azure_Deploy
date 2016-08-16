#DEPLOY de una aplicacion .NET Core con Azure
Esta es una guia rapida de como hacer el deploy de una aplicacion .NET CORE en Mac y hacer su deploy con Azure, aun cuando se incluye la creacion de una aplicacion simple como ejemplo este workshop no se enfoca en la creacion de la aplicacion .NET CORE ni en los detalles de su funcionamiento, para detalles de la creacion de una aplicacion .NET CORE consulte el siguiente repositorio


Antes de comenzar necesitas
**Instalar Git**
Configuraremos nuestro 'Continuous Deployment' con Git por lo que es necesario tenerlo instalado
Para instalar Git ir a https://git-scm.com/downloads

**Instalar .NET Core**
Instalar pre-requisitos
Para poder utilizar .NET Core, primero necesitamos la ultima version de OpenSSL. La manera mas facil de obtenerlo es desde Homebrew <http://brew.sh/> Despues de instalar brew, hacer lo siguiente:
~$ brew update
~$ brew install openssl
~$ ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
~$ ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/

Instalar .NET Core SDK
La mejor manera de instalar .NET Core en macOS is descargando el instalador oficial <https://go.microsoft.com/fwlink/?LinkID=809124> 
Este instalador instalara los tools y los pondra en tu PATH para que puedan ejecutar .NET desde tu consola.
Nota. Si tienes algun problema con la instalacion en macOS, consultar la pagina de problemas conocidos <https://github.com/dotnet/core/blob/master/cli/known-issues.md>

Para verificar la instalacion exitosa puedes usar el siguiente comando en tu terminal
~$ dotnet --version

.NET Framework Downloads https://www.microsoft.com/net/download#core
Windows https://www.microsoft.com/net/core#windows
Docker https://www.microsoft.com/net/core#docker
Linux RHEL https://www.microsoft.com/net/core#redhat
Linux Ubuntu, Linux Mint https://www.microsoft.com/net/core#ubuntu
Linux Debian https://www.microsoft.com/net/core#debian
Linux Fedora https://www.microsoft.com/net/core#fedora
Linux CentOS, Oracle Linux https://www.microsoft.com/net/core#centos
Linux openSUSE https://www.microsoft.com/net/core#opensuse


**Instalar un editor de texto**
Visual Studio Code corre en macOS y tiene soporte completo para .NET Core
Puedes descargarlo en Visual Studio Code <https://code.visualstudio.com/> gratis e instalar la extension para C# <https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp> si deseas tener una mejor experiencia.

**Crear cuenta de Azure**
Selecciona la opcion 'Start free' en https://azure.microsoft.com/en-us/free/



#Crear una aplicacion .NET Core

#Deploy .NET Core App con 




Para mas ejemplos visita .NET Core en GitHub <https://github.com/dotnet/core/>
Consulta la Documentacion de .NET para aprender mas acerca de .NET Core <http://docs.microsoft.com/dotnet>
Participa en nuestra comunidad <https://dotnet.github.io/support>
