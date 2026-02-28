# AniVault v2

Tracker personal de anime construido con **React + Vite + Supabase**.

---

## 🚀 Setup local

### 1. Instalar dependencias
```bash
npm install
```

### 2. Configurar variables de entorno
```bash
cp .env.example .env.local
```
Edita `.env.local` y pega tus credenciales de Supabase:
```
VITE_SUPABASE_URL=https://xxxxxxxxxxxx.supabase.co
VITE_SUPABASE_ANON_KEY=eyJhbGci...
```
> Las encuentras en **Supabase Dashboard → Settings → API**

### 3. Inicializar la base de datos
En Supabase Dashboard → **SQL Editor → New query**, pega y ejecuta el contenido de `supabase_setup.sql`.

### 4. Iniciar en desarrollo
```bash
npm run dev
```

### 5. Build de producción
```bash
npm run build
npm run preview   # opcional: probar el build localmente
```

---

## ☁️ Deploy en Vercel

1. Sube el proyecto a GitHub.
2. En **Vercel → New Project**, importa el repositorio.
3. En **Environment Variables**, agrega:
   - `VITE_SUPABASE_URL`
   - `VITE_SUPABASE_ANON_KEY`
4. Framework preset: **Vite** (Vercel lo detecta automáticamente).
5. Click **Deploy** — listo ✅

> El archivo `vercel.json` ya gestiona el routing SPA para que las rutas no den 404.

---

## 📁 Estructura del proyecto

```
anivault/
├── public/
│   └── favicon.svg
├── src/
│   ├── AnimeTracker.jsx   ← componente principal
│   ├── supabaseClient.js  ← cliente Supabase + helpers DB/Auth
│   ├── App.jsx            ← wrapper raíz
│   └── main.jsx           ← punto de entrada React
├── supabase_setup.sql     ← SQL para inicializar la BD
├── .env.example           ← plantilla de variables de entorno
├── .gitignore
├── index.html
├── package.json
├── vercel.json            ← routing SPA para Vercel
└── vite.config.js
```
