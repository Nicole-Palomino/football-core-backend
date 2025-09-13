# Backend API - Football Core

## 📋 Descripción

API REST desarrollada con FastAPI para el sistema de gestión de ligas de fútbol. Proporciona endpoints para todas las operaciones necesarias del sistema.

## 🛠️ Tecnologías

- Python
- FastAPI
- SQLAlchemy (ORM)
- Pydantic
- JWT para autenticación

## 🚀 Instalación

1. Crea un entorno virtual:
```bash
python -m venv venv
```

2. Activa el entorno virtual:
- Windows:
```bash
venv\Scripts\activate
```
- Unix o MacOS:
```bash
source venv/bin/activate
```

3. Instala las dependencias:
```bash
pip install -r requirements.txt
```

4. Configura las variables de entorno:
```bash
cp .env.example .env
# Edita .env con tus configuraciones
```

5. Inicia el servidor de desarrollo:
```bash
./run.sh
# o
uvicorn main:app --reload
```

## 🗂️ Estructura del Proyecto

```
backend/
├── app/
│   ├── core/          # Configuraciones centrales
│   ├── crud/          # Operaciones CRUD
│   ├── models/        # Modelos SQLAlchemy
│   ├── routers/       # Endpoints de la API
│   ├── schemas/       # Esquemas Pydantic
│   └── utils/         # Utilidades
├── database.py        # Configuración de base de datos
├── main.py           # Punto de entrada de la aplicación
└── requirements.txt   # Dependencias del proyecto
```

## 📚 Documentación API

Cuando el servidor está en ejecución, puedes acceder a:

- Documentación Swagger UI: `/docs`
- Documentación ReDoc: `/redoc`

## 🔑 Endpoints Principales

### Autenticación
- POST `/auth/login` - Iniciar sesión
- POST `/auth/refresh` - Refrescar token

### Usuarios
- GET `/users/` - Listar usuarios
- POST `/users/` - Crear usuario
- GET `/users/{id}` - Obtener usuario
- PUT `/users/{id}` - Actualizar usuario
- DELETE `/users/{id}` - Eliminar usuario

### Ligas
- GET `/leagues/` - Listar ligas
- POST `/leagues/` - Crear liga
- GET `/leagues/{id}` - Obtener liga
- PUT `/leagues/{id}` - Actualizar liga
- DELETE `/leagues/{id}` - Eliminar liga

### Equipos
- GET `/teams/` - Listar equipos
- POST `/teams/` - Crear equipo
- GET `/teams/{id}` - Obtener equipo
- PUT `/teams/{id}` - Actualizar equipo
- DELETE `/teams/{id}` - Eliminar equipo

## 🔒 Seguridad

### Autenticación
- JWT (JSON Web Tokens)
- Refresh tokens
- Expiración configurable

### Autorización
- Control de acceso basado en roles (RBAC)
- Permisos granulares
- Middleware de autorización

### Protección de Datos
- Encriptación de contraseñas
- Validación de datos con Pydantic
- Sanitización de entradas
- Rate limiting

## 🧪 Testing

Ejecutar tests:

```bash
python -m pytest
```

Con coverage:

```bash
python -m pytest --cov=app tests/
```

## 📝 Contribuir

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request