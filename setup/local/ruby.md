## Ruby Setup

Para nuestros desarrollos en ruby utilizamos el manejador de versiones [rbenv](https://github.com/rbenv/rbenv) y algunos plugins.

```bash
# Instala rbenv y ruby-build
brew install rbenv ruby-build

# Instala plugins
brew install rbenv-vars rbenv-aliases rbenv-default-gems
```

Luego debes cargar rbenv en tu shell para que puedas acceder a las diferentes versiones. Para esto debes agregar la siguiente linea en tu `.bash_profile` o `.zshrc` dependiendo del shell que uses.

```bash
eval "$(rbenv init -)"
```

### Instalando versiones de ruby

Para instalar nuevas versiones de ruby puedes usar el plugin [ruby-build](https://github.com/rbenv/ruby-build)

```bash
# Listar todos las versiones disponibles para instalar
rbenv install --list

# Instalar una version en particular
rbenv install 2.4.1

# Actualizar las versiones de ruby disponibles para instalar
brew upgrade ruby-build
```

> **Recomendación**: Define alguna version de ruby que quieras para tener como global haciendo `rbenv global 2.4.1`  De esta manera no estarás usando la version de ruby que trae el sistema operativo. Esto hace que sea más seguro ya que no necesitas usar `sudo` para instalar gemas.

> **TIP**: Las versiones de ruby quedan instaladas en `$HOME/.rbenv/versions`

> **TIP**: El paquete `rbenv-default-gems` tiene como objetivo instalar gemas automáticamente cuando instalas una nueva version de ruby. Para esto crea un archivo en `~/.rbenv/default-gems` y agrega línea por línea el nombre de las gemas que quieres que se instalen. Buenos candidatos son `bundler` y `rails`

### Ruby Aliases

Como estandar en Platanus usamos aliases para definir las versiones de ruby que utilizan los proyectos. De esta manera nos evitamos tener que actualizar los proyectos cada vez que instalas una nueva version de ruby. Esto nos ayuda en menos manteción y en menos uso de espacio en disco.

Los aliases son simplemente symbolic links de una version de ruby con un nombre en particular. Estos aliases podrían ser nombre arbitrarios, pero nosotros usamos la version de ruby sin el `patch`

Para manejar estos aliases, puedes usar el plugin de [rbenv-aliases](https://github.com/tpope/rbenv-aliases) que crea los alias automáticamente al instalar nuevas versiones de ruby.

```bash
# Listar los aliases
rbenv alias

2.2 => 2.2.7
2.3 => 2.3.4
2.4 => 2.4.1
```
