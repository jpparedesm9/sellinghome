Sistema de Bienes Raíces

========================

Introducción

------------

Este sistema contempla todo lo necesario para una página de compra y venta de bienes raíces. Incluye una API de autenticación que permite a los usuarios registrarse y acceder a las funcionalidades de la plataforma.

Base de datos

-------------

Para almacenar la información de los usuarios y los bienes raíces, se utiliza una base de datos PostgreSQL.

sqlCopy code

`// Código para la creación de la tabla de usuarios

CREATE TABLE users (

    id SERIAL PRIMARY KEY,

    email VARCHAR(255) NOT NULL,

    password VARCHAR(255) NOT NULL,

    role VARCHAR(255) NOT NULL

);`

sqlCopy code

`// Código para la creación de la tabla de propiedades

CREATE TABLE properties (

    id SERIAL PRIMARY KEY,

    title VARCHAR(255) NOT NULL,

    description TEXT NOT NULL,

    price INTEGER NOT NULL,

    user_id INTEGER NOT NULL REFERENCES users(id)

);`

API de autenticación

--------------------

La API de autenticación utiliza el middleware de autenticación Passport para validar las credenciales de los usuarios.

javascriptCopy code

`// Código para la ruta de registro

router.post('/register', (req, res) => {

    User.register(new User({ email: req.body.email, role: req.body.role }), req.body.password, (err, user) => {

        if (err) {

            return res.status(500).json({

                error: err

            });

        }

        passport.authenticate('local')(req, res, () => {

            return res.status(200).json({

                status: 'Registro exitoso!'

            });

        });

    });

});`
