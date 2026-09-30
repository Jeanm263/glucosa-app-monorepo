# GlucosaApp - Guía de Despliegue Móvil

Aplicación móvil para Android usando Capacitor.

## Requisitos

1. Node.js 20+
2. JDK 11+
3. Android Studio (recomendado para emulador)
4. Android SDK

## Pasos para el Despliegue

### 1. Construir la aplicación web

```bash
npm install
npm run build
```

### 2. Agregar Capacitor (si es la primera vez)

```bash
npx cap add android
```

### 3. Copiar archivos web al proyecto Android

```bash
npm run build:android
```

Este comando ejecuta:
- `npm run build` (genera `dist/`)
- `npx cap add android` (si no existe)
- `npx cap copy android` (copia `dist/` a Android)

### 4. Abrir en Android Studio

```bash
npm run open:android
```

### 5. Construir el APK

Desde Android Studio:
- Build → Generate Signed Bundle / APK
- O desde terminal:
```bash
cd android && ./gradlew assembleDebug
```

El APK estará disponible en `android/app/build/outputs/apk/debug/`.

## Configuración del Backend

La app móvil necesita apuntar al backend. Actualiza `.env.production`:

```
VITE_API_URL=https://tu-backend-en-render.onrender.com/api
```

## Solución de Problemas

1. **Error de conexión**: Verifica que el backend esté accesible desde móvil/emulador
2. **CORS**: Asegúrate de que el backend tenga `FRONTEND_URL` configurado correctamente
3. **Build fallido**: Ejecuta `npm run build` y revisa errores de TypeScript
