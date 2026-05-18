# 🖥️ UserFlow — Dashboard de Gestión de Usuarios

Panel administrativo moderno para gestión de cuentas, roles y accesos, construido con HTML5, CSS Grid y Flexbox puro, sin dependencias de frameworks.

---

## 📋 Descripción

**UserFlow** es un dashboard administrativo de gestión de usuarios que permite visualizar métricas clave, distribución de roles, registros de actividad reciente y una tabla de datos interactiva. Diseñado con un estilo oscuro profesional optimizado para uso en escritorio, tablet y móvil.

### Componentes principales

| Componente | Descripción |
|---|---|
| **Sidebar** | Navegación lateral colapsable con indicador de sección activa |
| **Header** | Barra superior con buscador, notificaciones y perfil |
| **KPI Cards** | 4 tarjetas de métricas clave (total, activos, pendientes, suspendidos) |
| **Gráfico de barras** | Visualización CSS de nuevos registros semanales |
| **Distribución de roles** | Barras de progreso por tipo de usuario |
| **Tabla de datos** | Lista paginada con badges, estados y acciones inline |
| **Footer** | Información del sistema y créditos |

---

## 🛠️ Tecnologías usadas

- **HTML5** semántico (`<aside>`, `<header>`, `<main>`, `<footer>`, `<section>`, `<article>`)
- **CSS Grid** para el layout principal (sidebar + header + main + footer)
- **Flexbox** para componentes internos (tarjetas, nav, tabla, filtros)
- **CSS Custom Properties** (variables para colores, tipografía, espaciado)
- **Media Queries** (1024px, 768px, 400px)
- **JavaScript vanilla** mínimo (toggle sidebar, nav activo)
- Sin frameworks ni librerías externas

---

## 📐 Estructura del layout (CSS Grid)

```
body (flex)
├── aside.sidebar          ← sticky, 260px
└── .dashboard-wrapper     ← grid: header | main | footer
    ├── header.header
    ├── main.main
    │   ├── .page-header
    │   ├── .kpi-grid      ← grid 4 cols → 2 cols (tablet) → 1 col (móvil)
    │   ├── .mid-grid      ← grid 1.6fr / 1fr → 1 col (tablet)
    │   └── .table-section
    └── footer.footer
```

---

## 📱 Capturas de pantalla

### 🖥️ Escritorio
![Desktop](evidencias/desktop.png)

### 📱 Tablet (1024px)
![Tablet](evidencias/tablet.png)

### 📱 Móvil (768px)
![Mobile](evidencias/mobile.png)

> **Cómo tomar las capturas:** Abre `index.html` en Chrome → DevTools (F12) → icono de dispositivo responsive → selecciona el ancho.

---

## 🎨 Decisiones de diseño

### Paleta oscura
Se eligió un tema oscuro (`#0f1117` base) por ser el estándar en herramientas administrativas modernas. Reduce la fatiga visual en sesiones largas.

### Acento azul (`#4f8ef7`)
Color neutro y profesional que indica estado activo y acciones primarias sin ser agresivo.

### CSS Grid para el layout
Permite definir áreas nombradas (`grid-template-areas`) haciendo el layout legible y fácil de modificar. El sidebar queda fuera del grid interno y se maneja con `position: sticky` en desktop y `position: fixed` drawer en móvil.

### Flexbox para componentes
Cada componente interno (tarjeta KPI, fila de tabla, menú lateral) usa Flexbox para alineación precisa sin necesidad de frameworks.

### Tabla responsive
En móvil se oculta el `<thead>` y se usan atributos `data-label` + pseudoelementos CSS `::before` para mostrar las etiquetas de columna inline.

---

## ♿ Accesibilidad

| Práctica | Implementación |
|---|---|
| Roles ARIA | `role="navigation"`, `role="main"`, `role="banner"`, `role="contentinfo"` |
| `aria-label` | Todos los botones de ícono, el buscador, la tabla, la paginación |
| `aria-current="page"` | Link activo en el sidebar |
| `aria-expanded` | Botón hamburguesa refleja el estado del sidebar |
| Tabindex | Tarjetas KPI navegables con teclado |
| `role="progressbar"` | Barras de distribución de roles con `aria-valuenow` |
| `role="img"` + `aria-label` | Gráfico de barras con descripción textual completa |
| `:focus-visible` | Outline visible al navegar con Tab |
| Contraste | Texto primario `#e8eaf6` sobre `#181c27` → ratio > 7:1 |
| `alt=""` en SVGs | Íconos decorativos con `aria-hidden="true"` |
| Escape key | Cierra el sidebar en móvil |

---

## 📁 Estructura de archivos

```
admin-dashboard/
├── index.html          ← Estructura HTML5
├── styles.css          ← Estilos (Grid + Flexbox + Variables CSS)
├── README.md           ← Este archivo
└── evidencias/
    ├── desktop.png
    ├── tablet.png
    └── mobile.png
```

---

## 🚀 Cómo ejecutar

1. Clona el repositorio:
   ```bash
   git clone https://github.com/TU_USUARIO/admin-dashboard.git
   ```
2. Abre `index.html` directamente en el navegador.
3. No requiere servidor ni dependencias.

---

*Desarrollado por Santiago Z. · Universidad Manuela Beltrán · 2025*