# 🏢 BMT - Business Market Trading

Organización dedicada al desarrollo de plataformas de comercio electrónico y gestión empresarial.

---

## 📋 Descripción General

**BMT-PI** es una plataforma integral de comercio/mercado que proporciona un ecosistema completo para la gestión de empresas, productos, pedidos y usuarios. Combina un backend robusto en .NET 8.0 con una interfaz moderna en Vue.js 3, respaldada por pruebas automatizadas y una arquitectura escalable.

### Características Principales

✅ **API REST** moderna con .NET Core  
✅ **Aplicación Web** responsiva con Vue.js 3  
✅ **Gestión de Empresas y Productos**  
✅ **Carrito de Compra y Sistema de Pedidos**  
✅ **Generación de Reportes** (ganancias anuales, órdenes completadas, etc.)  
✅ **Autenticación y Autorización de Usuarios**  
✅ **Gestión de Direcciones y Datos de Envío**  
✅ **Sistema de Correos Electrónicos**  
✅ **Manejo de Archivos e Imágenes**  
✅ **Pruebas Unitarias y de Interfaz**  

---

## 👥 Equipo de Desarrollo

| Nombre | ID |
|--------|-----|
| David González Villanueva | C13388 |
| Marco Angulo Rodríguez | C10458 |
| Alejandro Barboza Taylor | C10886 |
| Brandon Trigueros Lara | C17899 |
| Jose Carlos Mena Diaz | C14653 |

---

## 📁 Estructura del Proyecto
```bash
BMT-PI/
├── backend/ # API REST (.NET 8.0)
│ ├── BMT-backend/ # Aplicación principal
│ │ ├── Controllers/ # Endpoints REST
│ │ ├── Domain/ # Entidades y lógica de dominio
│ │ ├── Application/ # Casos de uso e interfaces
│ │ ├── Infrastructure/ # Persistencia y dependencias externas
│ │ ├── Handlers/ # Manejadores específicos
│ │ ├── Services/ # Servicios de negocio
│ │ ├── Models/ # DTOs y modelos
│ │ └── appsettings*.json # Configuración
│ ├── BMT-Unit-Tests/ # Pruebas unitarias
│ └── BMT-UITesting/ # Pruebas de interfaz (.NET)
│
├── frontend/ # Aplicación Vue.js 3
│ └── bmt-frontend/
│ ├── src/ # Código fuente
│ ├── public/ # Activos estáticos
│ ├── package.json # Dependencias
│ └── vue.config.js # Configuración de Vue
│
├── database/ # Scripts SQL
│ ├── 01_TableCreation.sql
│ ├── 02_StoredProcedures.sql
│ ├── ...
│ └── 21_Indexes.sql
│
├── UITests/ # Pruebas de UI (Selenium IDE)
│ ├── CheckoutUITest.side
│ └── SeleniumIDETests.side
│
└── README.md
```

## 🚀 Instalación y Setup

### Requisitos Previos

- **Backend**: .NET SDK 8.0 o superior
- **Frontend**: Node.js 16+ y npm/yarn
- **Base de Datos**: SQL Server 2019 o superior
- **IDE**: Visual Studio 2022 / VS Code

### Backend

```bash
# Navegar al directorio del backend
cd backend/BMT-backend

# Restaurar dependencias
dotnet restore

# Ejecutar migraciones de base de datos
dotnet ef database update

# Ejecutar la aplicación
dotnet run

# La API estará disponible en: https://localhost:7000 (o el puerto configurado)

```
Configuración: Actualiza appsettings.json con tu cadena de conexión y variables de entorno.

## Frontend
Navegar al directorio del frontend
cd frontend/bmt-frontend

Instalar dependencias
npm install

Ejecutar en modo desarrollo
npm run serve

La aplicación estará disponible en: http://localhost:8080

## Base de Datos
Conectarse a SQL Server
sqlcmd -S <servidor> -U <usuario> -P <contraseña>

Ejecutar scripts en orden (01_ → 21_)
:r database/01_TableCreation.sql
:r database/02_StoredProcedureUpdateForeignKeyWithCascade.sql
-- ... continuar con todos los scripts

## Pruebas
Pruebas Unitarias

```bash
cd backend/BMT-Unit-Tests

# Ejecutar todas las pruebas
dotnet test

# Tests disponibles:
# - UserServiceTest
# - ProductServiceTest
# - EnterpriseServiceTest
# - OrderServiceTest
# - DirectionServiceTest
# - DistanceCalculatorTest
# - ShoppingCartServiceTest
# - Reportes (CanceledOrdersReport, CompletedOrdersReport, etc.)
```
Pruebas de UI

UITesting (Selenium/C#): BMT-UITesting
```bash
cd backend/BMT-UITesting
dotnet test
```
Selenium IDE (SIDE): Importar archivos .side en Selenium IDE

  - CheckoutUITest.side
  - SeleniumIDETestGenerarReporteGananciasAnuales.side

## Arquitectura
Backend
Implementa una Arquitectura por Capas con separación clara de responsabilidades:
```bash
Controllers (API REST)
    ↓
Application (Servicios, Queries, Interfaces)
    ↓
Domain (Entidades, Lógica de Negocio)
    ↓
Infrastructure (Base de Datos, Repositorios, Externos)
```

Patrones Utilizados:

Repository Pattern
Service Pattern
Handler Pattern
Query Pattern
Frontend
Vue.js 3 con componentes reactivos y gestión de estado:

Stack Principal:

- Vue 3 (Options API / Composition API)
- Bootstrap Vue 3 (UI Components)
- Axios (HTTP Client)
- Chart.js (Gráficos)
- Vuetify (Material Design)
- jsPDF (Generación de PDFs)

## 📊 Funcionalidades Principales

Gestión de Usuarios
- Registro e inicio de sesión
- Validación y autenticación
- Control de roles y permisos
  
Gestión de Empresas
- Creación y administración de empresas
- Datos de contacto (teléfono, email)
- Soft delete (eliminación lógica)
  
Gestión de Productos
- Catálogo de productos
- Búsqueda full-text
- Gestión de imágenes
- Stock y disponibilidad
  
Carrito de Compra y Órdenes
- Agregar/remover productos
- Gestión de cantidades
- Procesamiento de pedidos
- Historial de órdenes
  
Reportes
- Reportes de órdenes completadas
- Reportes de órdenes canceladas
- Ganancias anuales por empresa

Servicios Adicionales
- Envío de correos electrónicos
- Carga y manejo de imágenes
- Gestión de direcciones de envío
- Manejo de tarjetas de crédito

## 🔧 Tecnologías
Backend
- Framework: ASP.NET Core 8.0
- Lenguaje: C#
- ORM: Entity Framework Core (presumiblemente)
- Base de Datos: SQL Server
- Testing: xUnit / NUnit / MSTest
  
Frontend
- Framework: Vue.js 3
- Bundler: Vue CLI
- HTTP Client: Axios
- UI Components: Bootstrap Vue 3, Vuetify
- Gráficos: Chart.js
- Documentos: jsPDF

Base de Datos
- Motor: SQL Server
- Versionado: Scripts SQL versionados
- Procedimientos: Stored Procedures
- Triggers: Triggers para lógica automática

## 📝 Controladores Disponibles
| Controlador | Responsabilidad |
| :--- | :--- |
| `UserController` | Gestión de usuarios (CRUD, perfiles, roles) |
| `EnterpriseController` | Administración de entidades empresariales |
| `ProductController` | Gestión del catálogo de productos y existencias |
| `OrderController` | Procesamiento, seguimiento y estados de pedidos |
| `ShoppingCartController` | Manejo de persistencia del carrito de compras |
| `DirectionController` | Gestión de direcciones de envío y facturación |
| `ImageFileController` | Carga, almacenamiento y recuperación de imágenes |
| `MailController` | Gestión de plantillas y envío de correos electrónicos |
| `DeveloperController` | Endpoints de utilidad y pruebas para desarrollo |

## 🔐 Seguridad
- ✅ Validación de entrada (FluentValidation presumiblemente)
- ✅ Autenticación de usuarios
- ✅ Control de acceso basado en roles
- ✅ Soft delete para protección de datos
- ✅ Encriptación de datos sensibles (tarjetas de crédito)

## 📚 Documentación Adicional
- Backend API HTTP Tests - Archivo para testing con REST Client
- README Backend - Detalles técnicos del backend
- README Frontend - Detalles técnicos del frontend
- Schema Base de Datos - Documentación de esquema

## 🤝 Contribuciones
Este proyecto es desarrollado por el equipo de BMT. Para contribuir:

1. Crea una rama desde develop
2. Realiza tus cambios y pruebas
3. Crea un Pull Request con descripción clara
4. Solicita revisión a los integrantes del equipo
