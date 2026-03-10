[README.md](https://github.com/user-attachments/files/25856979/README.md)
# 🛡️ Apollo Emergency Response System v2

> Sistema corporativo de reporte de emergencias en tiempo real con cruce automático de base de datos de empleados.

![Status](https://img.shields.io/badge/Status-Live-brightgreen) ![Cost](https://img.shields.io/badge/Costo-$0%2Fmes-blue) ![Firebase](https://img.shields.io/badge/Firebase-Realtime%20DB-orange) ![Netlify](https://img.shields.io/badge/Netlify-Deployed-teal)

---

## 🚀 URLs del Sistema

| Página | URL |
|--------|-----|
| 📋 Formulario Empleados | `https://stellar-selkie-464814.netlify.app/__index.html` |
| 📊 Dashboard Admin | `https://stellar-selkie-464814.netlify.app/__dashboard.html` |
| 👥 Panel de Empleados | `https://stellar-selkie-464814.netlify.app/__admin.html` |

**🔑 Contraseña:** `Brigada2026`

---

## 📁 Archivos del Proyecto

| Archivo | Descripción |
|---------|-------------|
| `__index.html` | Formulario de reporte para empleados con auto-fill por email |
| `__dashboard.html` | Dashboard en tiempo real para administradores |
| `__admin.html` | Panel para gestionar la base de datos de empleados |
| `empleados_apollo.xlsx` | Plantilla Excel de la base de datos de empleados |
| `empleados_firebase.json` | Base de datos lista para importar a Firebase |

---

## ✨ Funcionalidades Principales

### 📋 Formulario de Empleados (`__index.html`)
- El empleado ingresa su **email corporativo**
- El sistema hace un **cruce automático con Firebase** usando el email como trigger
- Se auto-completan: **Nombre, Manager, Departamento y Teléfono**
- Solo selecciona su estado: ✅ A Salvo / ⚠️ Necesito Ayuda / 🆘 Emergencia
- Confirmación visual al enviar

### 📊 Dashboard en Tiempo Real (`__dashboard.html`)
- Actualización **EN VIVO** sin recargar la página
- Contadores por estado: A Salvo, Necesitan Ayuda, Emergencia
- Resumen por departamento: HVO, Support, CA, Sales, HR
- Filtros por estado y búsqueda por nombre
- Columna **Agente Brigada** — editable en tiempo real
- Exportar reportes a **CSV**
- Botón de reinicio con confirmación
- Protegido por contraseña

### 👥 Panel Admin de Empleados (`__admin.html`)
- Agregar empleados nuevos sin tocar Firebase
- Editar información de empleados existentes
- Eliminar empleados con confirmación
- Búsqueda en tiempo real
- Protegido por contraseña

---

## 🔥 Arquitectura Firebase

```
/empleados/
  {email_key}/
    email:          "oscar.lorenzoni@apollo.io"
    nombre:         "Oscar Lorenzoni Narvaez"
    manager:        "Alejandro Nunez"
    departamento:   "HVO"
    telefono:       "+525572137646"
    agente_brigada: "Maria Lopez"

/reportes/
  {auto-id}/
    email:          "oscar.lorenzoni@apollo.io"
    nombre:         "Oscar Lorenzoni Narvaez"
    manager:        "Alejandro Nunez"
    departamento:   "HVO"
    telefono:       "+525572137646"
    status:         "safe" | "help" | "emergency"
    notes:          "Notas adicionales"
    agente_brigada: "Erika Barrios"
    timestamp:      1234567890000
```

---

## 🔄 Flujo del Sistema

```
Empleado ingresa email
        ↓
Firebase busca el email en /empleados
        ↓
Auto-completa: Nombre, Manager, Departamento, Teléfono
        ↓
Empleado selecciona su estado + notas
        ↓
Reporte guardado en /reportes
        ↓
Dashboard se actualiza EN VIVO
        ↓
Admin asigna Agente de Brigada
```

---

## 🛠️ Stack Tecnológico

| Tecnología | Uso | Costo |
|------------|-----|-------|
| Firebase Realtime Database | Base de datos en tiempo real | $0 |
| Netlify | Hosting y deployment automático | $0 |
| GitHub | Repositorio y control de versiones | $0 |
| Firebase JS SDK v10.12.2 | Conexión frontend-database | $0 |
| HTML / CSS / JavaScript | Frontend | $0 |
| **TOTAL** | | **$0/mes** |

---

## 📊 Cómo Actualizar la Base de Empleados

### Opción A — Panel Admin (Recomendada)
1. Ve a `/__admin.html`
2. Ingresa la contraseña
3. Agrega, edita o elimina empleados directamente

### Opción B — Importar Excel a Firebase
1. Llena el archivo `empleados_apollo.xlsx`
2. Conviértelo a JSON
3. Ve a **Firebase Console** → Realtime Database → ⋮ → **Import JSON**

### Opción C — Firebase Console directo
1. Ve a `console.firebase.google.com`
2. Entra a tu proyecto → **Realtime Database**
3. Edita el nodo `empleados` directamente

---

## 🚀 Deployment

Este proyecto usa **GitHub + Netlify** para deployment automático:
- Cada `push` a la rama `main` dispara un deploy automático en Netlify
- Los cambios están en producción en menos de 60 segundos

---

## 👨‍💻 Desarrollado por

**Oscar Lorenzoni Narvaez** — GTM Product Specialist @ Apollo.io
🔗 [GitHub: Zoniloren](https://github.com/Zoniloren/New-Apollo-Emergency)

---

*Sistema de uso interno exclusivo — Apollo.io México* 🇲🇽
