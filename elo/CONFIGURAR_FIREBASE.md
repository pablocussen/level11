# 🔥 Cómo Configurar Firebase (Gratis)

## Tiempo: 5 minutos

---

## Paso 1: Crear cuenta Firebase

1. Ve a **https://console.firebase.google.com**
2. Inicia sesión con tu cuenta de Google
3. Haz clic en **"Crear un proyecto"** (o "Add project")

---

## Paso 2: Crear proyecto

1. Nombre del proyecto: **level11** (o el que quieras)
2. Google Analytics: **No** (no es necesario)
3. Haz clic en **"Crear proyecto"**
4. Espera unos segundos y clic en **"Continuar"**

---

## Paso 3: Agregar app web

1. En la página principal del proyecto, haz clic en el ícono **`</>`** (Web)
2. Nombre de la app: **level11**
3. **NO** marques "Firebase Hosting"
4. Haz clic en **"Registrar app"**
5. Verás un bloque de código. Copia SOLO el objeto `firebaseConfig`:

```json
{
  "apiKey": "AIza...",
  "authDomain": "level11-xxxxx.firebaseapp.com",
  "databaseURL": "https://level11-xxxxx-default-rtdb.firebaseio.com",
  "projectId": "level11-xxxxx",
  "storageBucket": "level11-xxxxx.appspot.com",
  "messagingSenderId": "123456789",
  "appId": "1:123456789:web:abcdef"
}
```

6. Haz clic en **"Continuar a la consola"**

---

## Paso 4: Activar Realtime Database

1. En el menú izquierdo, ve a **"Crear"** → **"Realtime Database"**
2. Haz clic en **"Crear base de datos"**
3. Ubicación: **United States (us-central1)** (o la más cercana)
4. Modo de seguridad: selecciona **"Modo de prueba"** (test mode)
5. Haz clic en **"Habilitar"**

---

## Paso 5: Reglas de seguridad (importante)

1. En Realtime Database, ve a la pestaña **"Reglas"**
2. Reemplaza todo con:

```json
{
  "rules": {
    "families": {
      "$familyId": {
        ".read": true,
        ".write": true
      }
    }
  }
}
```

3. Haz clic en **"Publicar"**

> ⚠️ Estas reglas son simples para facilitar el uso. Solo tú y tu hija usarán la app.

---

## Paso 6: Usar en la app

1. Abre **Level:11** en el navegador (index.html o cussen.cl/elo)
2. Pega el objeto JSON del Paso 3 en el campo de configuración
3. ¡Listo! La app se conectará automáticamente

---

## Resumen

| Paso | Acción |
|------|--------|
| 1 | Crear cuenta en Firebase Console |
| 2 | Crear proyecto "level11" |
| 3 | Agregar app web y copiar config |
| 4 | Activar Realtime Database |
| 5 | Configurar reglas de seguridad |
| 6 | Pegar config en Level:11 |

---

## ¿Problemas?

- **"Permission denied"**: Revisa las reglas del Paso 5
- **No se sincroniza**: Verifica que el `databaseURL` esté correcto
- **No aparece databaseURL**: Asegúrate de crear la Realtime Database (Paso 4) ANTES de copiar la config

---

*Una vez configurado, la app sincroniza automáticamente entre el Samsung y el iPhone/iPad* 📱↔️📱
