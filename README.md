# API Usuarios Osticket

_Implementacion de un API para la creacion de usuarios para Osticket sin la necesidad de la confirmacion por correo por parte del usuario_


## Pre-requisitos 📋

_Antes de comenzar, asegúrate de cumplir con los siguientes requisitos:_

1. **Servidor Web**: Debes tener un servidor web que soporte PHP y MySQL. Se recomienda usar [Apache](https://httpd.apache.org/) o [Nginx](https://nginx.org/).
2. **PHP**: Asegúrate de tener PHP instalado. La versión recomendada es **PHP 7.2** o superior. Puedes verificar tu versión de PHP ejecutando el siguiente comando:
3. **Extensiones de PHP**: Las siguientes extensiones de PHP son necesarias:
   - mysqli
   - curl
   - mbstring
   - xml
   - json
4. **Base de Datos MySQL**: Necesitarás tener una instancia de MySQL configurada. Puedes usar MySQL o MariaDB. Asegúrate de crear una base de datos para osTicket.
5. **osTicket**: Descarga la última versión de osTicket desde el sitio oficial. Descomprime los archivos y colócalos en tu servidor web.
6. **Configuración del entorno**: Asegúrate de configurar el archivo de configuración de osTicket (config.php) con los datos correctos de la base de datos.
7. **Acceso a la Red**: Verifica que tu servidor tenga acceso a Internet, ya que podría necesitar descargar dependencias o comunicarse con otros servicios.

_Siguiendo estos pasos, deberías estar listo para comenzar con la implementación de la API de osTicket._

Puedes instalar osticket desde el siguiente [Link](https://osticket.com/download/).

Recomendable seguir la documentacion por parte de Osticket para la correcta configuracion e instalacion [Documentacion](https://docs.osticket.com/en/latest/Getting%20Started/Installation.html).

### Instalación 🔧
_**El repositorio puede ser clonado en tu entorno de desarrollo, descargado o simplemente puedes modificar el archivo upload\api\http.php y crear el archivo upload\include\api.users.php que son los 2 archivos necesarios para el funcionamiento de esta API**_

_Una vez tengas Osticket funcional y configurado sera necesario:_
1. Iniciar sesion como un agente Osticket.
2. Ir al panel de administracion o admin panel
3. Ir al apartado Manage>API
4. Creamos una nueva API key
5. Sera necesario que ingresemos la direccion IP donde se encuentra alojandose nuestra aplicacion, ademas daremos click en las casillas donde permitiremos a la API key generar JSON, XML e EMAIL
6. Sera necesario que guardemos esta API para despues usarla ya sea como un 'parametro' o como un 'header' para hacer llamados a nuestra API.

_Ahora para hacer un llamado a la API sera necesario que tengamos ya un entorno de desarrollo configurado para esto o podria ser utilizado una aplicacion para pruebas (por ejemplo PostMan)_
- Para hacer un llamado a la API sera necesario hacer un POST hacia la direccion: http://dominio-aplicacion/api/users.json\xml\email
  
1. Por ejemplo si alojas tu aplicacion utilizando XAMPP y quieres utilizar un formato json sera necesario utilizar una direccion asi: http://dominio-aplicacion/osticket/upload/api/users.json
2. Finalmente deberemos ingresar los datos necesarios para la creacion de usuarios, en este caso, en un formato json
```
   {
    "email": "prueba16@ejemplo.com",
    "full_name": "prueba16",
    "phone": "123456789X686",
    "timezone": "America/Los_Angeles",
    "password": "123456789",
    "confirm_password": "123456789"
}
```
_Nota: La X en telefono es para agregar la extension del telefono, en este caso 686 son la extension del telefono 123456789_
