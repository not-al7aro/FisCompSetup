# Instalar TODO

## Homebrew

Lo primero que hace falta es el instalador de paquetes que se usa en Mac, Homebrew.
**Para instalarlo abrimos la terminal y pegamos el siguiente comando:**

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Al ejecutar este comando por primera vez es posible que se nos pida instalar las herramientas de desarrollo de Xcode y la contrasena, en ese caso aceptamos y esperamos a que termine la instalacion.

Homebrew ya esta instalado, pero para poder usarlo es necesario agregarlo al PATH para que el sistema lo encuentre cada vez que lo utlicemos.
Al terminal de instalar Homebrew, se nos muestra un mensaje que nos indica como hacerlo, este mensaje dice algo asi como: 
```text
=> Next steps:
- Run these commands in your terminal to add Homebrew to your PATH
```
Copiamos los dos comandos que nos da y los pegamos en la terminal.

Una vez instalado Homebrew, es muy sencillo instalar los paquetes que necesitamos.

### Fotran

```bash
brew install gcc
brew install gfortran
```

### GNU Plot

```bash
brew install gnuplot
```

### Geany

```bash
brew install geany
```

En principio los programas se deberian haber añadido al PATH automaticamente.

## AUN NO HEMOS TERMINADO

Por ultimo hace falta configurar Geany para que pueda compilar programas en Fortran e interpretar los scripts de Gnuplot.

### Para los scripts de Gnuplot

Geany necesita unos archivos de configuracion especificos para poder interpretar los scripts de Gnuplot.
Para copiarlos en el lugar necesario basta con correr estos tres comandos:

```bash
brew install wget
wget https://raw.githubusercontent.com/not-al7aro/FisCompSetup/refs/heads/main/files/filetype_extensions.conf -O ~/.config/geany/filetype_extensions.conf
wget https://raw.githubusercontent.com/not-al7aro/FisCompSetup/refs/heads/main/files/filetypes.Gnuplot.conf -O ~/.config/geany/filedefs/filetypes.Gnuplot.conf
```

Estos comandos instalan una herramienta que perimte descargar arhivos de forma remota y los coloca donde deben estar.

## Para Fortran

Es posible que Fortran funcione directamente sin hacer nada, sin embargo, puede que haya que configurar Geany para que sepa donde buscar el compilador.

Este problema ocurre porque Geany trata de utilizar una terminal diferente a la utilizada para instalar el resto de programas, es muy posible que esto se solucione simplemente haciendo:

```bash
echo "export PATH=/opt/homebrew/bin:$PATH" >> ~/.bash_profile && source ~/.bash_profile
```

**Si esto no funciona**, la alternativa mas sencilla es configurar Geany manualmente:

1. Introducimos en la terminal lo siguiente:
```bash
echo $SHELL
```
Este comando nos dara una salida parecida a `/bin/bash`, `/bin/zsh`, `/usr/local/bin/bash`, etc.

2. Copiamos la salida de este comando con `Cmd+C`.

3. Ahora vamos a Geany y en la parter superior de la pantalla abrimos
```
Edit -> Settings -> Tools
```
Y en el campo `Shell` pegamos lo que copiamos antes.