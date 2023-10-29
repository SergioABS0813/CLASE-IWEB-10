# CLASE-IWEB-10

## PROYECTO (USO DEL GIT)

1) Git Commit (guardar los cambios en mi repo local)
2) Git Pull (jalar cambios de repo remota con local) Aquí se combinarán entre mis cambios y los del grupo.
3) Git Push (pushear la combinación de mi repo local con repo remota).

## Verificación correcta de Copy-Paste de un proyecto (Daos, Beans, Servlets, Jsp) a otro proyecto nuevo

1) Verificar si todas las dependencias empleadas (MYSQL) están xml del nuevo.
2) Verificar los import de los Daos y Beans. (BEANS, DAOS, SERVLETS, JSP)
     (Si hay error entonces borrar el antiguo import y que se auto-importe de nuevo).
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/fd9e0145-7834-41cb-a1e8-8155886c10f6)

## Bootstrap 
Tenemos que copiar el primer link para usar bootstrap

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/a1bbf013-d55a-43a6-bb14-e971be34dcca)


## HTML (Crear Botón)

   < a href = "" >< /a > Para crear botón.

   Crear botón alineado en columna "td"
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/77161f07-3bd6-4018-8fa0-122ce3f579a7)

   Resultado:

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/95c9805d-5b06-47e1-853f-9552576ead05)

## HTML (Alinear botón o palabra con otra)
   Clearfix es para alinear en Bootstrap:
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/fc78fc91-4745-42e4-8346-a352afbbd15a)

   Clearfix con Big info: (Sin Big Info ya no aparece)
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/e3cb4d35-a8d5-4bde-b913-8fd3c01a03bf)

   Resultado:

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/ce9171cb-6fb2-41f0-896c-002953db33af)

   Alineado Correcto (HTML): float-start y float-end
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/252c7aaa-2f9f-4858-9a8d-a31be03c4619)


## Vínculo JSP-JSP JSP-SERVLET

Jsp - Jsp si es que no hay que mostrar algo de base de datos.

Si el Jsp necesita base de datos va por SERVLET.

## Funcionamiento Servlet con diferentes botones (En el mismo Servlet)

Sabemos que la vista por Default te presenta un listado, péro si queremos colocar un boton que te redirija a ese mismo servlet tenemos que hacerlo con un parámetro "?action=X".

Significa que se ha realizado una acción determinada en la vista. Este parámetro será enviado DESDE EL JSP AL SERVLET.
     
![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/1e2f9494-24c1-4e4b-a525-616ee6a31375)

RECORDAR: request.setAttribute y request.getAttribute es para (SERVLET --> VISTA) unidireccional

## USO DEL REQUEST.GET PARAMETER (Servlet reciba de la Vista)
Antes el Listado lo hacíamos por Default, ahora enviaremos un action "crear" una actividad cuando presione dicho botón. TODO DESDE EL JSP HASTA EL SERVLET.

El request.getRequestDispatcher REDIRECCIONA A UN JSP (VISTA)

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/b68d77a4-280f-4028-9ee5-f7355119e7c5)

Si ingreso defrente al servlet defrente:

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/d820ae58-8a20-4c29-b1a3-d9b50e96ba61)

Nos damos cuenta que el action es null, por eso creamos esta lógica para el estado principal de la vista, si queremos hacer acciones (entrar a diferentes href mediante botones), solo con la variable action enviamos al sevrlet y con el switch-case (imag de arriba) e implementeamos para la recepción del action en el servlet:

Definición: Si es null --> action = "lista". Si no es null --> action = request.getParameter...

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/11a4dd24-b729-43cb-8875-9d5c4aaacca6)

## Linkear Botones GET
Agregamos el request.getContextPath para que contenga el [proyecto] en el url, si no, nunca llegaría a la vista:

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/1f1f9191-1196-4acc-918c-c2d1dadec4e3)

Vemos el url del botón href y tiene la parte [proyecto]:

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/4635d27b-d484-44c4-9d2e-19902141774f)

## Envío de INPUTS con POST (Formularios)
En formularios se usa el método POST de HTTPS, lo que se manda en formularios, se manda CIFRADO.

INPUTS que se enviarán al servidor

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/6cb61a72-663d-4894-be8b-ad89b32bba01)

Emplearemos < form > < /form > para todos los inputs y obligatoriamente un botón de type = "submit". No nos preocupemos del botón regresar ya que como no es de tipo submit, es como si no estuviera.

Para enviar los inputs al servidor, necesitamos:

     -Método HTTP (get/post)
     -A dónde va
     -¿qué voy a mandar?
     -botón (submit) de envío 

Para este caso, el método es POST por ser formulario.

Van hacia el JobServlet (controlador de los jobs) y enviamos mediante "action".

Voy a mandar INPUTS pero para diferenciarlos necesitamos que tengan "name".

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/8a010ead-67d8-4dab-ab57-d5b36c7c03c9)

## Verificación Método Post en JobServlet

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/f61e1aa0-6fcc-4fc5-a2bf-e5c47b3d9f9f)

## Recepción de datos enviados (POST en Servlet)

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/b4996d2e-26cb-49a0-bd49-734e034bdaaa)

## Redireccionar a la página con los respectivos cambios

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/c8c621f6-ef0d-4d0c-ae3e-00270a62b5cc)

## PARA PRACTICAR (Query que se encarga de insertar datos) - Servlet

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/fdbd6e64-4e38-4ad1-bb5a-eb2c6e8279ea)

## PARA PRACTICAR: HACER EL BOTÓN DE EDITAR UN TRABAJO

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/3874c1ba-ce39-42b1-94ce-5767105d5b2d)

Primero hacemos el Dao en donde corresponda:

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/3320207c-3f22-46fe-8739-56089f2572aa)

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/8786a8dd-f8d0-4b47-b5f6-a2d621361d6a)

Luego de Crear la función del Dao, nos vamos al Servlet (ESTABLECEMOS COMUNICACIÓN MEDIANTE EL BEAN JOB) y desde el servlet enviamos el job que vamos a editar:

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/a16c62cb-6c6f-463b-946b-fd0b88e9169c)

Finalmente, en el jsp se colocan los parámetros de forms con value para que aparezcan con valores por defecto: con VALUES

![image](https://github.com/SergioABS0813/CLASE-IWEB-10/assets/134556600/3a43cebc-7ebd-4798-83d9-6188dd2208d9)









