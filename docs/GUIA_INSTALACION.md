# 🚀 Guía de Instalación y Configuración

> Paso a paso para tener el proyecto funcionando en tu computadora

---

## ✅ Requisitos Previos

Antes de empezar, asegúrate de tener instalado:

- **Node.js** (v14 o superior) - Descarga desde [nodejs.org](https://nodejs.org)
- **Git** - Descarga desde [git-scm.com](https://git-scm.com)
- **MySQL o PostgreSQL** - (Opcional, usaremos datos simulados primero)
- **Visual Studio Code** - Recomendado para escribir código

### Verificar que esté instalado:

```bash
node --version      # Debe mostrar v14.0.0 o superior
npm --version       # Debe mostrar 6.0.0 o superior
git --version       # Debe mostrar 2.0.0 o superior
```

---

## 📥 Paso 1: Clonar el Repositorio

```bash
# Abre tu terminal y ejecuta:
git clone https://github.com/Alonvidxx2-design/estructura-proyecto-web-app.git

# Entra a la carpeta del proyecto
cd estructura-proyecto-web-app
```

---

## 🔧 Paso 2: Configurar Backend

```bash
# Entra a la carpeta del backend
cd backend

# Instala las dependencias
npm install

# Crea archivo .env (copia de .env.example)
# En Linux/Mac:
cp ../.env.example .env

# En Windows (PowerShell):
Copy-Item ../.env.example -Destination .env

# Abre .env y configura:
# - PORT=5000
# - NODE_ENV=development
```

---

## 🎨 Paso 3: Configurar Frontend

```bash
# Desde la carpeta raíz
cd frontend

# Instala las dependencias
npm install

# Crea archivo .env
# En Linux/Mac:
cp ../.env.example .env

# En Windows (PowerShell):
Copy-Item ../.env.example -Destination .env

# Abre .env y asegúrate de:
# REACT_APP_API_URL=http://localhost:5000/api
```

---

## 📊 Paso 4: (Opcional) Configurar Base de Datos

Si quieres usar una BD real en lugar de datos simulados:

### Para MySQL:

```bash
# 1. Abre MySQL desde terminal:
mysql -u root -p

# 2. Ejecuta los comandos del archivo schema.sql
source database/schema.sql;

# 3. Verifica que se creó:
USE tareas_app;
SELECT * FROM usuarios;
```

### Modificar backend para usar BD:

En `backend/server.js`, reemplaza la simulación de datos con conexión a MySQL.

---

## 🎬 Paso 5: Iniciar la Aplicación

### Terminal 1 - Backend:

```bash
cd backend
npm start

# Deberías ver:
# ╔════════════════════════════════════════════╗
# ║   🚀 SERVIDOR INICIADO CORRECTAMENTE      ║
# ║   http://localhost:5000                   ║
# ╚════════════════════════════════════════════╝
```

### Terminal 2 - Frontend:

```bash
cd frontend
npm start

# Se abrirá automáticamente en http://localhost:3000
# Si no, abre tu navegador y entra a esa URL
```

---

## ✨ ¡Listo!

Si ves la aplicación funcionando en tu navegador, ¡felicidades! 🎉

### Prueba estos casos:

1. **Agregar tarea**: Escribe algo en el input y presiona el botón
2. **Ver tareas**: Se mostrarán todas las tareas en la lista
3. **Eliminar tarea**: Haz clic en el botón "❌ Eliminar"

---

## 🐛 Solucionar Problemas

### Error: "Port 5000 already in use"

```bash
# En Linux/Mac:
lsof -ti:5000 | xargs kill -9

# En Windows (PowerShell):
Stop-Process -Id (Get-NetTCPConnection -LocalPort 5000).OwningProcess -Force
```

### Error: "Cannot find module"

```bash
# Asegúrate de estar en la carpeta correcta:
pwd  # (en la carpeta del backend o frontend)

# Reinstala dependencias:
rm -rf node_modules package-lock.json
npm install
```

### El frontend no se conecta al backend

```bash
# Verifica que ambos estén corriendo:
# - Backend: http://localhost:5000
# - Frontend: http://localhost:3000

# Abre la consola del navegador (F12) y busca errores de red
```

---

## 📚 Próximos Pasos

1. Modifica los componentes del frontend
2. Agrega nuevas rutas en el backend
3. Conecta una base de datos real
4. Implementa autenticación (Login/Registro)
5. Deploy a un servidor en la nube

---

## 💬 ¿Necesitas ayuda?

- Abre un **Issue** en GitHub
- Revisa la documentación en `docs/`
- Busca el error en Google + tu versión de Node.js

¡Happy Coding! 🚀
