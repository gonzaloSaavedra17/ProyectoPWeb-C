# ProyectoPWeb-C
Proyecto final del curso de Programación Web del semestre 2024B
Descripción de la Aplicación

Esta aplicación web gestiona complejos deportivos, eventos y pagos realizados por los usuarios. Los administradores pueden visualizar, actualizar y gestionar datos relacionados con los pagos y reservas, mientras que los usuarios tienen acceso a consultar sus pagos y realizar registros. La aplicación utiliza tecnologías como Perl para la capa de servidor, MySQL para la base de datos y CGI para la interacción web.

Integrantes

1. Barra Quispe, Fernando Jonathan
2. Saavedra Inga, Gonzalo de Alesandro
3. Yanqui Toribio, Hazzbel Sinai (pertenece a otro grupo de teoria)

Descripción de Pantallas


1. Pantalla de Inicio

- Usuarios: Presenta información general sobre los complejos deportivos disponibles y enlaces para registro e inicio de sesión.
- Administradores: Redirige a una vista de gestión luego del inicio de sesión.


2. Registro de Usuarios

- Permite a los usuarios registrarse proporcionando nombre, apellido, correo electrónico y contraseña.


3. Inicio de Sesión

- Los usuarios y administradores pueden acceder a sus respectivas vistas tras autenticarse correctamente.


4. Gestión de Complejos Deportivos (Admin)

- Lista todos los complejos deportivos registrados con opciones para añadir, editar o eliminar.


5. Gestión de Pagos (Admin)

- Muestra una tabla con todos los pagos realizados, permitiendo actualizar su estado.


6. Historial de Pagos (Usuario)

- Proporciona al usuario un historial de sus pagos realizados, detallando el método de pago, fecha y estado.


7. Eventos Deportivos

- Visualiza los eventos deportivos disponibles con filtros por tipo y fecha.

Diagrama de la Base de Datos

|        users               |

-> user_id                
-> nombre                     
-> apellido                   
-> email                      
-> password                   

|   complejos_deportivos     |
-> id                    
-> nombre                     
-> tipo                       
-> capacidad                  

|          pagos             |
-> pago_id                
-> pedido_id              
-> cantidad                   
-> metodo_pago                
-> estado                     
-> fecha                      

|         pedidos            |
-> pedido_id             
-> descripcion                
-> user_id                

|          eventos           |

-> id (PK)                    
-> tipo_evento                
-> fecha_evento               


Explicación del Uso de AJAX para CRUD

El uso de AJAX mejora la interactividad al actualizar solo partes específicas de la página sin necesidad de recargarla completamente. Ejemplo:

- Visualizar Eventos:

  - Enviar una solicitud AJAX desde el cliente para filtrar eventos por tipo y fecha.
  - El servidor responde con datos en formato JSON, que se procesan para actualizar la interfaz de usuario dinámicamente.

- Actualizar Estado de Pagos:

  - Un formulario envía la solicitud AJAX con el `pago_id` y el nuevo `estado` al servidor.
  - El servidor ejecuta la actualización en la base de datos y devuelve un mensaje de confirmación para actualizar la tabla.

Explicación del Uso de Variables de Sesión

Las variables de sesión son importantes para mantener el estado del usuario en la aplicación. En este caso, se utilizan para:

1. Autenticación: Basicamente, guardar el `user_id` y el rol (usuario/admin) tras el inicio de sesión.
2. Personalización: Mostrar contenido específico según el rol del usuario, util debido a que tenemos 2 roles importantes.
3. Seguridad: Asegurar que las acciones sensibles solo sean realizadas por usuarios autorizados.

Conclusiones

- La aplicación cumple con los objetivos de gestión y visualización de datos, proporcionando interfaces funcionales para usuarios y administradores.
- El uso de Perl y CGI son buenas herramientas para aplicaciones web simples.

Recomendaciones
