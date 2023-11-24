# prueba
*Instructivo de uso para el repositorio*  

Una vez descargado el repositorio sigue los siguientes pasos para que puedas visualizar su funcionamiento:  

1.	Descomprime la carpeta que contiene el proyecto.  

2.	Abre en el editor de código de tu preferencia, la carpeta e inicia tu terminal con:  <br>
•	npm install (este comando instala los paquetes y dependencias necesarias utilizadas en el proyecto).  <br>
 Dentro de ellas están: express, express-generator, mysql, bcrypt, JWT, cookie-parser, dotenv y nodemon (para el desarrollo).  

3.	Crea en tu editor de código un archivo << .env >> .  
•	Como ayuda te explicamos un ejemplo sobre los datos que contendrá tu archivo   << .env >>:
DB_HOST=localhost  <br>
DB_DATABASE= (nombre de la base de datos)  <br>
DB_USER= root  <br>
DB_PASSWORD=  <br>
JWT_SECRET=secretJWT_token  <br> 

4.	Busca en la carpeta config el archivo de instalación de la base de datos.  


5.	Inicia el programa Xampp (el servidor de MySQL o el de tu preferencia).  


6.	Importa la base de datos a phpMyAdmin.  


7.	Inicia el proyecto con el siguiente comando:      

•	npm run start (Este comando se utiliza para iniciar el proyecto y gestionar los paquetes utilizados).  

8.	Para hacer las consultas desde la base de datos usa la extensión ThunderClient, POSTMAN o incluso las Vistas.  <br>

9. Para ello elige que permisos deseas tener para realizar cada operación o consulta desde la base de datos.
<br>

Si quieres hacer operaciones como usuario editor o administrador desde ThunderClient, realiza los siguientes pasos: <br>

1. Dirigete a ThunderClient, elige el metodo POST y copia la siguiente URL :  localhost:3000/usuario/login <br>

2. En la seccion Body copia el siguiente JSON: <br>

Si es para un Usuario Editor: <br>

{ <br>
  "cedula_usuario": 31975611,<br>
  "nombre_usuario": "Editor", <br>
  "clave_usuario": "54321",<br>
  "rol_usuario": "editor"<br>
}
<br>  

Si es para un Usuario Administrador:<br>

{ <br>
  "cedula_usuario": 30975611,  <br>
  "nombre_usuario": "Admin",  <br>
  "clave_usuario": "12345",  <br>
  "rol_usuario": "admin"  <br>
}

3. Una vez generado tu token, dirigete en Auth, y en Bearer almacena tu token. El se encargara de que sea posible realizar las operaciones que gustes. <br>

4. Cada que desees realizar una operacion recuerda mantener el token en Bearer (Preferiblemente al hacer este paso que sea en un New Request).<br>


Operaciones a las cuales tiene acceso el Usuario Editor: <br>

* Ingresar equipos participantes.

* Mostrar los equipos participantes.

* Ingresar patrocinantes.

* Mostrar los patrocinantes.

* Mostrar modalidades.

* Ingresar modalidad.

* Mostrar los equipos participantes inscritos en cada categoría.

* Mostrar categorías. 

* Mostrar Equipos y sus padrinos.   

* Mostrar Modalidades y sus categorías.

* Editar Usuario.

* Eliminar inscripción a una categoría.

* Editar equipo


Operaciones a las cuales tiene acceso el Usuario Administrador: <br>

* Eliminar equipo.  

* Eliminar categoría.

* Editar patrocinador. 

* Ingresar equipos participantes.

* Mostrar los equipos participantes.

* Ingresar patrocinantes.

* Mostrar los patrocinantes.

* Eliminar patrocinador. 

* Mostrar modalidades.

* Ingresar modalidad.

* Mostrar los equipos participantes inscritos en cada categoría.

* Mostrar categorías. 

* Mostrar padrinos.

* Ingresar categoría a cada modalidad.

* Mostrar Equipos y sus padrinos.

* Editar equipo participante.

* Editar categoría.

* Mostrar Modalidades y sus categorías. 


- URL para las vistas:

http://localhost:3000/home/login (Ingresar usuario)

http://localhost:3000/Modalidad/nuevaModalidad (Ingresar nueva Modalidad)

http://localhost:3000/equipo/verEquipo         (ver Equipos)



-URL para cada operación en ThunderClient:  


/// Método GET
1.	Mostrar patrocinantes  

•	GET => http://localhost:3000/patrocinador/   

2.	Mostrar Modalidades y sus categorías  

•	GET => http://localhost:3000/modalidad/2  

3.	Mostrar los equipos participantes  

•	GET => http://localhost:3000/equipo/  

4.	Mostrar modalidades  

•	GET => http://localhost:3000/modalidad/  

5.	Mostrar categorías  

•	GET => http://localhost:3000/categoria/  

6.	Mostrar los equipos participantes inscritos en cada categoría  

•	GET=> http://localhost:3000/categoria/participantes (Con el objeto)  

Ejemplo:
{  <br>
  "nombre_categoria": "Recolección de objetos"  <br> 
}  


•	GET=> http://localhost:3000/categoria/equipos/1 (Con la url)  

7.	Mostrar Equipos y sus padrinos  

•	GET=> http://localhost:3000/equipo/padrinos  


///	Método POST  


1.	Ingresar equipos participantes
•	POST => http://localhost:3000/equipo/
-Para este ejemplo puedes tomar el objeto e insertar que nuevos valores va a llevar cada propiedad.  


{  <br>
    "representante": "Miguel",  <br>
    "email": "M1key9090@gmail.com",  <br>
    "telefono": "0412-7544567",
    "nombre_de_equipo": "Robots de la suerte",
    "participantes": "Miguel,Orlando",
    "comentario": ""
  }
  

2.	Ingresar patrocinantes  

•	POST => http://localhost:3000/patrocinador/  

3.	Ingresar modalidad  

•	POST=> http://localhost:3000/modalidad/  

4.	Ingresar categoría a cada modalidad  

•	POST=> http://localhost:3000/categoria  

///	Método PUT  


1.	Editar patrocinador (Ejemplo)  

•	PUT=> http://localhost:3000/patrocinador/2 (el 2 representa el id de la entidad que se desea actualizar)  


-Para este ejemplo puedes tomar el objeto y modificar las propiedades que necesites actualizar.

{
   "nombre_comercial": "Uni",
    "persona_de_contacto": "Mari",
    "telefono": "0414-7542212",
    "idPatrocinio": 2,
    "comentario": "suerte a todos"
}  


2.	Editar equipo participante  

•	PUT=> http://localhost:3000/equipo/2  

3.	Editar categoría (PATCH y PUT)  

•	PATCH=> http://localhost:3000/categoria/3  


///	Método DELETE  


1.	Eliminar de la inscripción de un equipo participante alguna categoría inscrita  

•	DELETE=> http://localhost:3000/equipo/sin_categoria/3/2  

2.	Eliminar equipo  

•	DELETE=> http://localhost:3000/equipo/3  

3.	Eliminar categoría  

•	DELETE=> http://localhost:3000/categoria/3  

4.	Eliminar patrocinador  

•	DELETE=> http://localhost:3000/patrocinador/2


