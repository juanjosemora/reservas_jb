Aviastour 🛫
Sistema de Gestión de Viajes Aéreos ✈️

Aviastour es un sistema web para la gestión de reservas de viajes aéreos, desarrollado con PHP, MySQL, HTML, CSS y JavaScript.
La aplicación implementa autenticación de usuarios, control de roles, auditoría de operaciones y una base de datos relacional, permitiendo una administración segura y organizada de la información.

Características del Sistema 🚀
Roles de Usuario 👥
Administrador 🧑‍💼

Administración de usuarios y roles del sistema.

Gestión completa de los viajes registrados.

Supervisión general de todas las reservas.

Empleado 👷

Consulta de viajes disponibles.

Actualización del estado de las reservas (Confirmar / Cancelar).

Cliente 🧍

Visualización del catálogo de viajes con soporte gráfico.

Registro y gestión de reservas personales.

Cancelación de reservas activas.

Estructura del Proyecto 🧩
aviastour/
│
├── api/
│   ├── auth.php
│   ├── db.php
│   ├── viajes.php
│   ├── reservas.php
│   ├── mis_reservas.php
│   ├── reservar.php
│   ├── cancelar_reserva.php
│   ├── empleado_reservas.php
│   ├── actualizar_reserva.php
│   └── empleado/
│       ├── consult.php
│       └── reservas.php
│
├── css/
│   ├── administrador.css
│   ├── cliente.css
│   ├── empleado.css
│   ├── index.css
│   ├── inicio.css
│   └── registro.css
│
├── html/
│   ├── administrador.html
│   ├── cliente.html
│   ├── empleado.html
│   ├── index.html
│   ├── inicio.html
│   └── registro.html
│
├── js/
│   ├── utils.js
│   ├── administrador.js
│   ├── cliente.js
│   ├── empleado.js
│   ├── index.js
│   ├── inicio.js
│   └── registro.js
│
├── public/
│   └── logo.jpg
│
└── database/
    └── formulariocrud.sql

Base de Datos 📊

Nombre: formulariocrud

Tabla	Descripción
compania	Información de clientes
usuarios	Credenciales y roles
reservas	Registro de reservas
roles	Permisos del sistema
auditoria_reservas	Historial de cambios
Auditoría de Cambios 🔐
CREATE TRIGGER auditoria_reserva_update
AFTER UPDATE ON reservas
FOR EACH ROW
BEGIN
  INSERT INTO auditoria_reservas (id_reserva, usuario, accion, detalles)
  VALUES (
    OLD.id_reserva,
    USER(),
    'UPDATE',
    CONCAT('Reserva modificada: estado "', OLD.estado, '" → "', NEW.estado, '"')
  );
END;

Instalación del Proyecto ⚙️

Clonar el repositorio:

git clone https://github.com/tuusuario/aviastour.git


Copiar el proyecto en htdocs:

C:\xampp\htdocs\aviastour


Configurar la base de datos:

Crear la base de datos formulariocrud

Importar database/formulariocrud.sql

Configurar api/db.php:

$host = 'localhost';
$user = 'root';
$pass = '';
$db   = 'formulariocrud';


Iniciar Apache y MySQL.

Acceder desde el navegador:

http://localhost/aviastour/html/inicio.html

Accesos de Prueba 🔑
Rol	Usuario	Contraseña
Administrador	Laura	123456
Empleado	cami	qwer
Cliente	Jesus	1234
Tecnologías Implementadas 🧠
Área	Herramientas
Interfaz	HTML5, CSS3, JavaScript
Lógica	PHP
Datos	MySQL
Entorno	XAMPP
Versionado	Git / GitHub
Flujo de Navegación 🗺️
Inicio (index.html)
│
├── Registro
├── Inicio de Sesión
│       ├── Administrador
│       ├── Empleado
│       └── Cliente
│
└── Cerrar Sesión

Autor del Proyecto 👨‍💻

Juan José Bocanegra Mora
Técnico en Programación de Software

Contexto Académico 🎓

Servicio Nacional de Aprendizaje (SENA)
Tercer Trimestre — Proyecto Académico
