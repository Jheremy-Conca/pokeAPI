# PokeAPI Vue 3 - Proyecto de Práctica

Este proyecto es una práctica personal desarrollada para mejorar mis habilidades en **Vue 3** y **JavaScript**. La aplicación consume la [PokeAPI](https://pokeapi.co/) para mostrar información sobre Pokémon y sus características, utilizando Vue Router para la navegación entre vistas.

🌐 **[Ver el proyecto en producción aquí](https://pokea-api.netlify.app/)**

---

## 🚀 Funcionalidades

1. **Listado de Pokémon**:

   - Muestra una lista interactiva de Pokémon obtenida desde la API.
   - Los nombres de los Pokémon están enlazados a sus respectivas vistas individuales.

2. **Detalle de Pokémon**:

   - Al seleccionar un Pokémon, se muestra una vista con detalles como:
     - **Nombre**.
     - **Imagen**.
     - **Altura**.
     - **Peso**.
     - **Habilidades**.
     - **Experiencia base**.
   - Incluye navegación para regresar al listado.

3. **Estilo y diseño responsivo**:

   - La aplicación utiliza **Bootstrap** para una apariencia moderna y profesional.
   - Diseños optimizados con CSS personalizado para imágenes y listas.

4. **Navegación**:
   - Implementación de Vue Router para manejar rutas dinámicas basadas en los nombres de los Pokémon.

---

## 🛠️ Herramientas y Tecnologías Utilizadas

- **Framework Frontend**: Vue 3
- **Rutas**: Vue Router
- **Estilo**: Bootstrap y CSS personalizado
- **Consumo de API**: Axios
- **Despliegue**: Netlify
- **API utilizada**: [PokeAPI](https://pokeapi.co/)

---

## 📂 Estructura del Proyecto

src/
├── assets/ # Archivos estáticos, como imágenes y recursos adicionales.
│ └── logo.png # Ejemplo de archivo de imagen
├── components/ # Componentes reutilizables de Vue, como el Header o Footer
│ └── PokemonCard.vue # Componente para mostrar los detalles de un Pokémon
├── views/ # Vistas principales de la aplicación
│ └── Home.vue # Vista que muestra la lista de Pokémon
│ └── PokemonDetail.vue # Vista que muestra los detalles de un Pokémon individual
├── router/ # Configuración de las rutas con Vue Router
│ └── index.js # Definición de rutas para la aplicación
├── App.vue # Componente raíz principal de la aplicación
└── main.js # Punto de entrada de la aplicación, donde se inicializa Vue
