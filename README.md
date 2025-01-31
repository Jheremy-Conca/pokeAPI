PokeAPI Vue 3 - Proyecto de Práctica
Este proyecto es una aplicación práctica desarrollada con el objetivo de mejorar mis habilidades en Vue 3 y JavaScript. La aplicación consume la PokeAPI para mostrar información detallada sobre Pokémon, sus características y habilidades, integrando Vue Router para la navegación entre vistas y Vue Pinia para la gestión del estado global.

🌐 Ver el proyecto en producción aquí

🚀 Funcionalidades
1. Listado de Pokémon:
La aplicación muestra una lista interactiva de Pokémon obtenida dinámicamente desde la API.
Los nombres de los Pokémon están enlazados a sus respectivas vistas individuales para ver más detalles.
2. Detalle de Pokémon:
Al seleccionar un Pokémon de la lista, se muestra una vista detallada con información como:
Nombre.
Imagen.
Altura.
Peso.
Habilidades.
Experiencia base.
Los usuarios pueden añadir Pokémon a su lista de favoritos.
Implementación de un botón de retroceso para regresar al listado de Pokémon.
3. Gestión de Favoritos con Pinia:
Implementación de Pinia para gestionar los Pokémon favoritos, permitiendo que los usuarios los guarden y accedan fácilmente desde cualquier vista.
4. Estilo y diseño responsivo:
La aplicación utiliza Bootstrap para ofrecer una interfaz moderna y profesional, adaptada a dispositivos móviles y escritorios.
El diseño incluye estilos personalizados con CSS para mejorar la visualización de las imágenes y las listas.
5. Navegación:
Se emplea Vue Router para gestionar la navegación entre las vistas y las rutas dinámicas de los Pokémon, asegurando una experiencia de usuario fluida.
🛠️ Herramientas y Tecnologías Utilizadas
Framework Frontend: Vue 3
Gestión del Estado: Pinia
Rutas: Vue Router
Estilo: Bootstrap, SCSS y CSS personalizado
Consumo de API: Axios
Despliegue: Netlify
API utilizada: PokeAPI
Iconos: Bootstrap Icons
📂 Estructura del Proyecto
plaintext
Copiar
Editar
src/
├── assets/                # Archivos estáticos (imágenes, iconos, etc.)
│   └── logo.png           # Logo de la aplicación
├── components/            # Componentes reutilizables de Vue
│   └── PokemonCard.vue    # Componente para mostrar la información básica de un Pokémon
├── views/                 # Vistas principales de la aplicación
│   └── Home.vue           # Vista que muestra la lista de Pokémon
│   └── PokemonDetail.vue # Vista que muestra los detalles de un Pokémon individual
├── router/                # Configuración de Vue Router
│   └── index.js           # Definición de rutas y navegación
├── store/                 # Gestión del estado con Pinia
│   └── favoritos.js       # Almacenamiento de Pokémon favoritos
├── App.vue                # Componente raíz principal de la aplicación
└── main.js                # Punto de entrada de la aplicación, inicialización de Vue
