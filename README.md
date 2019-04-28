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
    
 #migraciones o crear una tabla por comando 
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
    
#como solucionar el error  despues de la migracion
In Connection.php line 458:
  SQLSTATE[42000]: Syntax error or access violation: 1071 Specified key was too long; max key length is 767 bytes
1.-buscar en documentacion index length mysql
https://laravel.com/docs/5.6/migrations
compiar este codigo dentro de app/providers/appServiceProvider
 
 2.-agregar el use debajo del usede service provier por defecto 
 use Illuminate\Support\Facades\Schema;
 luego
 3.-dentro de la funcion boot 
 instalacion de paginacion
 use Illuminate\Support\Facades\DB;
   public function boot()
    {
        Schema::defaultStringLength(191);

    }
4 FINALMENTE EJECUTAR LA MIGRACION 
   ojo si no migra alguna tabla se debe  borrar las tablas de las base de datos y ejercutar php artisan migrate 
   como resutado debera crear las tablas en php myadmin  
 #CREACION DE MODELOS
1 .- php artisan make:model Categoria   /// con mayuscula al inicio
5 CREANDO UN CRUD RELACIONAL 
   1 MIGRACION:php artisan make:migration create_articulos_table
6 instalacion de codigo de barras 
https://github.com/lindell/vue-barcode
# crud persona y tabla usuario 
php artisan make:migration create_personas_table
php artisan migrate
php artisan make:model Persona   //primera letra con mayuscula
php artisan make:controller ClienteController
# crud proveedores
php artisan make:migration create_proveedores_table
php artisan migrate 
php artisan make:model Proveedor
php artisan make:controller ProveedorController
# crud Roles
php artisan make:migration create_roles_table
php artisan make:model Rol
php artisan make:controller RolController
# usuario
php artisan migrate 
php artisan make:controller UserController
# autorizacion
php artisan make:auth   //crea un scaffol de autentificacion

# para ver las rutas 
php artisan route:list
# middleware
php artisan make:middleware Administrador
php artisan make:middleware Vendedor
php artisan make:middleware Almacenero
# ingresos y detalle 
primero crear las migraciones 
php artisan make:migration create_ingresos_table
php artisan make:migration create_detalle_ingresos_table
php artisan make:model Ingreso
# componente vue select 
npm install vue-select
https://vue-select.org/
# reportes con dompdf
https://github.com/barryvdh/laravel-dompdf
composer require barryvdh/laravel-dompdf
agregar  el proveedor en la carpeta config/app.php
Barryvdh\DomPDF\ServiceProvider::class,
luego agregar la fachada en los alias
'PDF' => Barryvdh\DomPDF\Facade::class,

