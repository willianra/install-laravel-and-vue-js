# install-laravel-and-vue-js 5.6
instalacion de lavel y vue js
1 installar composer en directorio xamp/htdos/php 
2. instalar laravel via composer
   c: xamp/htdocs>   composer globlal require "laravel/install"
3. crear un nuevo proyecto 
#configurar  css , js blade 
# configuracion de laravel mixin 

  c: xamp/htdocs> laravel new  demo
#instalacion de node js 
 1 descargar del sitio https://nodejs.org/es/download/ y ejecutar el programa 
 2 dentro de la aplicacion ejecutar para que se instalen las dependencias del archivo yarn
    c: xamp/htdocs/demo>npm install 
    c: xamp/htdocs/demo>npm run dev   // para crear los archivos mixing de css y js dentro de public
    
 #migraciones
 php artisan make:migration create_nombre_table
 
 #configuracion con postgres 
  .env 
  db_conection:pgsql
  username:postgres
  port:5432
  password:123
 1.- una vez creada la tabla y configurada el gestor de db 
 hacer una migracion para generar las tablas
 comando :php artisan migrate
    
