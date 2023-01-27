Documentación de sistema de bienes raíces
Introducción
Este sistema está diseñado para brindar una plataforma completa para la compra y venta de bienes raíces. Incluye un sistema de autenticación seguro para asegurar la privacidad y seguridad de los usuarios.

Autenticación
Para garantizar la seguridad de la información de los usuarios, se ha implementado un sistema de autenticación mediante el uso de tokens JWT.

Rutas
POST /api/auth/register: permite al usuario registrarse en el sistema proporcionando su nombre de usuario, correo electrónico y contraseña.
POST /api/auth/login: permite al usuario iniciar sesión en el sistema proporcionando su nombre de usuario y contraseña.
POST /api/auth/logout: permite al usuario cerrar sesión en el sistema invalidando su token actual.
POST /api/auth/token/refresh: permite al usuario actualizar su token actual antes de que expire.
Inmuebles
Rutas
GET /api/properties: Devuelve una lista de todos los inmuebles disponibles en el sistema
GET /api/properties/:id: Devuelve la información detallada de un inmueble específico
POST /api/properties: Permite a un usuario autenticado crear un nuevo inmueble
PUT /api/properties/:id: Permite a un usuario autenticado editar un inmueble existente
DELETE /api/properties/:id: Permite a un usuario autenticado eliminar un inmueble existente
Reservas
Rutas
GET /api/bookings: Devuelve una lista de todas las reservas realizadas por un usuario autenticado
POST /api/bookings: Permite a un usuario autenticado realizar una reserva en un inmueble específico
DELETE /api/bookings/:id: Permite a un usuario autenticado cancelar una reserva existente
Usuarios
Rutas
GET /api/users/:id: Devuelve la información del perfil de un usuario específico
PUT /api/users/:id: Permite a un usuario autenticado editar su perfil
