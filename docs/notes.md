# Apuntes del curso - Tailwind CSS

## 1. Configuración inicial

#### Instalación de dependencias
1. ``` npm init -y ```
2. ``` npm install tailwindcss autoprefixer postcss-cli ```

#### Inicialización - Creación de archivo de configuración tailwindcss
* Archivo de configuración Tailwind (vacío)
``` npx tailwindcss init ```
* Archivo de configuración completo
``` npx tailwindcss init tailwind.config.full.js --full ``` 

#### Creación de archivo de configuración postcss

1. Se crea el archivo postcss.config.js
``` touch postcss.config.js ```

2. Exportamos un modulo con el plugin de tailwindcss

*postcss.config.js*
```javascript 
module.exports = {
    plugins: [
        require('tailwindcss'),
        require('autoprefixer')
    ]
}; 
 ```

#### Configuración de los estilos con tailwindcss

1. Crear una carpeta 'css' donde se ubicaran los archivos css

``` mkdir css ```
``` touch css/tailwind.css ``` --> creación del archivo 'tailwind.css' dentro de la carpeta.

2. Configuración 

```css 
@tailwind base; 
@tailwind components;
@tailwind utilities;
 ```

3. Editamos el script en el package.json

```json
"scripts": {
    "build": { "postcss css/tailwind.css -o public/css/styles.css" },
}
 ```

4. Comandos:
    * ``` npm run dev ``` -> compila el projecto y lo corre para entorno de desarrollo.
    * ``` npm run build ``` -> genera un directorio css con el archivo style.css en la carpeta public.
