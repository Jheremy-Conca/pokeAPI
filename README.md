# **PokeAPI Vue 3 - Proyecto de Práctica**

Este proyecto es una aplicación práctica desarrollada con el objetivo de mejorar mis habilidades en **Vue 3** y **JavaScript**. La aplicación consume la [PokeAPI](https://pokeapi.co/) para mostrar información detallada sobre Pokémon, sus características y habilidades, integrando Vue Router para la navegación entre vistas y Vue Pinia para la gestión del estado global.

🌐 **[Ver el proyecto en producción aquí](https://poke-api-pinia.netlify.app/favoritos)**

---

## 🚀 **Funcionalidades**

### 1. **Listado de Pokémon**:
- La aplicación muestra una lista interactiva de Pokémon obtenida dinámicamente desde la API.
- Los nombres de los Pokémon están enlazados a sus respectivas vistas individuales para ver más detalles.

### 2. **Detalle de Pokémon**:
- Al seleccionar un Pokémon de la lista, se muestra una vista detallada con información como:
  - **Nombre**.
  - **Imagen**.
  - **Altura**.
  - **Peso**.
  - **Habilidades**.
  - **Experiencia base**.
- Los usuarios pueden añadir Pokémon a su lista de favoritos.
- Implementación de un botón de retroceso para regresar al listado de Pokémon.

### 3. **Gestión de Favoritos con Pinia**:
- Implementación de **Pinia** para gestionar los Pokémon favoritos, permitiendo que los usuarios los guarden y accedan fácilmente desde cualquier vista.

### 4. **Estilo y diseño responsivo**:
- La aplicación utiliza **Bootstrap** para ofrecer una interfaz moderna y profesional, adaptada a dispositivos móviles y escritorios.
- El diseño incluye estilos personalizados con **CSS** para mejorar la visualización de las imágenes y las listas.

### 5. **Navegación**:
- Se emplea **Vue Router** para gestionar la navegación entre las vistas y las rutas dinámicas de los Pokémon, asegurando una experiencia de usuario fluida.

---

## 🛠️ **Herramientas y Tecnologías Utilizadas**

- **Framework Frontend**: Vue 3
- **Gestión del Estado**: Pinia
- **Rutas**: Vue Router
- **Estilo**: Bootstrap, SCSS y CSS personalizado
- **Consumo de API**: Axios
- **Despliegue**: Netlify
- **API utilizada**: [PokeAPI](https://pokeapi.co/)
- **Iconos**: [Bootstrap Icons](https://icons.getbootstrap.com/
