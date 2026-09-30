# GlucosaApp Frontend

Aplicación frontend para GlucosaApp - Acompañamiento nutricional y educativo para personas con diabetes tipo II.

## Estado del Servicio

✅ **Servicio en funcionamiento** - Conectado al backend `glucosa-app-backend`

## Requisitos Previos

- Node.js 20+
- npm 10+

## Instalación

```bash
npm install
```

## Variables de Entorno

Crea un archivo `.env` en la raíz del proyecto con las siguientes variables:

```env
VITE_API_URL=http://localhost:4000/api
VITE_USE_MOCK_SERVICE=false
```

## Desarrollo

```bash
npm run dev
```

La aplicación se iniciará en `http://localhost:5173`.

## Construcción para Producción

```bash
npm run build
```

Los archivos compilados se generarán en `dist/`.

## Despliegue

### Render (Web)

1. Conecta tu repositorio a [Render](https://render.com)
2. Configura como "Static Site"
3. Build Command: `npm install && npm run build`
4. Publish Directory: `dist`
5. Añade las variables de entorno de `.env.production`
6. Ve a `DEPLOY_RENDER.md` para instrucciones detalladas

### Docker

```bash
docker-compose up -d
```

### Mobile (Capacitor)

```bash
npm run build:android
npm run open:android
```

## Scripts Disponibles

| Script | Descripción |
|--------|-------------|
| `dev` | Iniciar servidor de desarrollo |
| `build` | Construir para producción |
| `lint` | Ejecutar ESLint |
| `test` | Ejecutar pruebas unitarias |
| `test:watch` | Ejecutar pruebas en modo observador |
| `preview` | Servir build localmente |
| `build:android` | Generar APK para Android |
| `open:android` | Abrir proyecto Android en Android Studio |

## Estructura del Proyecto

```
src/
├── assets/          # Imágenes y recursos estáticos
├── components/      # Componentes reutilizables
├── config/          # Configuración (env, theme)
├── constants/       # Datos constantes
├── contexts/        # Contextos de React (Auth, Theme)
├── hooks/           # Hooks personalizados
├── screens/         # Pantallas/vistas principales
├── schemas/         # Esquemas de validación (Zod)
├── services/        # Servicios API
├── styles/          # Estilos CSS
├── types/           # Tipos TypeScript
├── utils/           # Utilidades
├── __mocks__/       # Mocks para pruebas (MSW)
└── __tests__/       # Pruebas unitarias
```

## Características

- Autenticación con JWT y cookies
- Tema claro/oscuro
- Monitoreo de glucosa
- Búsqueda y tracking de alimentos
- Contenido educativo sobre diabetes
- Notificaciones
- Soporte móvil (Capacitor + Android)
- Modo offline con servicios mock

## Tecnologías

- React 19 + TypeScript
- Vite (build tool)
- Tailwind CSS (estilos)
- React Router DOM 7 (rutas)
- React Hook Form + Zod (form validation)
- Axios (HTTP client)
- Capacitor 7 (mobile)
- Jest + Testing Library (testing)
- MSW (mock service worker)
