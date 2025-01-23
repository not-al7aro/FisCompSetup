# Instalación FisComp 💖

> [!NOTE]  
> Las descargas de cada programa pueden tardar un poco, tengan paciencia 😵‍💫

## Homebrew 🍺

Lo primero que hace falta es el instalador de paquetes 🥡 que se usa en Mac 🍎, Homebrew 🍺.
**Para instalarlo abrimos la terminal y pegamos el siguiente comando:**

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Al ejecutar este comando por primera vez es posible que se nos pida instalar las herramientas de desarrollo de Xcode🔨 y la contrasena, en ese caso aceptamos y esperamos a que termine la instalacion.

Homebrew 🍺 ya esta instalado, pero para poder usarlo es necesario agregarlo al PATH 👣 para que el sistema lo encuentre cada vez que lo utlicemos.
Al terminal de instalar Homebrew 🍺, se nos muestra un mensaje que nos indica como hacerlo, este mensaje dice algo asi como: 
```text
=> Next steps:
- Run these commands in your terminal to add Homebrew to your PATH
```
Los comandos seran parecidos, **pero no identicos** 😡, a estos:
```bash
echo >> /Users/[tu-nombre]/.[algo]profile
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/[tu-nombre]/.[algo]profile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

Copiamos los tres comandos que nos da y los pegamos en la terminal 💾.

Una vez instalado Homebrew 🍺, es muy sencillo instalar los paquetes 🥡 que necesitamos.

### Fortran 👴🏼

```bash
brew install gcc
brew install gfortran
```

### GNU Plot 📈

```bash
brew install gnuplot
```

### Geany 🧞‍♀️

```bash
brew install geany
```

> [!WARNING]  
> Antes de continuar busca Geany en el buscador de MAC 🍎 y abrelo y cierralo, de esta forma se crearan los archivos de configuracion necesarios.

### PATH 👣

En principio los programas se deberian haber añadido al PATH 👣 automaticamente.

Pero por si acaso podemos ejecutar 🥊:

```bash
echo 'export PATH="/opt/homebrew/bin:$PATH"' >> ~/.bash_profile
export ~/.bash_profile
```

```bash
echo 'export PATH="/opt/homebrew/bin:$PATH"' >> ~/.zshrc
export ~/.zshrc
```

## AUN NO HEMOS TERMINADO 🤓

Por ultimo hace falta configurar Geany 🧞‍♀️ para que pueda compilar programas en Fortran 👴🏼 e interpretar los scripts de Gnuplot 📈.

### Configuracion para Gnuplot 📈

Geany 🧞‍♀️ necesita unos archivos de configuracion especificos para poder interpretar los scripts de Gnuplot 📈.
Para copiarlos en el lugar necesario basta con correr estos tres comandos:

```bash
brew install wget
wget https://raw.githubusercontent.com/not-al7aro/FisCompSetup/refs/heads/main/files/filetype_extensions.conf -O ~/.config/geany/filetype_extensions.conf
wget https://raw.githubusercontent.com/not-al7aro/FisCompSetup/refs/heads/main/files/filetypes.Gnuplot.conf -O ~/.config/geany/filedefs/filetypes.Gnuplot.conf
```

Estos comandos instalan una herramienta que perimte descargar arhivos de forma remota 🥡 y los coloca donde deben estar ☝🏼.

### Configuracion para Fortran 👴🏼

Es posible que Fortran 👴🏼 funcione directamente 😔 sin hacer nada, sin embargo 😎, puede que haya que configurar Geany 🧞‍♀️ para que sepa donde buscar el compilador.

**Si Fortran 👴🏼 no funciona directamente**, la alternativa mas sencilla es configurar Geany 🧞‍♀️ manualmente:

1. Introducimos en la terminal lo siguiente:
```bash
echo $SHELL
```
Este comando nos dara una salida parecida a `/bin/bash`, `/bin/zsh`, `/usr/local/bin/bash`, etc.

1. Copiamos la salida de este comando con `Cmd+C`.

2. Ahora vamos a Geany 🧞‍♀️ y en la parter superior de la pantalla abrimos
```
Edit -> Settings -> Tools
```
Y en el campo `Shell` 🐚 pegamos lo que copiamos antes.

---

# POSIBLES ERRORES 🤬
No se, si tienes algun problema preguntame directamente a mi