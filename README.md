# UNIDAD-4-BASE-DE-DATOS-EJERCICIO-12
1. Entidades Principales y Tablas del Sistema
usuario

Almacena la información de los perfiles registrados en la plataforma.

Atributos: id_usuario (clave primaria), fecha_alta, nombre, apellido, correo, contrase a y biografia.

publicacion

Registra las fotografías o publicaciones multimedia compartidas por los usuarios.

Atributos: id_publicacion (clave primaria), url_publicacion, leyenda y id_usuario (clave foránea que vincula la publicación con su autor).

etiqueta

Administra los tópicos o etiquetas (hashtags) disponibles en la red social.

Atributos: id_etiqueta (clave primaria) y nombre.

2. Tablas de Interacción y Vínculos Sociales
comentario

Almacena las respuestas o textos que los usuarios dejan en las publicaciones.

Atributos: id_comentario (clave primaria), fecha, hora, texto, id_usuario (autor del comentario) e id_publicacion (publicación asociada).

reaccion

Gestiona las interacciones de tipo "Me gusta" o similares sobre las publicaciones.

Atributos: id_reaccion (clave primaria), tipo_reaccion e id_publicacion.

sigue

Tabla asociativa de carácter autorreferencial que modela la red de contactos, permitiendo registrar quién sigue a quién.

Atributos: Clave primaria compuesta por (id_usuario_seguidor, id_usuario_seguido), donde ambos actúan como claves foráneas hacia la tabla usuario.

3. Restricciones e Integridad Referencial (Foreign Keys)
El script configura las reglas estrictas de validación para mantener la consistencia relacional mediante las siguientes restricciones:

comentario_id_publicacion_fkey y comentario_id_usuario_fkey: Conectan los comentarios con la publicación y el usuario emisor.

publicacion_id_usuario_fkey: Garantiza que toda publicación esté respaldada por un usuario existente.

sigue_id_usuario_seguido_fkey y sigue_id_usuario_seguidor_fkey: Aseguran que las relaciones de seguimiento involucren únicamente a usuarios registrados en el sistema.

IMAGEN DE EJEMPLO DE UNA CONSULTA:
<img width="1415" height="366" alt="image" src="https://github.com/user-attachments/assets/2c2cffa7-b553-45d6-91fe-0a3846625ca1" />
