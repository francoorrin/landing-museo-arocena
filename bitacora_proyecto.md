# Bitácora Integral de Avance del Proyecto
**Proyecto:** Landing Page y Sistema de Reservas para Restaurante Temático del Museo Arocena  
**Nombre Comercial:** Arocena Bistró & Arte  
**Ubicación:** Torreón, Coahuila, México  
**Fecha de actualización:** 18 de Noviembre de 2026  

---

## 1. Resumen Ejecutivo
Se diseñó, desarrolló y desplegó una landing page de alta gama para promocionar e introducir un restaurante temático inmersivo dentro de las instalaciones del **Museo Arocena** (complejo Casino de La Laguna en Torreón). La oferta gastronómica, coctelería y ambientación rotan conforme a las exposiciones temporales del museo, enfocado en conectar la gastronomía con la cultura y atraer a jóvenes adultos de 25 a 35 años.

---

## 2. Enlaces Activos y Conexiones en Producción

| Servicio | Plataforma | Estado | Enlace / Identificador |
| :--- | :--- | :--- | :--- |
| **Sitio Web en Vivo** | Vercel (Producción HTTPS) | Activo | [arocena-bistro-arte.vercel.app](https://arocena-bistro-arte-co8u5vz6t-francoorrin.vercel.app) |
| **Repositorio de Código** | GitHub | Conectado | [github.com/francoorrin/landing-museo-arocena](https://github.com/francoorrin/landing-museo-arocena) |
| **Base de Datos Cloud** | Supabase PostgreSQL | Activo | Proyecto `arocena-bistro` (`ivntldttltaovrzvpjan.supabase.co`) |
| **Diseños y Prototipos** | Google Stitch (Google Labs) | Conectado vía MCP | Proyecto ID: `14830678099978312804` |

---

## 3. Arquitectura y Componentes Desarrollados

### 3.1. Frontend (`index.html`)
- **Estética visual:** Inspirada en la jerarquía, impacto tipográfico y bloques modulares de **Adidas** combinada con la elegancia museográfica del **Museo Arocena** y el enfoque de experiencia gastronómica de **Nicanor**.
- **Secciones completadas según el PRD:**
  1. **Top Bar Promocional:** Aviso del ciclo vigente (*París en la Belle Époque*).
  2. **Header Sticky:** Logotipo, navegación por anclas, CTA rápido de reserva y acceso administrativo a base de datos.
  3. **Hero Section:** Titular monumental (*"El arte también se disfruta en la mesa"*), subtítulo de rotación temporal y llamadas a la acción.
  4. **Concepto & Propuesta de Valor:** Storytelling sobre maridar arte y cocina en la misma visita.
  5. **Ciclos Temporales:** Muestra de la exposición actual (*París Siglo XIX*) y próximas temporadas (*Raíces y Oro del Desierto - México*, *Renacimiento y Banquete - Italia*).
  6. **Más que un Restaurante:** 4 pilares clave orientados a jóvenes adultos (Menús efímeros, inmersión, spots instagrameables, planes sociales).
  7. **Menú en Turno con Filtros:** Tabs dinámicos para filtrar entradas, platos fuertes y postres/coctelería temática con descripciones de inspiración histórica y precios.
  8. **Ubicación & Acceso:** Dirección en Calle Cepeda, horarios, convenio de estacionamiento e iframe interactivo de Google Maps.
  9. **Formulario de Reservas en Tiempo Real:** Captura de Nombre, Celular/WhatsApp, Número de Comensales, Fecha y Horario con asignación automática de ID `#ARO-XXXX`.
  10. **Panel Administrativo (Modal):** Vista integrada de comensales registrados en Supabase con opción para exportar a **Excel (CSV)**.

### 3.2. Base de Datos en Supabase (PostgreSQL)
- **Tabla:** `public.reservas`
- **Esquema de columnas:**
  - `id`: `TEXT` (Clave primaria autogenerada, ej. `ARO-1042`).
  - `nombre`: `TEXT NOT NULL`
  - `telefono`: `TEXT NOT NULL`
  - `personas`: `TEXT NOT NULL`
  - `fecha`: `TEXT NOT NULL`
  - `horario`: `TEXT NOT NULL`
  - `created_at`: `TIMESTAMP WITH TIME ZONE DEFAULT timezone('utc'::text, now()) NOT NULL`
- **Políticas de Seguridad (Row Level Security - RLS):**
  - Inserción pública permitida (`anon`) para envíos desde la landing.
  - Consulta pública permitida (`anon`) para visualización de reservas.

---

## 4. Integración con Google Stitch (Google Labs)

Se estableció la conexión oficial con la API / MCP de Google Stitch (`https://stitch.googleapis.com/mcp`) utilizando la clave de autenticación vía `X-Goog-Api-Key`.

### 4.1. Metadatos del Proyecto en Stitch
- **Proyecto:** *Museo Arocena Restaurant App*
- **ID:** `14830678099978312804`
- **Tema de diseño:** *Arocena Cuaderno Gastronómico*
- **Paleta de colores oficial:**
  - Primario: `#922d16` (Terracota colonial / Lacado virreinal)
  - Superficie: `#fdf8f6` (Blanco cálido / Papel de grabado)
  - Contenedores: `#ece7e5` y `#f1edeb`
  - Texto principal: `#1c1b1a`
- **Tipografías definidas en Stitch:** `Newsreader` (Titulares de prensa y museo), `Hanken Grotesk` (Cuerpo y lectura fluida), `JetBrains Mono` (Etiquetas y fichas técnicas).

### 4.2. Pantallas Extraídas y Guardadas Localmente
Se descargaron tanto los **screenshots completos** como el **código HTML estructurado** de cada pantalla dentro del directorio local:  
📂 `PRD_Landing/assets/stitch/`

1. **Pantalla 1: Menú Actual — Restaurante Arocena**
   - ID: `52f58bf7b172475a990aa7db06b56ba4`
   - Archivos: `Menú_Actual_Restaurante_Arocena_screenshot.png` y `Menú_Actual_Restaurante_Arocena_code.html`
2. **Pantalla 2: Exposiciones y Menús — Restaurante Arocena**
   - ID: `75f6d8dd00bf47f8bd73a7b50b108f51`
   - Archivos: `Exposiciones_y_Menús_Restaurante_Arocena_screenshot.png` y `Exposiciones_y_Menús_Restaurante_Arocena_code.html`
3. **Pantalla 3: Inicio — Museo Arocena Restaurante**
   - ID: `7f07fe4f784647bbbab4c4b31451d671`
   - Archivos: `Inicio_Museo_Arocena_Restaurante_screenshot.png` y `Inicio_Museo_Arocena_Restaurante_code.html`
4. **Pantalla 4: Detalle de Platillo — Restaurante Arocena**
   - ID: `969e3a30eead47738d026c7c168ed97c`
   - Archivos: `Detalle_de_Platillo_Restaurante_Arocena_screenshot.png` y `Detalle_de_Platillo_Restaurante_Arocena_code.html`

### 4.3. URLs de Imágenes Oficiales Extraídas de Google Stitch
Las siguientes imágenes de alta resolución fueron generadas y alojadas en la infraestructura de Google Labs para el proyecto y están disponibles para embeber directamente en la web:

- **Logotipo Oficial / Sello Arocena:**
  `https://lh3.googleusercontent.com/aida/ALJJyrD-JYztuoAltVd-9cnUxUlfx2rBe0O03x5iR3CEj4i_YDf7ywm8JnUsl_kzFje6TyiqSOqFjEpCz8JQeTUsBPHZzEx0drbRQKsl9ZHqqO7XRTSEf22nN7hROAbyihj2qn3XoxMk2n_ha-Dry36Gzs4gDUPNzIKH2Esi1husPAKnQ0lAHz2e9kGWS2k7_8P5lAxGRif_jVRPagrB6-9ijcO_YmIop0777WrZ4ADnsUsmeQ`
- **Hero / Galería Virreinal y Arte Contemporáneo:**
  `https://lh3.googleusercontent.com/aida-public/AB6AXuDrGIGy7CQXxr17KyIvs1SifA_iDIGXBYX7u08DHySqTBvSU0HiKI5A9FnL9r3l1epGesxgpfyQ8_x-QKtXR1fmCNPY1KiPCTZE3wi239x6BBlIBgZ7MLtqlKZzA3_TKuE5Thr1D4aM20vSjlRsCTptLMgeK5tofbwkQTsjucJwAg1kjPUjhgxTTLmjpVQpeMLD3JcQp0M4nzMdLg-IfIyQs9OXSX-3dkfpFZFqbkmd`
- **Platillo Principal / Reinterpretación Gastronómica:**
  `https://lh3.googleusercontent.com/aida-public/AB6AXuCvLxdTdI9B9_frNxsBJUsPO7ZjmGzIqR0-Vff3IozTdDPnxDu26gcEpaQLJ2lgNXlnoxFKCWWcBgtYE62ee5wE_07BOFv9dGUDsXPX_LoAwu1EAfQN_14S6m_TM52FHsfNb81m5hZ7VTDauT0jPccLMN6ldUECK1gh3x6O-zlXpXIidgcC_v_6kpN0sVDUC979FoIhmCXZ-EgRM7ETqi942SqIZAn8CPxAYQJD7ajy`
- **Detalle de Emplatado & Maridaje:**
  `https://lh3.googleusercontent.com/aida-public/AB6AXuCweFnsAzi_hIsoqNtkmORrSicCcgVkNqgBQ9ePk4kupmQgh7mVWILKFC1loLDpjKkGJjFPdqiQOhnGfYrLUrOVh3jNrUxWQPtMWTbrTEYVHMDy3K3Xtohrzn8fvATrUvd5rIc3b2JFlPSHCLuc8sFyqx68Qljv8UP-6aKV9Quho8TgY3J3pPCzsBroz0kkSFZyX5gkigeMV4HJXxu09MVmhDr0geqoYK40-6g5GzJt`
- **Exposición "Tierra y Plata: Mestizaje en La Laguna":**
  `https://lh3.googleusercontent.com/aida-public/AB6AXuAVOtNB6-40fe0lmQ0GOPtl4nEWr8DMKqpj6nkAt9ZgfSegRJufhACu_EYrG_jS5EXuDnP0fYDqJfhVRnt1Oe33nxi6VQshEmCp3FuFdd0uE5Sj-1FVThDtwYZDvEYvgV7wreRGCM61sdXLr_6v7k1OEPMirue0RoMAJaoyCadxUuhlCPe9SwdOJP2P16dsh4Y5OuzsyW2i98MrQPyCEMfg8ZygdhJ7pfeammLGwXUA`
- **Platillos de la Carta (Entradas, Fuertes, Postres de Autor):**
  - `https://lh3.googleusercontent.com/aida-public/AB6AXuAeH8gSRkgxRba9tblFV4Vn92ev617RVV7R7ohK2f87N94FzZP-6HkQMqaAvDP-YuNxmu7v2V55T0hL0lvRvpoEtAOQUkO6ol1p8I-s6xTrL-Jy8O7-R95QJAXU9Jxn6u5OSL1hCsXiHuhem9p9jl2KSRXg2e7jDu16ZTk18AfipEbftgor2P0gv60tbOq4Xra0irH5y3EJ86CJVC_i39Qd9vOCXJlSkOMIxu8yP4eU`
  - `https://lh3.googleusercontent.com/aida-public/AB6AXuBdzAxQCC2DQZ6YNLH7LB2ZxCsF26_707DBU98BfOZxDAUv5Bjx_RVqsTMiNFta7XphMORSIlIicB93X8Guuhgd61nl4tRhOqSK2w7ij-AbGUPpD2rxUw6u_001rQR8_3JKsV_hZuaewXRyq5ev9Djdw35B9TIzAfqg3VZZr56GV4jqQf1CvSU1ogSnvuS8prRXVXadFlTW_pfFmf2quMsYE5kce6OBQ-wzJ3P1km_O`
  - `https://lh3.googleusercontent.com/aida-public/AB6AXuAkFg3cImH-9yYjn6iOctz9s8vZIcbdLWqypmAddTrs8TvrlHQFmpeyxCb_l-axy-OP6XOU99SZqReaYjfGZszbyKD2BBvXZENgEpScy0QQccYXwflfNM9atJAdYUFNzEzWzwAkL_i-fkdzJvQYSfxHCzLcehc1kWF9-zv-N695RIoZ2uiZn0c_vU2YySjkiEGb9AfSDPZnGHjWXKCBCEERq5DgSJGKOclktQX4BLh_`
  - `https://lh3.googleusercontent.com/aida-public/AB6AXuDs3QdgzTkbh500EY3VV6-JFrLtBB1NT3H_RvVn6gB5trVVm-uDFxVeBVPuMv_YQZcT2Ns4rgvOP3ewU2A9tPSOHAABb2EHVYMKaEkKkXrCnWIW5Lf-2sKPGX_rGEvgKmfUGTmIO-9gEuvJVJm96xF435aU8PVSjKV5BuaSqd58Itb44fZuc-MvYc3w0lv0KgfoZZzWMh8ag4oRJ0jSOBlApzOZ8ZddJEb-xdczKO6B`

---

## 5. Estructura de Archivos del Espacio de Trabajo
```text
PRD_Landing/
├── assets/
│   └── stitch/
│       ├── Detalle_de_Platillo_Restaurante_Arocena_code.html
│       ├── Detalle_de_Platillo_Restaurante_Arocena_screenshot.png
│       ├── Exposiciones_y_Menús_Restaurante_Arocena_code.html
│       ├── Exposiciones_y_Menús_Restaurante_Arocena_screenshot.png
│       ├── Inicio_Museo_Arocena_Restaurante_code.html
│       ├── Inicio_Museo_Arocena_Restaurante_screenshot.png
│       ├── Menú_Actual_Restaurante_Arocena_code.html
│       └── Menú_Actual_Restaurante_Arocena_screenshot.png
├── .gitignore
├── bitacora_proyecto.md             <-- Este documento
├── index.html                       <-- Landing page conectada a Supabase
├── iniciar_servidor.bat             <-- Servidor local de soporte
├── PRD – Landing Page.pdf           <-- Documento de requerimientos original
├── README.md                        <-- Documentación para GitHub
├── reservas.json                    <-- Base de datos local de respaldo
├── servidor.ps1                     <-- Script backend local
├── stitch_project_data.json         <-- Metadatos del proyecto en Stitch
├── Stitch Instructions.md.txt       <-- Instrucciones de exportación de Stitch
├── www.adidas.mx_....md             <-- Archivo de referencia visual (Adidas)
└── www.nicanor.mx_....md            <-- Archivo de contexto gastronómico (Nicanor)
```

---

## 6. Próximos Pasos Sugeridos
1. **Reemplazo de Imágenes en la Landing:** ✅ Completado. Se integraron el isotipo/sello oficial de Arocena, el hero de la galería virreinal, las tarjetas de valor conceptual y los platillos emblemáticos del menú extraídos directamente de Google Stitch.
2. **Actualización de Vercel & GitHub:** Para sincronizar los cambios más recientes con el repositorio de GitHub y el despliegue en Vercel, ejecutar el commit y push correspondientes una vez que el CLI de Git o Vercel esté disponible en la sesión de terminal.
