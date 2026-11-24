# Lunara React + Flux (prototipo académico)

## 1. Descripción del proyecto

Lunara React + Flux es un prototipo académico desarrollado con React, cuyo propósito es aplicar el patrón arquitectónico Flux para organizar la gestión del estado compartido de la aplicación.

Este proyecto constituye una versión independiente de Lunara. No modifica la aplicación original ni su infraestructura existente.

**Aplicación desplegada:** https://lunara-react-firebase.web.app/

**Repositorio:** https://github.com/pausierra2022-sudo/lunara-react-flux-firebase

## 2. Alcance implementado

El prototipo contempla las siguientes funcionalidades:

- Navegación entre Inicio, Catálogo y Carrito.
- Consulta de productos mediante la API REST existente: https://obtenerproductos-zyurdt3cka-uc.a.run.app.
- Búsqueda de productos por nombre.
- Filtros por categoría, talla y precio máximo.
- Agregar productos al carrito.
- Modificar cantidades y eliminar productos.
- Consultar subtotales y valor total de la selección.
- Vaciar el carrito.
- Persistencia de la información mediante `localStorage`.

La gestión del estado compartido del carrito se implementa mediante React Context y `useReducer`, siguiendo un flujo unidireccional inspirado en el patrón Flux.

Las acciones implementadas son:

- `ADD_TO_CART`
- `UPDATE_QUANTITY`
- `REMOVE_FROM_CART`
- `CLEAR_CART`

## 3. Tecnologías utilizadas

- **React 18:** construcción de la interfaz y sus componentes.
- **JavaScript:** implementación de la lógica de la aplicación.
- **React Router DOM:** navegación entre las vistas.
- **Context API y useReducer:** gestión centralizada del estado del carrito.
- **Vite:** herramientas de desarrollo y compilación.
- **CSS:** presentación y estilos de la interfaz.
- **Firebase Hosting:** despliegue del prototipo.
- **Cloud Functions y Firestore:** infraestructura existente que soporta la consulta de productos mediante la API REST.

## 4. Requisitos previos

- Node.js 18 o superior.
- npm.
- Visual Studio Code u otro editor de código.

## 5. Instalación y ejecución local

1. Clonar el repositorio o descargar el proyecto.
2. Abrir la carpeta `lunara-react-firebase` en Visual Studio Code.
3. Abrir una terminal en la carpeta del proyecto.
4. Instalar las dependencias:

```bash
npm install
```

5. Iniciar el servidor de desarrollo:

```bash
npm run dev
```

6. Abrir en el navegador la dirección local indicada por Vite, normalmente:

`http://localhost:5173`

Para generar la versión de producción:

```bash
npm run build
```

Para verificar localmente la compilación:

```bash
npm run preview
```

## 6. Estructura del proyecto

```text
lunara-react-firebase/
├── public/
│   └── img/
│       └── productos/
├── src/
│   ├── components/
│   │   ├── Navbar.jsx
│   │   └── ProductCard.jsx
│   ├── context/
│   │   └── CartContext.jsx
│   ├── reducers/
│   │   └── cartReducer.js
│   ├── services/
│   │   └── productService.js
│   ├── views/
│   │   ├── Cart.jsx
│   │   ├── Catalog.jsx
│   │   └── Home.jsx
│   ├── App.jsx
│   ├── main.jsx
│   └── styles.css
├── index.html
├── package.json
├── package-lock.json
├── firebase.json
└── vite.config.js
```

## 7. Consideraciones y limitaciones

- El prototipo no implementa autenticación real, pagos electrónicos, registro de compras, logística ni administración de productos.
- El carrito permite simular la selección de productos, pero no realiza transacciones comerciales.
- La consulta de productos depende de la disponibilidad del API REST existente y de su configuración CORS.
- No se modifica el backend ni la base de datos desde este proyecto.
- La función `dispatch` utilizada corresponde a la proporcionada por `useReducer`; no se implementa un Dispatcher independiente.
- React Context y `useReducer` administran el estado del carrito durante la ejecución, mientras que `localStorage` permite conservar la selección entre recargas.

## 8. Pruebas funcionales

Se realizaron pruebas manuales para verificar las principales funcionalidades:

1. Consultar el catálogo de productos.
2. Buscar productos por nombre y aplicar filtros.
3. Agregar productos al carrito y verificar el contador.
4. Agregar nuevamente un producto y comprobar el incremento de cantidad.
5. Modificar cantidades y eliminar productos.
6. Verificar el cálculo de subtotales y total.
7. Recargar la aplicación y comprobar la persistencia del carrito.
8. Vaciar el carrito y verificar que el contador vuelve a cero.

Las pruebas realizadas durante la validación del prototipo obtuvieron resultados satisfactorios.