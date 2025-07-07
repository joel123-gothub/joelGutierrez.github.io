<div align="center">
<table>
    <theader>
        <tr>
            <td style="width:25%;"><img src="https://github.com/rescobedoq/pw2/blob/main/epis.png?raw=true" alt="EPIS" style="width:80%; height:auto"/></td>
            <td>
                <span style="font-weight:bold;">UNIVERSIDAD NACIONAL DE SAN AGUSTIN</span><br />
                <span style="font-weight:bold;">FACULTAD DE INGENIERÍA DE PRODUCCIÓN Y SERVICIOS</span><br />
                <span style="font-weight:bold;">DEPARTAMENTO ACADÉMICO DE INGENIERÍA DE SISTEMAS E INFORMÁTICA</span><br />
                <span style="font-weight:bold;">ESCUELA PROFESIONAL DE INGENIERÍA DE SISTEMAS</span>
            </td>            
        </tr>
    </theader>
    <tbody>
        <tr>
        <td colspan="2"><span style="font-weight:bold;">Proyecto web</span>: Desarrollo de una aplicación web para adopción de Mascotas</td>
        </tr>
        <tr>
        <td colspan="2"><span style="font-weight:bold;">Fecha</span>:  2022/08/23</td>
        </tr>
    </tbody>
</table>
</div>

<div align="center">
<span style="font-weight:bold;">PROYECTO WEB</span><br />
</div>


<table>
<theader>
<tr><th>INFORMACIÓN BÁSICA</th></tr>
</theader>
<tbody>
    <tr>
        <td>ASIGNATURA:</td><td>Programación Web 2</td>
    </tr>
    <tr>
        <td>SEMESTRE:</td><td>III</td>
    </tr>
    <tr>
        <td>FECHA INICIO:</td><td>30-May-2022</td><td>FECHA FIN:</td>
        <td>31-Agosto-2022</td><td>DURACIÓN:</td><td>04 horas</td>
    </tr>
    <tr>
        <td colspan="3">DOCENTES:
        <ul>
        <li>Richart Smith Escobedo Quispe - rescobedoq@unsa.edu.pe</li>
        </ul>
        </td>
    </<tr>
</tdbody>
</table>

#   WebApp con Django

[![License][license]][license-file]
[![Downloads][downloads]][releases]
[![Last Commit][last-commit]][releases]

[![Debian][Debian]][debian-site]
[![Git][Git]][git-site]
[![GitHub][GitHub]][github-site]
[![Vim][Vim]][vim-site]
[![Java][Java]][java-site]

##  Tipo de Sistema
    Se trata de una aplicación web construida con el framework Django 4, que permita la adopción de mascotas.

##  Requisitos del sistema
    El sistema debe satisfacer los siguientes requisitos funcionales y no funcionales:

    RQ01 : Diseño de operaciones CRUD (usuarios y mascotas)
    RQ02 : Creación de login para usuarios
    RQ03 : Creación de galerías de mascotas por adoptar
    RQ04 : Creación de formularios para registro usuarios y mascotas
    RQ05 : Creación de Base de Datos para el sistema
    RQ06 :  Generación de documentación en formato pdf con datos de adopción  realizada
    RQ07 : Envío de email con datos de adopción al cliente
    RQ08 : Manejo de solicitudes, se marcará como no disponible en caso una mascota haya sido ya adoptada
    RQ09 :  Usabilidad, la navegabilidad y uso debe ser intuitivo para el usuario.
    RQ10 : Pedir DNI para la verificación de ser mayor de edad

##  Diagrama de Arquitectura
    El siguiente diagrama muestra cómo y dónde fluyen, se procesan y se utilizan los datos.
   ![image](https://user-images.githubusercontent.com/64146055/185713083-b754547f-ff10-4701-a37c-624ae9cd8742.png)

##  Modelo de datos
    El modelo de datos esta conformado por las siguientes entidades.

    -   Cliente : En esta entidad se almacena la información de los cliente o usuario que quiere adoptar. Ejemplo: Nombre, Apellido, Edad, Telefono, etc.
    -   Mascota : En esta entidad se almacena los datos de las mascotas que estan disponibles en galerias para futuros adopciones. Ejemplo: nombre, especie, raza, edad, etc.
    -   Adopción: En esta entidad se almacena la información del proceso en sí, de la adopción. Ejemplo: ID Cliente, ID Mascota, Fecha, etc.
    -   Aves: Esta entidad hereda información de la entidad padre Mascota, pero tiene sus propios datos.
    -   Perros: Esta entidad hereda información de la entidad padre Mascota, pero tiene sus propios datos.
    -   Gatos: Esta entidad hereda información de la entidad padre Mascota, pero tiene sus propios datos.
   ![image](https://user-images.githubusercontent.com/64146055/185712556-79d5cf9a-839c-4a42-8b9d-2fa6919433f1.png)


##  Diccionario de datos

    Este diccionario muestra las diferentes entidades y descripción de sus campos.

![image](https://user-images.githubusercontent.com/64146055/185759662-018e449f-7399-4a34-b7ca-faad4fee043e.png)
![image](https://user-images.githubusercontent.com/64146055/185759673-ad02fc00-5e1e-46eb-8eb6-f8c0189bc89c.png)

##  Diagrama Entidad-Relación
    Este diagrama es un tipo de diagrama de flujo que ilustra cómo las "entidades", como cliente, objetos o conceptos, se relacionan entre sí dentro de un sistema.
    Esta realizado para una BD MySQL.
  
  ![image](https://user-images.githubusercontent.com/64146055/185716793-19021bff-bed9-44f5-b910-b5e0689b2556.png)

##  Administración con Django
    Se muestran los pasos realizados para crear el Proyecto, la aplicación, creacion de modelos, migraciones y habilitación del panel de administración en Django.
    
   Entonces: 
   1. Primero es necesario la instalación de dependencias como: Python, Django y un entorno virtual.
        * Python
            ![image](https://user-images.githubusercontent.com/64146055/185759923-f1a4716d-c327-40bb-85a3-eb545d101e6c.png)

        * Django
            ![image](https://user-images.githubusercontent.com/64146055/185759936-23e3f11b-c243-47ed-bb57-d30c6156c80c.png)

        * VirtualEnv, mediante los comandos: 
            * pip install virtualenv : Instalación
            * virtualenv -p python project-prueba : Creación un entorno virtual  
            * source project-prueba/bin/activate : Para la activación del entorno virtual  (para desactivarlo:    deactivate)
   
   2. Luego, crearemos nuestro primer proyecto:
        - Mediante los comando (de manera consecutiva): 
            * mkdir src; cd src
            * source ../bin/activate
            * django-admin startproject ProyectoPWeb02
            * Lo que el comando anterior, creo:
                ![image](https://user-images.githubusercontent.com/64146055/185763453-f86ef0e2-6d07-4cf0-8469-7df8477c34bf.png)
   
   3. Luego, corremos por primera vez nuestro servidor, mediante el comando:
       * python manage.py runserver
       * ![image](https://user-images.githubusercontent.com/64146055/185761875-24cdfb5c-273c-411f-aa94-f2f3f990eba7.png)
       * ![image](https://user-images.githubusercontent.com/64146055/185797948-10207323-d045-41ed-b8d9-f7c3d9ad56ed.png)
       
   4. Configurar una base de datos
       * Hay una gran variedad de opciones de bases de datos para almacenar los datos de tu sitio. Utilizaremos la que viene por defecto, sqlite3.
       * ProyectPWeb02/settings.py
       * ![image](https://user-images.githubusercontent.com/64146055/185798096-d343ed0b-86c7-46d3-bdad-286f56b86ee3.png)
       
   5. Luego creamos nuestra primera aplicacion llamada Adopciones:
        * python manage.py startapp Adopciones

   6. De manera que se crea lo siguiente:
        ![image](https://user-images.githubusercontent.com/64146055/185763256-4ee5c863-8f2e-417e-863d-018a82e2cb06.png)
   
   7. Creación de modelo (models.py):
   
        * Creamos nuestro primer modelo 'usuario':
            ![image](https://user-images.githubusercontent.com/64146055/185762042-5aa20a2d-a7f2-464b-8063-7753d178860f.png)

        * Registramos el modelo en admin.py
            ![image](https://user-images.githubusercontent.com/64146055/185762069-e58ddcbc-0163-4a29-af30-1568bf998c68.png)

        * Y lo registramos en INSTALLED_APPS de settings.py del proyecto:
            ![image](https://user-images.githubusercontent.com/64146055/185762113-535d2ea9-c157-4423-a1f5-47fc0fc03858.png)
        
        * Una vez realizado esos cambios, actualizamos los cambios hechos en el framework, mediante los comandos:
            - python manage.py makemigrations
                ![image](https://user-images.githubusercontent.com/64146055/185763387-61772493-8894-47f8-8151-25f8f45a4a4f.png)

            - python manage.py migrate
                ![image](https://user-images.githubusercontent.com/64146055/185763407-aad87117-6c0e-4d6c-af67-3641216ad764.png)
   
   8. Panel de Administración de Django:
        * Para habilitar esto, debemos crear un superusurio:
            + python manage.py createsuperuser  (Crea un nuevo usuario con su contraseña con permisos de administrador)
            ![image](https://user-images.githubusercontent.com/64146055/185762560-da95d854-38de-40e4-a7de-a66f8104843e.png)
        
        * Luego, agregar la ruta del panel al proyecto  (ProyectoPWeb02\urls.py)
            ![image](https://user-images.githubusercontent.com/64146055/185763017-70638cf6-d963-4aba-b311-3d6016ee1d6c.png)  
        
        * Luego corremos el servidor:
            + python manage.py runserver
        
        * Y nos dirigimos a la dirección y agregamos nuestros credenciales:  http://127.0.0.1:8000/admin/
            ![image](https://user-images.githubusercontent.com/64146055/185763082-31f76595-c5b2-4fa0-803f-ca4020d9d555.png)
        
        * Una vez iniciado sesión, accedemos al sitio administrativo:
            ![image](https://user-images.githubusercontent.com/64146055/185763177-d2a548d4-9e27-4f5b-bb8b-b1eb04f28141.png)
            ![image](https://user-images.githubusercontent.com/64146055/185763206-9313c235-2a97-42de-ae0b-e00c745a613f.png)

##  Plantillas Bootstrap
    Se seleccionó la siguiente plantilla para el usuario final (No administrador).
    
   * Demo online: https://plantillashtmlgratis.com/wp-content/themes/helium-child/vista_previa/page263/dpot/ 
   * URL: https://plantillashtmlgratis.com/todas-las-plantillas/plantilla/plantillas-html-css-gratis-para-descargar-dpot/ 

    Se muestran las actividades realizadas para adecuación de plantillas, vistas, formularios en Django.
  
   Entonces:
   
   1. Primero descargamos un template gratis en nuestro caso usamos este template:
        * https://plantillashtmlgratis.com/todas-las-plantillas/plantilla/plantillas-html-css-gratis-para-descargar-dpot/
        * Así, creamos nuestra otra aplicacion llamada 'inicio', mediante el siguiente comando:
            - python manage.py startapp inicio
        * Luego de crear un app para el inicio de la aplicacion se creo una carpeta template donde se ubicara el template que descargamos solo el html, para que     reconosca el template se cambio en la aplicaion principal la ubicacion de los templates.
        * ![pw](https://user-images.githubusercontent.com/83080715/177056999-912f3b04-e401-495b-9f62-73d612111bac.png)

   2. Para el css tambien se creo otra carpeta, llamada 'static', donde estara los scripts de la hoja de estilos, css y bootstrap que tambien son del mismo template descargado:
        * ![pw2](https://user-images.githubusercontent.com/83080715/177057019-1453dc63-ee34-436c-80e3-f86972c3824d.png)

   3. Para que funcione el template se creo una vista dentro de la app adopciones que sera el inicio se modifico en views.py un def para la vista
        * ![pw3](https://user-images.githubusercontent.com/83080715/177057892-05913db8-6d22-4e14-aba8-58dff3b4ecc7.png)

   4. Tambien se canbio en urls.py, donde se agregó la ruta, de la pagina principal principal para que muestre la página:
        * ![pw4](https://user-images.githubusercontent.com/83080715/177057942-3f5a31df-643b-42f9-a091-99d23feee955.png)
   
   5. Luego, en 'ProjectPWeb02/setting.py', configuramos y definimos STATIC_URL, entre otros:
        * ![image](https://user-images.githubusercontent.com/64146055/185807137-f12ec079-41fd-4344-8876-1a590b229002.png)
   
   6. Otro cambio más, es en el mismo template (el '{% load static %}') y definir la rutade donde esta dicha carpeta 'static', para que cargue los css, js, bootstrap del template descargado.
        * ![pw5](https://user-images.githubusercontent.com/83080715/177057997-b33bceb5-4115-42b9-9568-bd44a26b52b3.png)
   
   7. Finalmente, ejecutamos el servidor en la siguiente dirección:
        * http://127.0.0.1:8000/
        * Y notamos la plantilla ejecutada localmente.
        * ![image](https://user-images.githubusercontent.com/64146055/185807439-b462bc8c-2c2c-4e23-b135-e6ce70b2306c.png)

##  CRUD - Core Business - Clientes finales
    El núcleo de negocio del sistema de adopciones de mascotas tiene valor de aceptación para los cliente finales radica en realizar el proceso de adopción propiamente, que empieza desde que:
    1. El cliente ingresa a la página principal.
    2. El cliente se redirige al botón de adoptar, donde se mostrará la galeria de mascotas.
    3. El cliente da clic en una determinada mascota.
    4. El cliente debe registrarse previamente para adoptar.
    5. Luego, se le enviará por correo los datos e información de la adopción.

    Todas y cada una de estas pantallas debe funcionar en la plantilla bootstrap.
    A continuación se muestran las actividades realizadas para su construcción:
    
   -En nuestro proyecto el CRUD es diferente por que el Create y Update es directo en la base de datos para evitar fraudes o estafas que otras personas puedan subir
    alguna mascota o editar una mascota
    
   -Una ves explicado eso para el CRUD tenemos que ir a las vistas de nuestra app en nuestro caso "mascotas" y en vista nosotros importaremos las vistas ya echos
    de django:
    
   ![views](https://user-images.githubusercontent.com/83080715/185993245-ed4eff33-7115-4442-a35e-61faf8070419.png)
    
   -Despues de importarlas tendremos que llamarlas con si fueran clases:
    
   ![image](https://user-images.githubusercontent.com/83080715/185993323-47def373-451b-4144-ac3b-db38fc64637e.png)
    
   -En nuestro caso como dije antes evitamos usar el Create y Update
    
   -El delete nosotros lo usamos como si fuera una opcion de "adoptar" ya que al momento de adoptar la mascota se va de la base de datos
    
   -Despues de crear las vistas tenemos que crear los templates como usamos las vistas de django los templates tienen nombres especificos que seria
    <nombre_de_la_app>_(accion).html como se puede ver aqui:
    
   ![image](https://user-images.githubusercontent.com/83080715/185994511-b242a7d7-1bf2-4943-8d1c-5634e4d7ad1d.png)
    
   -En la lista de mascotas usamos un for para que itere en las mascotas por su id
    
   ![image](https://user-images.githubusercontent.com/83080715/185994673-77f54a81-eca5-4a21-b45e-703b696789f0.png)
    
   -En el detalle de una mascota en especifico y la eliminacion usamos el get_absolute_url para que nos de la id usando reverse en el modelo
    
   ![image](https://user-images.githubusercontent.com/83080715/185994963-07113fb9-ba13-477c-8ff7-cb10418fbbde.png)
    
   -En el detalle usamos esta estructura:
    
   ![image](https://user-images.githubusercontent.com/83080715/185995074-466203c2-6345-4e56-80b2-08039c1b9545.png)
    
   -Y en el de "adopcion" que en realidad es elminacion usamos este que es similar al de detalle:
    
   ![image](https://user-images.githubusercontent.com/83080715/185995158-a40f4413-2c98-4369-98f2-be3759c07eb6.png)
    
   -Por ultimo añadimos los urls:
   
   ![image](https://user-images.githubusercontent.com/83080715/185996413-b5b42115-7a8d-431d-833c-1bb217c5393b.png)


##  Servicios mediante una API RESTful
    Se ha creado una aplicación que pondra a disposición cierta información para ser consumida por otros clientes HTTP.
    1. GET : Con el método get se devolverá la lista de usuarios y mascotas establecidos para que el admin sobre todo vea esta información en cualquier otro medio.
    2. POST : Con este método se enviara el código del usuario o mascota y se devolvera sus inscripciones.
    
    Ejemplo: Prueba en Página web, admin, lista usuarios, listar mascotas.
    Se especifican los pasos para crear el servicio RestFul
    
   - Para ello trabajaremos con nuestra app Adopciones, especificamente con los usuario y/o clientes que quieren adoptan.
   - Donde los datos de un adoptante son los siguientes (models.py):
     ![image](https://user-images.githubusercontent.com/64146055/183317250-5e35cfca-f4c8-4b12-8265-22aa70ba6df7.png)
     
   - Entonces, para crear el servicio REST, instalamos todos los siguientes módulos de Django:
        --> pip install djangorestframework
        --> pip install markdown       # Markdown support for the browsable API.
        --> pip install django-filter  # Filtering support 
   - Verificamos,
     ![image](https://user-images.githubusercontent.com/64146055/183317521-fe05a8e7-6606-4a0c-ab87-80899bf61c54.png)
     
   - Activamos la app rest_framework en el settings.py.
     ![image](https://user-images.githubusercontent.com/64146055/183317631-8456fccb-bef9-4393-b70d-842d8216d54f.png)
     
   - Ahora vamos a configurar un serializador (serializers.py), éste definirá el contenido de los usuarios tal como las devolverá la API:
   - Adopciones/serializers.py
     ![image](https://user-images.githubusercontent.com/64146055/183317897-b272d63f-1156-4acb-9e7c-6b4f9bb2512f.png)
   - Como vemos en la figura anterior, podemos agregar cada campo, uno por uno, o podemos añadir '__all__' para que se agreguen todos los campos
   
   - Luego, Vamos por la parte del viewset y las urls
   - Para ello, ya teniendo el modelo y el serializador, ya sólo nos falta programar el viewset de DRF:
   - api/views.py
     ![image](https://user-images.githubusercontent.com/64146055/183318083-2c66552f-56ea-408e-b71a-1a59dc25e9b8.png)
   - Como vemos en la figura anterior, importamos viewsets de rest_framework, el serializer, el modelo, y luego definimos la clase UsuarioViewSet

   - Y ahora añadimos a las urls la ruta de la viewset en la API: (Adopciones/urls.py)
     ![image](https://user-images.githubusercontent.com/64146055/183318291-fc415e7a-443d-43e6-becb-bbe719ccdbc1.png)

   - Lamentablemente por defecto las viewsets tienen permisos públicos, así que cualquiera podría manejar las Usuarios que quieren adoptar. Para solucionarlo simplemente añadiremos un permiso por defecto en el settings.py: (ProyectoPweb02/settings.py)
     ![image](https://user-images.githubusercontent.com/64146055/183318468-bbba6953-7d0d-48da-a89e-a5e348474ab8.png) 
   
   - Ahora, corremos el servido local:
   - python manage.py runserver
     ![image](https://user-images.githubusercontent.com/64146055/183318576-d0c85b29-3704-467d-9175-3784d4ec5bcf.png)
   
   - Además, podemos ver una lista en formato JSON de los diferentes usuarios que desean adoptar, cada uno con sus respectivos datos:
     ![image](https://user-images.githubusercontent.com/64146055/183318706-85c2bf23-a7c2-42d1-9c76-91adf25668c9.png)
     ![image](https://user-images.githubusercontent.com/64146055/183319598-a6832638-3e56-48ac-8433-ddc5ac912895.png)

   - Ahora mostraremos los resultados mediante un cliente REST, en este caso la aplicación descargable POSTMAN:
   - Para ello, vamos a su link oficial de descarga para windows: https://www.postman.com/downloads/ 
     ![image](https://user-images.githubusercontent.com/64146055/183318894-4e4888ba-e7bf-41b7-b6d3-4078a3521916.png)

   - Luego, ejecutamos Postman, y nos logueamos con una cuenta de la misma:
     ![image](https://user-images.githubusercontent.com/64146055/183318970-0fa5ee23-8531-45ae-bd82-ec2a855cd5b6.png)

   - Una vez iniciado sesión
    - realizamos y escogemos nuestra primera petición HTTP, en este caso GET.
    - Definimos la URL: http://127.0.0.1:8000/adopciones/Usuarios/6, donde queremos obtener los datos del usuario con id=6
    - Luego, damos en el botón 'Send'.
      ![image](https://user-images.githubusercontent.com/64146055/183319185-d4febdf1-1203-4769-9859-22bc9cc338e5.png)
   - Como podemos notar, nos devuelve un mensaje de 200 OK, que significa que la petición fue exitosa.  
   - También, notamos de salida de la petición que es en formato JSON con el respectivo usuario de id=6       
 
 
   - Asi tambien, probaremos con otro cliente REST, en este caso la aplicación INSOMNIA.
   - realizamos y escogemos nuestra petición HTTP, en este caso GET.
        - ![image](https://user-images.githubusercontent.com/91225726/184166745-00f4f57d-45b9-44b4-94e9-fff9134598d4.png)

        - ![image](https://user-images.githubusercontent.com/91225726/184167494-776ec118-a97d-488c-b542-42f4e5c5b22a.png)
      
   -Ahora vemos que se puede editar en la misma apis rest que es insomnia

- crear cliente REST que consuma el servicio implementado
        - ![image](https://user-images.githubusercontent.com/91225726/186206354-99cf3545-e892-46d5-8121-bbf9e47ae8a0.png)
       creamos el crud mediante ng new crud, generamos el server ng serve y ng generate service api
        
        
      
     - ![image](https://user-images.githubusercontent.com/91225726/186206628-e19df425-bbd6-4612-9708-11f8547b0cc6.png)
     - ![image](https://user-images.githubusercontent.com/91225726/186206846-c502d23d-bbc4-4564-afc5-e0dcc0f5e8b2.png)
     - ![image](https://user-images.githubusercontent.com/91225726/186207207-42108041-f899-4abd-a7a0-2667fccf358f.png)
     - ![image](https://user-images.githubusercontent.com/91225726/186207352-1dfc7ef4-bc03-44bb-905d-ff8d1ddf57a5.png)
     - ![image](https://user-images.githubusercontent.com/91225726/186207407-5e4bdb2d-43ff-4ca8-89a8-5b9aecdbcf45.png)
     - ![image](https://user-images.githubusercontent.com/91225726/186208204-c4abc1b2-5572-47b1-aaf8-3df662ba712a.png)







- Mostrar resultados:
    - Cliente HTML AJAX o Cliente Form Django o Cliente móvil
    - ![image](https://user-images.githubusercontent.com/91225726/186208252-e0a9c883-37c1-459a-8e83-a7c53a0fffc4.png)


##  Operaciones asíncronas AJAX
    Se propone el uso de AJAX para realizar la asignación de carga académica a los docentes que estan registrados. Esta operación la realizará el usuario operador encargado por el DAISI.
    Se muestran los pasos necesarios a realizar.
    ....

##  Investigación: Email, Upload.
    - Email: Se utilizará la funcionalidad del uso de envío de correos electrónicos cuando el proceso de adopciones culmine y al cliente le llegue la información del la adopción realizada.
    - Upload: Se utilizará esta funcionalidad para que al momento de crear una mascota, especificamente en la subida de la foto(tipo imagen).
    Se muestran los pasos realizados para su funcionamiento correcto.
    
   - Lo primero que debemos hacer es configurar nuestro proyecto; para ellos modificaremos el archivo settings.py agregando 5 nuevas constantes.
        ![image](https://user-images.githubusercontent.com/64146055/186201552-d56321cb-fc16-4aec-9dab-edc890c05937.png)
   - Para ello necesitamos las credenciales: usuario y password  
   
   - Bien, una vez tengamos las configuraciones el siguiente paso es definir una función la cuales nos permita enviar los correos.

   - Para la creacion del envio de email nosotros lo hacemos cuando adoptan a una mascota mandandole un correo para eso tenemos que crear en las vistas de la app unas funciones
   
   ![image](https://user-images.githubusercontent.com/83080715/186186965-ab0baed5-8640-4464-911c-ed6ba39d86e5.png)
   
   - Estas funciones seran con metodo Post tendremos que hacer varias importaciones del modelo de usuarios y otras funciones de django para el correo.
   - Asi, debemos importar la clase EmailMultiAlternatives y el módulo settings.

   - Lo primero que debemos hacer es generar nuestro mensaje, para ello nos apoyamos de EmailMultiAlternatives. 
   - Definimos el subject, el remitente y finalmente los destinatarios(Esto último mediante una lista).
   - El siguiente paso es agregar un cuerpo al mensaje. Para ello me apoyo de un template renderizado.
   - Y finalmente, con el método send enviamos el correo.
   
   - Luego, el llamado de la función se realiza dentro de la función enviar, en la linea send_email(mail,obj).
   
   ![image](https://user-images.githubusercontent.com/83080715/186188151-d54ad382-5c1f-4acd-a5f9-0cea8fc27673.png)
   
   - Despues tenemos que crear templates para estos aqui se mostrara el template cuando se envia el correo
   
   ![image](https://user-images.githubusercontent.com/83080715/186188436-40448840-8457-409c-8ffc-c41bb2134c78.png)
   
   - Y este template es para enviarnos un correo cuando se adopta a una mascota
   
   ![image](https://user-images.githubusercontent.com/83080715/186188682-806f1308-c9f1-46f5-9ae9-a06758f57d4c.png)
   
   - Estos templates de correo se usan en el template de mascotas cuando se va a adoptar
   
   - Para la subida de archivos .jpg o .png se realizara en la función createMascotas.views
   ![image](https://user-images.githubusercontent.com/64146055/186209395-b81f2884-562b-497f-bd0b-14462e04aaf5.png)
   - Mediante el siguiente form
   ![image](https://user-images.githubusercontent.com/64146055/186209589-f7496780-a48b-4b02-9753-76ebb0a6a01e.png)
   - De manera que la plantilla quedaria de la siguiente manera (MascotaForm.html)
   ![image](https://user-images.githubusercontent.com/64146055/186209723-02108a6e-7888-4bb0-adf9-c2afe01715f4.png)
   - Donde se cargar una imagen de una foto al crear una mascota. 
   
Github del proyecto: https://github.com/kevinPedroYare/Proyecto_LabPweb2 

URL en Heroku:

* URL Playlist YouTube: https://www.youtube.com/playlist?list=PL_CXzPeLfGUC5EIUo6hUbSQ0Z3hQ7SvLz

Producción de un PlayList en Youtube explicando cada una de los requerimientos.

* Video 01 - Sistema - Requisitos: https://www.youtube.com/watch?v=5gh60o97p-A&list=PL_CXzPeLfGUC5EIUo6hUbSQ0Z3hQ7SvLz&index=1
* Video 02 - Modelo de datos - DD - DER - DARQ: https://www.youtube.com/watch?v=zJ8BHdDnYmA&list=PL_CXzPeLfGUC5EIUo6hUbSQ0Z3hQ7SvLz&index=2
* Video 03 - Administración con Django: https://www.youtube.com/watch?v=2FFLnvbLq88&list=PL_CXzPeLfGUC5EIUo6hUbSQ0Z3hQ7SvLz&index=3
* Video 04 - Plantillas Bootstrap: https://www.youtube.com/watch?v=05zCiMd857Q&list=PL_CXzPeLfGUC5EIUo6hUbSQ0Z3hQ7SvLz&index=4
* Video 05 - CRUD: https://www.youtube.com/watch?v=t9ZPk8qwzyc&list=PL_CXzPeLfGUC5EIUo6hUbSQ0Z3hQ7SvLz&index=5&t=1s 
* Video 06 - Servicios REST: https://www.youtube.com/watch?v=kn8Y2oYJVL8&list=PL_CXzPeLfGUC5EIUo6hUbSQ0Z3hQ7SvLz&index=8
* Video 07 - Operaciones AJAX:
* Video 08 - Email y Upload al server: https://www.youtube.com/watch?v=Uz4lOB9IL9I&list=PL_CXzPeLfGUC5EIUo6hUbSQ0Z3hQ7SvLz&index=7

## REFERENCIAS
-   https://www.django-rest-framework.org/
-   https://docs.hektorprofe.net/academia/django/api-rest-framework/ 
-   https://www.postman.com/downloads/
-   https://insomnia.rest/download 
-   https://docs.djangoproject.com/en/4.1/howto/static-files/
-   https://plantillashtmlgratis.com/todas-las-plantillas/plantilla/plantillas-html-css-gratis-para-descargar-dpot/
-   https://docs.google.com/presentation/d/1_6t7ixfyL0RXYz_Osvo7Lf-f-JXvWMnw/edit#slide=id.g13da2fd672b_0_6
-   https://codigofacilito.com/articulos/envio-correos-django

#

[license]: https://img.shields.io/github/license/rescobedoq/pw2?label=rescobedoq
[license-file]: https://github.com/rescobedoq/pw2/blob/main/LICENSE

[downloads]: https://img.shields.io/github/downloads/rescobedoq/pw2/total?label=Downloads
[releases]: https://github.com/rescobedoq/pw2/releases/

[last-commit]: https://img.shields.io/github/last-commit/rescobedoq/pw2?label=Last%20Commit

[Debian]: https://img.shields.io/badge/Debian-D70A53?style=for-the-badge&logo=debian&logoColor=white
[debian-site]: https://www.debian.org/index.es.html

[Git]: https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white
[git-site]: https://git-scm.com/

[GitHub]: https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white
[github-site]: https://github.com/

[Vim]: https://img.shields.io/badge/VIM-%2311AB00.svg?style=for-the-badge&logo=vim&logoColor=white
[vim-site]: https://www.vim.org/

[Java]: https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=java&logoColor=white
[java-site]: https://docs.oracle.com/javase/tutorial/


[![Debian][Debian]][debian-site]
[![Git][Git]][git-site]
[![GitHub][GitHub]][github-site]
[![Vim][Vim]][vim-site]
[![Java][Java]][java-site]


[![License][license]][license-file]
[![Downloads][downloads]][releases]
[![Last Commit][last-commit]][releases]
