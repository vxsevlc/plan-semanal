# Planificador de Comidas — Juan y Marian

Aplicación web para **planificar comidas y cenas** de la semana, guardar recetas y **generar la lista de la compra** automáticamente. Funciona **sin backend** (todo ocurre en el navegador con `localStorage`) y está optimizada para **móvil y escritorio**.

> **Demo:** https://vxsevlc.github.io/plan-semanal/

---

## ✨ Características

- **Calendario semanal** con scroll horizontal en móvil y columna “Tipo” fija.
- **Slots por día**: Comida / Cena.
- **Pastillas legibles**: el nombre de la receta se muestra **completo** (no se corta).
- **Base de datos de recetas** con búsqueda, filtros (tipo/dificultad) y **drag & drop** hacia el calendario.
- **Añadir receta** desde un modal (nombre, descripción, tipo, dificultad, tiempo, ingredientes).
- **Añadir rápido**: selecciona una receta y toca un hueco del calendario.
- **Lista de la compra** generada a partir del plan, con ranking de ingredientes más usados.
- **Exportar / Importar** recetas en JSON (compatible con lotes grandes de recetas).
- **Sin servidor**: un solo `index.html` (HTML + Tailwind + JavaScript).
- **Branding corporativo** con verde `#009688` (aplicado en header, tabs y pastillas).

---

## 📱 Diseño responsive

- Calendario con **scroll horizontal** en pantallas pequeñas.
- **Primera columna fija** (“Tipo”) para mantener el contexto mientras se desplaza.
- Pastillas `.meal-chip` muestran el **nombre completo** (`white-space: normal; overflow-wrap: anywhere;`).

---

## 🧱 Stack

- **Frontend:** HTML + Tailwind (CDN) + JavaScript vanilla  
- **Iconos:** Font Awesome (CDN)  
- **Datos locales:** `localStorage` (no requiere base de datos)

---

## 🚀 Empezar

### A) Usar en local
1. Descarga o clona el repositorio.
2. Abre `index.html` en tu navegador. ¡Listo!

### B) Publicar en GitHub Pages
1. Sube `index.html` a la rama `main`.
2. Ve a **Settings → Pages**.
   - **Source:** `Deploy from a branch`
   - **Branch:** `main` / `/root`
   - Pulsa **Save**.
3. Tu web quedará en: `https://TU_USUARIO.github.io/TU_REPO/`  
   (en este caso: `https://vxsevlc.github.io/plan-semanal/`)

---

## 📦 Importar / Exportar recetas

En la pestaña **Base de Datos**:
- **Exportar** → descarga un JSON con todas tus recetas.
- **Importar** → selecciona un archivo JSON compatible.

**Formato aceptado:**

```json
{
  "recipes": [
    {
      "id": 1,
      "name": "Paella Valenciana",
      "description": "Paella tradicional con pollo, conejo y verduras.",
      "difficulty": "media",          // "facil" | "media" | "dificil"
      "time": 75,                     // minutos
      "type": "lunch",                // "lunch" (comida) | "dinner" (cena)
      "ingredients": [
        "aceite de oliva", "arroz", "pollo", "conejo", "judía verde", "garrofón", "tomate", "azafrán", "sal"
      ]
    }
  ]
}
