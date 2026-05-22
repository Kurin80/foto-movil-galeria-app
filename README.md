# 📱 Foto Móvil Galería App

Aplicación web responsive (mobile-first) para subir, organizar y visualizar fotografías desde el celular.

## 🚀 Stack Tecnológico

- **Frontend**: Next.js 14 (React)
- **Backend**: Node.js + Express
- **Base de Datos**: PostgreSQL
- **Almacenamiento**: Local (Cloud Storage ready)
- **Autenticación**: JWT + Email/Password

## 📋 Requisitos Previos

- Node.js 18+
- PostgreSQL 12+
- npm o yarn

## 🛠️ Instalación

### 1. Clonar el repositorio

```bash
git clone https://github.com/Kurin80/foto-movil-galeria-app.git
cd foto-movil-galeria-app
```

### 2. Configurar Backend

```bash
cd backend
npm install
```

Crear archivo `.env`:

```
PORT=5000
DATABASE_URL=postgresql://usuario:contraseña@localhost:5432/foto_galeria
JWT_SECRET=tu_clave_secreta_super_segura_aqui
NODE_ENV=development
```

### 3. Configurar Base de Datos

```bash
# Conectarse a PostgreSQL
psql -U postgres

# Crear base de datos
CREATE DATABASE foto_galeria;

# Salir
\q
```

Luego ejecutar migraciones:

```bash
cd backend
npm run migrate
```

### 4. Configurar Frontend

```bash
cd frontend
npm install
```

Crear archivo `.env.local`:

```
NEXT_PUBLIC_API_URL=http://localhost:5000/api
```

## 📱 Ejecutar la Aplicación

### Desarrollo

**Terminal 1 - Backend**:
```bash
cd backend
npm run dev
```

**Terminal 2 - Frontend**:
```bash
cd frontend
npm run dev
```

Acceder a: `http://localhost:3000`

## 📁 Estructura del Proyecto

```
foto-movil-galeria-app/
├── backend/
│   ├── src/
│   │   ├── routes/          # Rutas de API
│   │   ├── controllers/     # Lógica de negocio
│   │   ├── models/          # Modelos de BD
│   │   ├── middleware/      # Autenticación, validación
│   │   ├── config/          # Configuración
│   │   └── server.js        # Entrada principal
│   ├── migrations/          # Migraciones de BD
│   ├── .env                 # Variables de entorno
│   └── package.json
├── frontend/
│   ├── app/
│   │   ├── (auth)/          # Páginas de autenticación
│   │   ├── (app)/           # Páginas de la app
│   │   └── layout.js        # Layout raíz
│   ├── components/          # Componentes React
│   ├── lib/                 # Utilidades
│   ├── public/              # Assets estáticos
│   └── package.json
├── docker-compose.yml       # (Opcional) PostgreSQL con Docker
└── README.md
```

## 🎯 Funcionalidades Principales

✅ Autenticación con JWT (Email/Password)
✅ Crear, renombrar y eliminar carpetas
✅ Subir múltiples fotos
✅ Galería responsive tipo Google Photos
✅ Ordenar por fecha
✅ Mover imágenes entre carpetas
✅ Optimizado para móvil

## 🔌 Endpoints de API

### Autenticación
- `POST /api/auth/register` - Registro
- `POST /api/auth/login` - Login
- `POST /api/auth/logout` - Logout

### Carpetas
- `GET /api/folders` - Listar carpetas
- `POST /api/folders` - Crear carpeta
- `PUT /api/folders/:id` - Renombrar carpeta
- `DELETE /api/folders/:id` - Eliminar carpeta

### Fotos
- `GET /api/photos?folderId=...` - Listar fotos
- `POST /api/photos/upload` - Subir foto
- `DELETE /api/photos/:id` - Eliminar foto
- `PUT /api/photos/:id/move` - Mover foto a otra carpeta

## 🌐 Acceso desde Celular

1. Backend y frontend en la misma red
2. Obtener IP local: `ipconfig` (Windows) o `ifconfig` (Mac/Linux)
3. Acceder desde celular: `http://[TU_IP]:3000`

## 🚀 Deploy (Opcional)

- **Frontend**: Vercel (Next.js nativo)
- **Backend**: Heroku, Railway, Render
- **BD**: AWS RDS, Neon, Railway

## 📝 Notas

- Las imágenes se guardan en `backend/uploads/` (modificable a Cloud Storage)
- JWT expira en 7 días
- Las contraseñas se hashean con bcrypt

---

**Happy Coding! 📸**
