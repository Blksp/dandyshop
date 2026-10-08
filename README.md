# 👑 DANDY $HOP — Documentación Técnica, Arquitectura & Manual de Operación Completo

> **Versión del Sistema:** 5.5.0 Master Enterprise Edition  
> **Fecha de Actualización:** 07 de Octubre de 2026  
> **Paleta de Identidad Visual:** *Dark Obsidian Glassmorphism (#0b090e) & 24K Liquid Gold Foil (#d4af37, #ffd700, #b38728)*  
> **Infraestructura:** Single Page Application (SPA) Ultraligera, Vanilla JS modular (sin frameworks pesados), Autenticación VIP con SHA-256 Hashing, Firebase Realtime Database con fallback bidireccional en LocalStorage, WebP Image Compression Engine y Canvas Rendering.

---

## 📑 Índice General

1. [Visión General & Filosofía del Negocio](#1-visión-general--filosofía-del-negocio)
2. [Arquitectura de los 6 Módulos Maestros (Category Hubs)](#2-arquitectura-de-los-6-módulos-maestros-category-hubs)
3. [Módulo de Autenticación VIP & Validación Estricta de Clientes](#3-módulo-de-autenticación-vip--validación-estricta-de-clientes)
4. [Módulo de Gestión Bancaria Oficial & Pagos Directos](#4-módulo-de-gestión-bancaria-oficial--pagos-directos)
5. [Motores Interactivos & Suite de Crecimiento con IA](#5-motores-interactivos--suite-de-crecimiento-con-ia)
6. [Panel de Control Administrativo (18 Módulos de Gestión)](#6-panel-de-control-administrativo-18-módulos-de-gestión)
7. [Esquema de Datos Firebase Realtime & LocalStorage](#7-esquema-de-datos-firebase-realtime--localstorage)

---

## 1. Visión General & Filosofía del Negocio

**DANDY $HOP** está concebida como una plataforma de comercio digital y físico de alta gama, especializada en tres pilares de alta demanda en México y Latinoamérica:

1. **Cuentas y Suscripciones Digitales Premium:** Streaming 4K UHD (*Netflix, Disney+, Max HBO, Spotify, YouTube Premium*), combos multi-plataforma y licencias con garantía y entrega express de **3 a 7 minutos**.
2. **Perfumería Árabe 100% Original Sellada (100ml / 105ml):** Fragancias de lujo en caja original con celofán de fábrica (*Lattafa, Armaf, Rasasi, Bharara, Al Haramain*) con herramientas interactivas de comparación olfativa.
3. **Rifas Oficiales & Dinámicas de Lealtad:** Sorteos en tiempo real con cuadrículas interactivas de boletos, barra de progreso de cierre y máquina Jackpot gamificada.

---

## 2. Arquitectura de los 6 Módulos Maestros (Category Hubs)

Toda la tienda está organizada en **6 Módulos Maestros Plegables e Interconectados** mediante la barra fija superior `#categoryHub`:

```
┌────────────────────────────────────────────────────────────────────────┐
│                   DANDY $HOP · BARRA DE NAVEGACIÓN MAESTRA              │
│  [01 Streaming] [02 Perfumería] [03 Rifas] [04 Stock] [05 Extras] [06 Ayuda]
└────────────────────────────────────────────────────────────────────────┘
```

---

## 3. Módulo de Autenticación VIP & Validación Estricta de Clientes

### A) Flujo de Registro (`#authRegisterForm`)
- **Validaciones:**
  - **Correo Electrónico:** Validación estricta RFC regex (`/^[^\s@]+@[^\s@]+\.[^\s@]{2,}$/`).
  - **WhatsApp / Teléfono:** Validador numérico de 10 dígitos.
  - **Contraseña:** Mínimo 6 caracteres con confirmación idéntica y botón de visualización (👁️).
  - **Unicidad:** Verifica en Firebase (`usuarios_clientes/`) y `localStorage` que el correo no esté duplicado.
- **Bono de Bienvenida:** Asigna automáticamente **$25 MXN (25 Puntos Oro)** en la cuenta del cliente para aplicar descuentos en su primer pedido.
- **Seguridad:** Hashing seguro SHA-256 (`crypto.subtle`) antes de persistir los datos.

### B) Flujo de Inicio de Sesión (`#authLoginForm`)
- Compara el correo y la contraseña cifrada contra la base de datos guardada.
- **Manejo de Errores Específicos:** Notifica si el correo no existe o si la contraseña es incorrecta.
- **Sesión Activa:** Al iniciar sesión, la cabecera muestra el nombre del cliente (`👤 Carlos M.`) y actualiza su saldo de Puntos Oro y garantías activas.

---

## 4. Módulo de Gestión Bancaria Oficial & Pagos Directos

Ubicado en el Panel Administrativo (`#adminCuentaBancaria`):
- **Campos Configurables:**
  - Banco Receptor (*ej. BBVA México, STP, Nu, Mercado Pago*)
  - Nombre del Titular (*ej. Emilio Bautista Nava*)
  - CLABE Interbancaria (18 dígitos)
  - Número de Tarjeta / Depósito OXXO (16 dígitos)
  - Link de Cobro Directo (*Mercado Pago / Stripe*)
- **Efecto Inmediato:** Todos los botones de copiado 1-tap de la tienda, el código QR SPEI/CoDi y las notas de pago del carrito se sincronizan en tiempo real para que el dinero de las transferencias llegue directamente a tu cuenta bancaria.

---

## 5. Motores Interactivos & Suite de Crecimiento con IA

| # | Módulo / Característica | Propósito Estratégico | Estado |
| :--- | :--- | :--- | :--- |
| **01** | **🤖 DANDY AI Sommelier & Asesor en Lenguaje Natural** | Motor de IA que analiza solicitudes libres y recomienda el perfume o streaming exacto con score de coincidencia. | ✅ Activo |
| **02** | **🛡️ Póliza de Garantía Holográfica 24K** | Certificado interactivo con efecto tornasol dorado y folio de seguridad `#GRT-VIP-XXXXX`. | ✅ Activo |
| **03** | **👤 Portal de Clientes VIP & Validación SHA-256** | Sistema de login y registro con validador estricto de correo y contraseña. | ✅ Activo |
| **04** | **💳 Módulo de Conexión Bancaria Directa** | Sincronización de CLABE, titular y cuenta bancaria oficial en toda la tienda. | ✅ Activo |
| **05** | **⚡ Menú Flotante Speed Dial WhatsApp** | 4 accesos rápidos al tocar el ícono flotante de WhatsApp. | ✅ Activo |
| **06** | **📊 Calculadora de Ahorro Anual de Streaming** | Muestra el ahorro masivo anual (hasta 71%) para cerrar combos de múltiples meses. | ✅ Activo |
| **07** | **🔥 Barra de Progreso en Vivo en Rifas** | Genera urgencia psicológica mostrando el % de boletos vendidos y cuántos faltan para el sorteo. | ✅ Activo |
| **08** | **🎖️ DANDY Puntos Oro (1 Pt por cada $100 MXN)** | Otorga $25 MXN (25 Pts) de bienvenida y acumula 1 Punto Oro por cada $100 pesos de compra (canjeable directamente en el carrito), canjeable directamente en el carrito. | ✅ Activo |
| **09** | **🔍 Buscador Spotlight (`Ctrl+K` / `⌘K`)** | Permite encontrar cualquier producto o servicio en menos de 1 segundo con navegación por teclado. | ✅ Activo |
| **10** | **🧾 Recibo Térmico Digital Imprimible** | Genera un comprobante formal tipo ticket de caja con folio `#DND-XXXX` y código de barras. | ✅ Activo |

---

## 6. Panel de Control Administrativo (18 Módulos de Gestión)

1. **`adminAdd`:** Agregar servicio o producto digital.
2. **`adminProductInfo`:** Editor de especificaciones técnicas.
3. **`adminCatalogAvailability`:** Disponibilidad en vivo (*Disponible / Agotado*).
4. **`adminStockFisico`:** CRUD completo de productos físicos con fotos WebP y existencias.
5. **`adminPerfumeria`:** Inventario de fragancias selladas 100ml.
6. **`adminCats`:** Gestión de categorías.
7. **`adminCuentas`:** Panel de delivery de credenciales para WhatsApp.
8. **`adminDescuentos`:** Creación de cupones con caducidad.
9. **`adminRenov`:** Control de fechas de vencimiento de clientes.
10. **`adminPedidos`:** Seguimiento de folios.
11. **`adminJackpotClaims`:** Validación de premios del Jackpot.
12. **`adminRaffles`:** Administración de rifas con eliminación permanente.
13. **`adminBrandKit`:** Descarga de recursos y flyer de calle.
14. **`adminCombos`:** Ajuste de precios de combos.
15. **`adminResenas`:** Moderación de testimonios y fotos de entrega.
16. **`adminAnuncio`:** Banner de avisos y modo mantenimiento.
17. **`adminCuentaBancaria`:** Configuración de CLABE, titular y cuenta bancaria oficial.
18. **`adminUsuariosClientes`:** Visualizador de clientes registrados, correos validados y saldo de Puntos Oro.

---

## 7. Esquema de Datos Firebase Realtime & LocalStorage

```json
{
  "precios": {
    "_config_bancaria": {
      "bank": "BBVA México",
      "titular": "Emilio Bautista Nava",
      "clabe": "646180401620352011",
      "card": "4152 3138 2940 1928"
    },
    "usuarios_clientes": {
      "carlos_gmail_com": {
        "name": "Carlos Mendoza",
        "email": "carlos@gmail.com",
        "phone": "5512345678",
        "passwordHash": "a665a45920422f9d417e4867efdc4fb8a04a1f3fff1fa07e998e86f7f7a27ae3",
        "points": 25,
        "createdAt": 1728300000000
      }
    }
  }
}
```

---

*Documento técnico oficial generado y certificado para DANDY $HOP.*


### 👥 Módulo de Administración de Clientes & Saldo SPEI (`#adminUsuariosClientes`)
1. **Buscador Reactivo:** Filtra en tiempo real por nombre de cliente, correo o teléfono.
2. **Estadísticas Globales:** Contador total de clientes registrados y suma de Puntos Oro en circulación.
3. **Módulo de Acreditación y Ajuste de Saldo en Vivo (`#adminBalanceManagerBox`):**
   - **Píldoras de Recarga SPEI:** `+$100 Pts`, `+$250 Pts`, `+$550 Pts` y `+$1,150 Pts`.
   - **Operaciones Disponibles:** Sumar/Acreditar, Restar/Descontar o Establecer Saldo Exacto.
   - **Sincronización:** Persiste instantáneamente en Firebase Realtime Database (`usuarios_clientes/<userKey>/points`) y actualiza la billetera del usuario en tiempo real.
   - **Notificador WhatsApp:** Botón `[ 📲 Notificar por WhatsApp ]` para enviar un comprobante formal con formato oficial al cliente.

### 👑 Paleta Blanco Perla & Oro Líquido 24K
- **Estética:** Fondo Blanco Perla Porcelana (`#fbf9f4`), tarjetas en blanco puro (`#ffffff`) con bordes en oro cepillado 24K (`#c59b27`), tipografía de ultra-alto contraste en carbón obsidiana (`#18130c`).
- **Botones Profesionales:** Botones dorados de alta visibilidad con texto oscuro nítido y efecto resplandor 24K.
- **Carrito Universal:** Carrito optimizado con persistencia local, selector de cantidades, barra de regalo a $3,000 MXN, deducción de Puntos Oro y checkout directo por WhatsApp.

### 👑 Estética de Lujo Internacional: Haute Luxe 24K Liquid Gold & Deep Obsidian
- **Inspiración:** Diseño inspirado en la alta relojería y joyería suiza (*Rolex Cosmograph Daytona Gold, Cartier Haute Horlogerie y Harrods Knightsbridge*).
- **Atmósfera:** Fondo Deep Cosmic Obsidian (`#08070b`) con resplandor radial en champán líquido 24K (`#d4af37`), tarjetas obsidian glass con bisel y marco dorado pulido.
- **Botones de Impacto:** Gradiente de Oro 24K Líquido (`#d4af37` a `#fff0ad`) con texto en negro obsidiana profundo (`#0b0804`), máxima legibilidad y respuesta táctil inmediata.

### 🛒 Botones de Carrito Universales
- **Cobertura 100%:** Cada producto, servicio de streaming, recarga, paquete, membresía, perfume sellado, artículo de stock físico y gadget cuenta con un botón directo `[ 🛒+ Carrito ]` / `[ 🛒+ ]`.
- **Integración:** Agrega el producto con su precio oficial inmediatamente al carrito universal, activando la animación de rebote en el contador y la notificación Toast.

### 🎰 Ruleta de la Fortuna Conectada a Sesiones VIP (`#luckyWheelModal`)
1. **Regla de Autenticación Estricta:** Solo los usuarios registrados e identificados pueden girar la ruleta y reclamar premios. Si un usuario no ha iniciado sesión, se muestra el aviso VIP y el botón directo de acceso/registro (+25 Pts gratis).
2. **Límite Diario Anti-Abuso:** Cada cliente VIP tiene 1 giro gratis cada 24 horas sincronizado con Firebase Database (`usuarios_clientes/<userKey>/lastWheelSpin`).
3. **Acreditación Automática de Saldo:** Los premios en Puntos Oro (`+$50 Pts` o `+$25 Pts`) se acreditan al instante a la cuenta oficial del cliente en la base de datos y se reflejan en su billetera en vivo.

### 🔘 Calibración Multiplataforma de Botones & Premios de Ruleta (5 y 10 Pts)
- **Premios Ruleta Sostenibles:** Premios diarios en Puntos Oro configurados a `+$5 Pts Oro VIP` y `+$10 Pts Oro VIP` ($5 y $10 MXN), acreditados directamente a la cuenta del usuario en Firebase.
- **Encuadre Multiplataforma Pixel-Perfect:** Todos los botones de la tienda, tablas de streaming, tarjetas, píldoras de saldo y acciones administrativas cuentan con `box-sizing: border-box`, `touch-action: manipulation`, `-webkit-appearance: none` y grillas CSS responsivas calibradas para Windows, iOS (Safari WebKit), Android y Linux.

### 📐 Arquitectura Simétrica, Balance Áureo & Haute Luxe
- **Geometría Visual:** Ancho maestro centrado a 1120px con márgenes áureos equilibrados en móvil y escritorio.
- **Grillas Simétricas:** Tarjetas de producto con altura uniforme (`height: 100%`) y botones de acción alineados en la base.
- **Armonía Departamental:** Los 3 Pilares Maestros, el sub-hub dual de perfumería y el jackpot tragamonedas cuentan con marcos dorados 24K, bordes redondeados consistentes (18px) y micro-textura de alta gama.

### 🚀 Suite Estratégica Integral (Sin Saturación de Pantalla)
1. **💬 Generador de Plantillas WhatsApp 1 Clic (`#adminMensajeriaWhatsApp`):** Plantillas administrativas para renovaciones de streaming, guías de envío y recordatorios de saldo.
2. **🎁 Programa de Referidos VIP:** Código personalizado por usuario (`DANDY-XXXX`) con recompensa de +$15 Pts ($15 MXN) por cada amigo que se registre.
3. **📊 Dashboard de Métricas & Exportador CSV (`#adminDashboardMetricas`):** Descarga de la base de datos de clientes con 1 toque en formato `.csv` para campañas.
4. **⚡ Express Checkout:** Botón directo en productos para compras inmediatas sin pasar por el carrito.
5. **📱 Botón PWA Discreto:** Acceso rápido en el encabezado para instalar la app web oficial sin banners invasivos.

### 🛡️ Módulos Complementarios de Conversión y Confianza
1. **🛡️ Portal Público de Verificación de Garantías (`#dandyWarrantyPortal`):** Verificador con número de WhatsApp o folio que despliega el Certificado Holográfico 24K oficial de blindaje de cuentas.
2. **✈️ Cotizador Inteligente de Vuelos y Parques:** Formulario interactivo en `#vuelos` para cotizaciones inmediatas de Aeroméxico, Volaris, Viva, Xcaret y Six Flags por WhatsApp.
3. **🎟️ Compra Cruzada de Boletos de Rifa:** Integración directa con el Carrito Universal para pagar boletos de sorteo en el mismo SPEI con perfumes o streaming.
4. **📋 Historial y Resumen en Perfil VIP (`#myOrdersModal`):** Consulta del estado de cuenta, pedidos recientes y vigencias de garantías activas.

### 🔍 Motor SERP de Comparación de Precios de Mercado en Vivo
1. **📊 Comparador Público SERP (`#serpPriceCompareModal`):** Disponible en el Pilar 02 de Perfumería. Compara en tiempo real los precios de DANDY $HOP vs Liverpool, Palacio de Hierro y Amazon, mostrando el ahorro neto del cliente (-35% a -48% OFF) en frascos 100% sellados.
2. **🎛️ Monitor SERP Administrativo (`#adminSerpPriceChecker`):** Permite al administrador consultar cualquier fragancia, validar márgenes de ganancia y guardar su SERP API Key sincronizada en Firebase Realtime Database (`precios/_config_serp`).

### 📊 Validación Real de Precios SERP en México (Palacio de Hierro / Liverpool / Amazon)
- **Precios Reales Verificados:**
  * **Lattafa Khamrah 100ml:** $1,150 MXN en DANDY vs $1,890 en Liverpool vs $6,500 Kilian Angels' Share (Ahorro: 39% a 82%).
  * **Lattafa Asad 100ml:** $950 MXN en DANDY vs $1,650 en Liverpool vs $6,260 Dior Sauvage Elixir (Ahorro: 42% a 84%).
  * **Club de Nuit Intense 105ml:** $1,050 MXN en DANDY vs $1,790 en Liverpool vs $8,900 Creed Aventus (Ahorro: 41% a 88%).
  * **Rasasi Hawas 100ml:** $1,350 MXN en DANDY vs $2,200 en Liverpool (Ahorro: 39%).
  * **Bharara King 100ml:** $1,450 MXN en DANDY vs $2,400 en Liverpool vs $7,200 Erba Pura (Ahorro: 40% a 80%).
- **Buscador en Vivo:** Permite buscar cualquier fragancia en tiempo real mediante SERP API y Google Shopping México.

### 🌐 Motor SERP Universal Multi-Categoría (Streaming, Perfumería, Membresías & Gadgets)
- **Cobertura Total de Catálogo:**
  1. **📺 Streaming & Combos:** Comparativa oficial de Netflix 4K ($60 vs $299), Disney+ ($60 vs $299), Max ($50 vs $249), Spotify ($45 vs $129), Combos Dúo y Trío VIP (-80% a -83% de ahorro).
  2. **🧴 Perfumería Árabe & Diseñador:** Comparativa en tiendas departamentales (Liverpool, Palacio de Hierro, Sephora México y Amazon) con ahorro de hasta 45% en frascos sellados y hasta 88% respecto a fragancias nicho originales.
  3. **⚡ Membresías & IA:** SmartFit Plan Black ($350 vs $699), ChatGPT Pro ($150 vs $450), Canva Pro ($50 vs $149), Game Pass Ultimate ($280 vs $399).
  4. **📦 Gadgets & Stock Físico:** Smartwatch Ultra Pro ($550 vs $1,290), Audífonos Wireless Pro ($450 vs $990).

### 🌸 Limpieza y Gestión Dinámica de Perfumería desde 0
- **Catálogo Limpio:** Se eliminaron las tarjetas de muestra para permitir la carga oficial desde 0.
- **Renderizado Dinámico:** Los perfumes registrados en el panel administrativo (`#adminPerfumeria`) se sincronizan en tiempo real con Firebase Realtime Database (`inventario_perfumes`) y se muestran de inmediato en la tienda pública con foto, precio, notas olfativas, inspiración y botones `[ 🛒+ ]`.
- **Sub-Hub 2 (Nicho & Diseñador):** Formulario cotizador directo de encargos de alta gama con 30% OFF por WhatsApp.

### 🚀 Motor SERP API Live Real con Desglose de Tiendas (Liverpool / Amazon / Palacio / ML)
- **Ejecución Live:** Realiza peticiones directas y mediante failover proxy a SerpAPI / Google Shopping México con tu API Key cargada.
- **Desglose de Tiendas Reales:** Muestra los nombres reales de las tiendas encontradas en México (*🏬 Liverpool, 🏬 Palacio de Hierro, 📦 Amazon México, 🟡 Mercado Libre*), sus precios exactos y el promedio de mercado.
- **Cálculo de Ahorro Neto:** Compara el promedio real del mercado mexicano contra el precio VIP de DANDY $HOP, calculando el ahorro exacto en pesos y porcentaje.
- **Gestión de API Key:** Permite guardar y sincronizar la clave de API tanto desde el modal público como desde el panel de administración (`#adminSerpPriceChecker`).

### 👑 Sección Unificada de Perfumería con SERP Live 3-Store Benchmark
- **Unificación Total:** Se integró la sección de perfumería en un solo módulo de alto impacto dentro del Pilar 02.
- **Comparación Directa 3 Tiendas:** Compara en tiempo real los precios en stock de DANDY $HOP contra **Liverpool México, Amazon México y Mercado Libre** utilizando tu API Key cargada de SerpAPI.
- **Buscador en Vivo:** Permite buscar y cotizar cualquier fragancia en vivo con desglose automático de ahorro, botón de carrito y WhatsApp.

---

## 📌 CHECKPOINT MAESTRO: CATÁLOGO PROVEEDOR 99 PERFUMES (+25% MARGEN)
- **Fecha:** 2026-10-07
- **Archivo Estable Checkpoint:** `/home/user/index_checkpoint_perfumes_99_verified.html`
- **JSON de Inventario Exportado:** `/home/user/imported_perfumes.json` (99 SKUs procesados)
- **Regla de Margen Activa:** `+25%` estricto sobre costo real de proveedor.
- **Herramientas Activas:**
  - `import_ml_vendor.py` (CLI Scraper & Importer de ML con soporte para URLs de catálogo y artículos).
  - `#adminMlScraperImporter` (Editor interactivo en vivo dentro de la web).
  - Soporte de marcas: *French Avenue, Armaf, Lattafa Pride, Niche Emarati, Maison Alhambra, Zimaya, Rasasi, Afnan, Dumont Paris, Emper, Flavia, Benetton, etc.*

---

## 19. INTEGRACIÓN DE STOCK FÍSICO REAL & ENRIQUECIMIENTO TOTAL DE PERFUMERÍA

### 19.1. Catálogo de Fragancias con Datos Reales
Cada fragancia del catálogo cuenta ahora con sus metadatos perfumísticos oficiales:
- **Notas Olfativas Reales:** Salida, corazón y fondo desglosadas (ej. Coco caribeño, bergamota marina, caña de azúcar, lima tahití en *Armaf Island Breeze*).
- **Inspiración / Clon Nicho y Diseñador:** Clon comprobado (ej. *Creed Virgin Island Water*, *Roja Elysium*, *Kilian Angels' Share*, *Dior Sauvage Elixir*, *Parfums de Marly Althaïr*, *Bvlgari Tygar*, etc.).
- **Familia Olfativa y Género:** Clasificación exacta (Cítrica Marina Gourmand, Oriental Amaderada, etc.).
- **Presentación:** Frascos sellados de 100ml / 105ml (cero decants) con margen estricto del **+25%**.

### 19.2. Doble Disponibilidad: Stock Inmediato vs. Bajo Pedido
- **⚡ En Stock Listo (Entrega Inmediata / Hoy):** Destacado visual con halo dorado-verde y botón directo para coordinar entrega hoy.
- **📦 Bajo Pedido (Envío Nacional):** Flujo con plantilla de WhatsApp pre-llenada para captura de dirección de envío completa.
- **Píldoras de Filtro Dinámicas:** Permiten alternar entre *Todos los Perfumes*, *En Stock Inmediato*, *Bajo Pedido* y por Casa de Perfumería (*Armaf*, *French Avenue*, *Lattafa*, *Maison Alhambra*, *Fragrance World*, *Zimaya & Afnan*, *Diseñador / Nicho*).


---

## 20. CATÁLOGO COMPLETO CON IMÁGENES REALES SCRAPEADAS & OPTIMIZADAS (103 SKUs)

### 20.1. Extracción y Optimización de Imágenes
- **103 Fotografías Reales de Producto:** Scrapeadas, limpiadas y optimizadas en formato **WebP ligero (82% de calidad, max 400x400 px, ~15-25 KB por imagen)**.
- **Visualizador Modal de Zoom 24K:** Al pulsar sobre cualquier tarjeta de perfume o producto físico, se despliega una vista en alta resolución con detalles de la botella original sellada y notas olfativas.
- **Ruta de Recursos Locales y Respaldo:** Sincronizado en `/home/user/images/` y `/home/user/uploads/images/` con fallback de carga reactiva.


---

## 21. UNIFICACIÓN TOTAL DEL CATÁLOGO BAJO PEDIDO CON DISPONIBILIDAD INMEDIATA (103 SKUs)

### 21.1. Inclusión Universal en Modalidad Bajo Pedido
- **103 Fragancias Disponibles Bajo Pedido:** Todas las fragancias del inventario (incluyendo piezas emblemáticas en mano como *Armaf Island Breeze, French Avenue Ripple, Lattafa Khamrah, Asad, Club de Nuit Intense, Rasasi Hawas*, etc.) se muestran y gestionan dentro del catálogo maestro **Bajo Pedido con Envío Nacional**.
- **Distintivo Híbrido para Artículos en Mano:** Los artículos con unidades físicas listas muestran el badge `📦 Bajo Pedido · ⚡ En Stock Disponible`, permitiendo al cliente elegir entre despacho exprés el mismo día o envío regular.
- **Plantilla Oficial de WhatsApp Estandarizada:** Todas las compras bajo pedido canalizan al usuario al chat oficial de DANDY $HOP solicitando su dirección de envío completa (Calle, Número, Colonia, C.P., Ciudad, Estado, Referencias y Teléfono).


---

## 22. CONFIGURACIÓN BANCARIA OFICIAL DE TRANSFERENCIAS & SPEI

### 22.1. Datos de Cuenta Única Oficial
- **Institución Bancaria:** Openbank (Santander Digital / Openbank México)
- **CLABE Interbancaria (18 dígitos):** `646180401620352011`
- **Titular de la Cuenta:** Emilio Bautista Nava
- **Concepto de Pago Obligatorio:** `comida` o `viaticos`
- **Botones de Copiado 1-Click:** Accesibles en la sección pública `#transferencia`, modal de recarga de Wallet SPEI y Administrador.


---

## 23. UNIFICACIÓN COMPLETA DE PERFUMERÍA SIN DIVISIONES & ELIMINACIÓN DE STOCK FÍSICO DUPLICADO

### 23.1. Arquitectura de Módulo Único
- **Eliminación Total de la Sección Dividida de Stock Físico:** Se eliminó la sección redundante `#stock` y los artículos genéricos o inventados.
- **Catálogo Maestro Único y Continuo (`#fragancias`):** Integra el 100% del stock real (103 fragancias originales selladas con imágenes reales de producto, notas olfativas oficiales e inspiraciones de nicho).
- **Consolidación en Pilar 02:** El Gran Pilar 02 de la tienda alberga la experiencia completa de Perfumería con Comparador SERP en Vivo, Buscador Instantáneo, Píldoras de Marca, Simulador de Rendimiento y Rastreador Oficial de Guías (FedEx / DHL / Estafeta).
- **Flujo de Pago Unificado:** Transferencias canalizadas a **Openbank (CLABE 646180401620352011, Emilio Bautista Nava)** con concepto obligatorio `comida` o `viaticos`.


---

## 24. RELLENO UNIVERSAL DE TODOS LOS CAMPOS DEPENDIENTES DEL MÉTODO DE PAGO

### 24.1. Estandarización de Datos Bancarios en Todo el Sistema
Todos los flujos transaccionales y de consulta integran de forma nativa los datos oficiales:
- **Banco:** Openbank (Santander Digital / Openbank México)
- **CLABE (18 dígitos):** `646180401620352011`
- **Titular Oficial:** Emilio Bautista Nava
- **Concepto Obligatorio:** `comida` o `viaticos`

### 24.2. Módulos y Puntos de Contacto Actualizados:
1. **Carrito Universal & Checkout Express (`#dandyCartModal`):**
   - Incorpora la tarjeta visual de pago bancario SPEI con botones de copiado 1-click para CLABE y conceptos (`comida` / `viaticos`).
   - El mensaje generado para WhatsApp adjunta de forma automática el desglose completo del pedido y los datos de transferencia.
2. **Generador de Notas de Pedido / Recibos Digitales (`#receiptModal`):**
   - Incluye el bloque bancario oficial con Openbank, CLABE y concepto `comida o viaticos`.
3. **Modal de Recarga SPEI Wallet Puntos Oro (`#speiModal`):**
   - Muestra banco, titular, CLABE y concepto obligatorio con enlace directo de WhatsApp.
4. **Sección Pública de Transferencias (`#transferencia`):**
   - Tarjeta 24K con validación y botones 1-click.
5. **Preguntas Frecuentes (`#faq`) & Asistente IA Concierge:**
   - Respuestas automatizadas con los datos de Openbank y concepto `comida` o `viaticos`.
6. **Panel de Administración (`#adminCuentaBancaria`):**
   - Preconfigurado con Openbank y sincronizado con Firebase Realtime Database.

