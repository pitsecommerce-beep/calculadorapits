# 📊 Dashboard Financiero · Marketplaces MX

Dashboard de análisis financiero para vendedores en Amazon México y Mercado Libre. Calcula indicadores financieros reales cruzando los reportes de cada plataforma con tu lista de precios.

## 🚀 Deploy en GitHub Pages

1. **Fork / clona** este repositorio
2. Ve a **Settings > Pages**
3. Selecciona **Branch: main** → carpeta **/ (root)**
4. El sitio estará disponible en `https://TU-USUARIO.github.io/REPO-NAME`

El archivo `index.html` es completamente auto-contenido (sin build step).

---

## 📁 Archivos que acepta el dashboard

| Archivo | Formato | Descripción |
|---|---|---|
| **Lista de precios** | `.xlsx` | SKU, descripción, precio sin IVA, precio con IVA |
| **Reporte Mercado Libre** | `.xlsx` | Reporte oficial de ventas ML/Mercado Shops |
| **Reporte Amazon** | `.csv` | "Reporte de aspectos económicos del SKU" |

> 🔒 **Privacidad total**: Los archivos se procesan directamente en tu navegador. Ningún dato se envía a ningún servidor.

---

## ⚖️ Supuestos Fiscales (México 2026)

### Ley de Ingresos de la Federación 2026
- **ISR**: 2.5% retenido por plataformas sobre ingresos brutos (personas físicas y morales con RFC)
- **IVA**: 8% retenido (50% del IVA 16%) para personas físicas con RFC
- Las retenciones son **acreditables** en tus pagos provisionales mensuales

### Costo de Mercancía (COGS)
- Se usa el **precio sin IVA** de tu lista de precios
- Correcto para contribuyentes que acreditan IVA de sus compras (proveedores que facturan)

### Mercado Libre
- Los "Cargos por venta e impuestos" del reporte ya incluyen comisión + IVA de la comisión
- Estados válidos como venta: Entregado, Etiqueta impresa/lista, En camino, Paquetes
- Estados excluidos: Devoluciones
- Estados pendientes: Mediaciones y reclamos (se alertan pero no se cuentan)

### Amazon México
- La "Tarifa por referencia" varía entre 8% y 15% según categoría
- El reporte SKU económico ya muestra los "Ingresos netos" después de tarifas

---

## 📈 Qué muestra el dashboard

### General
- Ingresos brutos totales (ML + Amazon)
- Neto recibido de plataformas
- Utilidad bruta y margen
- Utilidad operativa (EBIT)
- COGS, cargos de plataformas, retenciones ISR

### Por canal (ML / Amazon)
- Desglose por SKU con ingresos, comisiones, COGS y margen
- Alertas de devoluciones, mediaciones y reclamos

### Estado de Resultados Dinámico
- Agrega costos fijos/variables en tiempo real
- Calcula automáticamente el break-even en unidades
- Todos los indicadores se actualizan al instante

### Exportación
- Descarga Excel con: Estado de Resultados, SKUs ML, SKUs Amazon, Indicadores

---

## 🛠 Stack técnico

- **React 18** (via CDN)
- **Recharts** para visualizaciones
- **SheetJS (XLSX)** para leer/escribir archivos Excel y CSV
- **Babel Standalone** para JSX en el navegador
- Sin build step — un solo archivo `index.html`

---

## ⚠️ Disclaimer

Este dashboard es una herramienta de análisis de gestión. Los cálculos fiscales son estimaciones basadas en la legislación vigente. **Consulta a tu contador** para decisiones fiscales y declaraciones oficiales.
