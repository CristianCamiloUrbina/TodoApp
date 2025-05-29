## TodoApp

API para la gestión de tareas y categorías con autenticación JWT en ASP.NET Core.

## Tecnologías usadas

ASP.NET Core Web API
Entity Framework Core
SQL Server
JWT (JSON Web Token)
Swagger
Funcionalidades

## Registro y login de usuarios

Gestión de tareas (CRUD)
Gestión de categorías
Roles de usuario

## Instalación

Clona el repositorio
git clone https://github.com/CristianCamiloUrbina/TodoApp.git
Abre el proyecto en Visual Studio
Configura la cadena de conexión en appsettings.json
Ejecuta las migraciones con:
dotnet ef database update
Ejecuta la aplicación (F5 o dotnet run)

## Endpoints principales

POST /api/Account/register → Registrar nuevo usuario
POST /api/Account/login → Autenticar usuario y obtener token JWT
GET /api/Tareas → Listar tareas (autenticado)
POST /api/Tareas → Crear nueva tarea
GET /api/Categorias → Listar categorías
POST /api/Categorias → Crear nueva categoría


## Estructura del proyecto

TodoApp/
│
├── Controllers/            # Controladores de la API
│   ├── AccountController.cs
│   ├── TareasController.cs
│   └── CategoriasController.cs
│
├── Models/                 # Modelos de datos (Entidades)
│   ├── Usuario.cs
│   ├── Tarea.cs
│   └── Categoria.cs
│
├── DTOs/                   # Objetos de transferencia de datos
│   ├── RegisterDTO.cs
│   ├── LoginDTO.cs
│   ├── TareaDTO.cs
│   └── CategoriaDTO.cs
│
├── Services/               # Servicios con lógica de negocio
│   ├── ITareaService.cs
│   ├── ICategoriaService.cs
│   └── Implementaciones/
│       ├── TareaService.cs
│       └── CategoriaService.cs
│
├── Data/                   # Contexto de la base de datos y seeding
│   └── ApplicationDbContext.cs
│
├── Helpers/                # Clases auxiliares (por ejemplo, JWT)
│   └── JwtHelper.cs
│
├── Middleware/             # Middleware personalizado (si aplica)
│   └── ExceptionMiddleware.cs
│
├── Repositories/           # Capa de acceso a datos (si separas servicios y acceso)
│   ├── ITareaRepository.cs
│   └── TareaRepository.cs
│
├── Mappings/               # Configuraciones de AutoMapper
│   └── MappingProfile.cs
│
├── appsettings.json        # Configuración de la aplicación
├── Program.cs              # Punto de entrada del proyecto
├── Startup.cs (si usas .NET 5/3.1) o configuración en Program.cs para .NET 6+
└── README.md               # Documentación general del proyecto

## DIAGRAMA BASE DE DATOS

<img width="510" alt="image" src="https://github.com/user-attachments/assets/2cab9454-7e89-47c8-b7fd-f4d7f606e3df" />


## Explicación de endpoints y cómo usarlos

## Endpoints Principales

Todos los endpoints (excepto register y login) requieren autenticación con JWT.

## Autenticación

POST /api/account/register

Registra un nuevo usuario.

{
  "username": "usuario1",
  "email": "usuario@email.com",
  "password": "Password123!"
}

POST /api/account/login

Inicia sesión y devuelve un token JWT.

{
  "username": "usuario1",
  "password": "Password123!"
}

Respuesta:

{ "token": "eyJhbGciOi..." }

## Gestión de Tareas

GET /api/tareas

Obtiene las tareas del usuario autenticado.

POST /api/tareas

Crea una nueva tarea.

{
  "titulo": "Estudiar para el examen",
  "descripcion": "Matemáticas y Física",
  "estado": "Pendiente"
}

PUT /api/tareas/{id}

Actualiza una tarea por ID.

DELETE /api/tareas/{id}

Elimina una tarea por ID.

## Gestión de Categorías

GET /api/categorias

Lista todas las categorías.

POST /api/categorias

Crea una nueva categoría.

{
  "nombre": "Trabajo"
}

## Autenticación JWT

Para acceder a los endpoints protegidos:

Inicia sesión con /api/account/login.

Copia el token recibido.

En Swagger, haz clic en "Authorize" y pega:

Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6...

O en Postman, usa el header:

Authorization: Bearer TU_TOKEN

## Ejecución del Proyecto

Clona el repositorio:

git clone https://github.com/tu-usuario/TodoApp.git

Configura la cadena de conexión en appsettings.json.

Ejecuta las migraciones:

dotnet ef database update

Inicia el servidor:

dotnet run

## Autor

Desarrollado por Cristian 




