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


Estructura del proyecto

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
