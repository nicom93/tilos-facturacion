# Sistema de Facturación - Los Tilos Pizza

Sistema completo de facturación para pizzería con gestión de precios, pedidos e historial.

## Archivos del sistema

- `index.html` - Sistema principal de facturación y POS
- `precios.html` - Gestión de precios de productos
- `logotilos.png` - Logo de la empresa

## Configuración inicial

### 1. Configurar Firebase Security Rules

1. Ve a [Firebase Console](https://console.firebase.google.com/)
2. Selecciona tu proyecto "lostilos-67059"
3. Ve a "Firestore Database" > "Rules"
4. Reemplaza las reglas existentes con el contenido del archivo `firebase-rules.txt`
5. Haz clic en "Publish"

### 2. Inicializar precios

1. Abre `precios.html` en tu navegador
2. Haz clic en "Inicializar catálogo con precios en $0"
3. Modifica los precios según corresponda
4. Haz clic en "Guardar todos los cambios"

### 3. Usar el sistema de facturación

1. Abre `index.html` en tu navegador
2. Los precios se cargarán automáticamente desde Firebase
3. Configura los datos del comercio (se guardan localmente)
4. Agrega productos al carrito desde el catálogo
5. Imprime tickets o guarda pedidos

## Funcionalidades

### Sistema de Facturación (index.html)
- ✅ Catálogo completo de productos organizados por categorías
- ✅ Pizzas con tamaños (Grande, Mediana, Chica)
- ✅ Opción "mitad y mitad" para pizzas (solo GDE/MED)
- ✅ Cálculo automático de precios
- ✅ Generación de tickets imprimibles
- ✅ Guardado de pedidos en Firebase
- ✅ Historial diario de ventas
- ✅ Cierre de caja con resumen

### Gestión de Precios (precios.html)
- ✅ Interfaz para modificar precios de todos los productos
- ✅ Precios diferenciados por tamaño para pizzas
- ✅ Sincronización automática con el sistema de facturación
- ✅ Validación de errores

## Estructura de datos en Firebase

### Colección "prices"
- `pizzas` - Precios por variedad y tamaño
- `empanadas_faina` - Precios de empanadas y fainá
- `bebidas_sin_alcohol` - Precios de bebidas
- `cervezas` - Precios de cervezas
- `vinos` - Precios de vinos
- `postres` - Precios de postres
- `otros` - Otros productos

### Colección "orders"
- Pedidos individuales con items, totales y timestamps

### Colección "cajas"
- Control de cajas abiertas/cerradas por día

### Colección "daily"
- Resúmenes diarios de ventas y categorías

## Solución de problemas

### Error "Missing or insufficient permissions"
- Verifica que las reglas de Firebase estén configuradas correctamente
- Asegúrate de que el archivo `firebase-rules.txt` esté aplicado

### Los precios no se cargan
- Verifica la conexión a internet
- Revisa la consola del navegador para errores
- Asegúrate de que los precios estén inicializados en `precios.html`

### Los tickets no se imprimen
- Verifica que el navegador permita ventanas emergentes
- Usa Ctrl+P para imprimir manualmente si es necesario

## Notas importantes

- Los datos del comercio se guardan en localStorage del navegador
- Los pedidos y precios se sincronizan automáticamente con Firebase
- El sistema maneja correctamente el cierre de caja después de medianoche
- Todos los cálculos de precios son automáticos y precisos
