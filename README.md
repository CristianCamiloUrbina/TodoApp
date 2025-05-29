TodoApp

API para la gestión de tareas y categorías con autenticación JWT en ASP.NET Core.

Tecnologías usadas

ASP.NET Core Web API
Entity Framework Core
SQL Server
JWT (JSON Web Token)
Swagger
Funcionalidades

Registro y login de usuarios

Gestión de tareas (CRUD)
Gestión de categorías
Roles de usuario

Instalación

Clona el repositorio
git clone https://github.com/CristianCamiloUrbina/TodoApp.git
Abre el proyecto en Visual Studio
Configura la cadena de conexión en appsettings.json
Ejecuta las migraciones con:
dotnet ef database update
Ejecuta la aplicación (F5 o dotnet run)

Endpoints principales

POST /api/Account/register → Registrar nuevo usuario
POST /api/Account/login → Autenticar usuario y obtener token JWT
GET /api/Tareas → Listar tareas (autenticado)
POST /api/Tareas → Crear nueva tarea
GET /api/Categorias → Listar categorías
POST /api/Categorias → Crear nueva categoría

Autor

Cristian Camilo Urbina
