# 🎬 CineSearch | Cartelera Interactiva con TMDB

Una aplicación web moderna y responsiva que consume la API de [The Movie Database (TMDB)](https://www.themoviedb.org/) para explorar las películas más populares, buscar títulos en tiempo real y visualizar detalles en un modal interactivo.

Construido desde cero con **Vanilla TypeScript**, enfocándose en la manipulación eficiente del DOM, la asincronía y el control de peticiones a la API.

## ✨ Características Principales

*   **Galería Inicial:** Carga automática de las películas más populares del momento.
*   **Búsqueda en Tiempo Real (Debounce):** Buscador optimizado que espera a que el usuario deje de escribir para lanzar la petición, evitando saturar la API.
*   **Control de Concurrencia (Race Condition):** Implementación de un sistema de `requestId` para asegurar que solo se renderice la última búsqueda realizada, evitando resultados cruzados si la red es lenta.
*   **Paginación Inteligente:** Navegación entre páginas que recuerda el contexto: si el usuario está viendo "Populares" o los resultados de una "Búsqueda".
*   **Modal de Detalles:** Ventana modal nativa de HTML5 (`<dialog>`) que muestra la sinopsis, géneros y puntuación de la película seleccionada.
*   **Manejo de Errores:** Feedback visual amigable si no hay resultados o falla la conexión con la API.
*   **Diseño Responsivo:** Interfaz adaptada a dispositivos móviles y de escritorio.

## 🚀 Tecnologías Utilizadas

*   **[TypeScript](https://www.typescriptlang.org/):** Tipado estricto para todas las respuestas de la API y variables del DOM.
*   **[Vite](https://vitejs.dev/):** Empaquetador y servidor de desarrollo.
*   **HTML5 & CSS3:** Uso de etiquetas semánticas, `<template>` para el renderizado y `<dialog>` para el modal.
*   **[TMDB API](https://developer.themoviedb.org/docs):** Fuente de datos RESTful.

## 🧠 Aspectos Técnicos Destacados

*   **Delegación de Eventos:** Uso de un solo `addEventListener` en el contenedor principal para manejar los clics en los botones generados dinámicamente.
*   **Clonación de Nodos:** Uso de `template.content.cloneNode(true)` para renderizar tarjetas de forma eficiente sin ensuciar el archivo principal de TypeScript.
*   **Manejo de Promesas:** Uso extensivo de `async / await` con bloques `try...catch...finally`.

## 🛠️ Cómo ejecutar el proyecto localmente

1. Clona este repositorio:
   ```bash
   git clone https://github.com/JohnCordoba2004/tmdb.git
   
2. Entra en la carpeta del proyecto:
   cd tmdb
  
3. Instala las dependencias:
   npm install

4. Configura tus variables de entorno:
   Crea un archivo .env en la raíz del proyecto y añade tu propia API Key de TMDB:
   VITE_TMDB_API_KEY=tu_api_key_aqui

5. Inicia el servidor de desarrollador
   npm run dev

6. Abre tu navegador en http://localhost:5173.

📸 Captura de Pantalla

<img width="2542" height="1300" alt="image" src="https://github.com/user-attachments/assets/d8ae1c43-6f25-4aff-b1fc-96ea96ca16df" />

<img width="1118" height="706" alt="image" src="https://github.com/user-attachments/assets/dc264953-f581-4458-a73c-e5bff9d4e564" />

<img width="2526" height="1279" alt="image" src="https://github.com/user-attachments/assets/96fc7fe5-e8e2-4f9c-8b4c-f8dba8091e87" />

<img width="2508" height="1290" alt="image" src="https://github.com/user-attachments/assets/5258f114-582a-4f35-9a1e-baea232ab6c6" />


💡 Lo que aprendí construyendo esto
A implementar un Debounce manual para mejorar el rendimiento de las búsquedas.

A manejar Race Conditions en las peticiones HTTP (evitando que datos viejos sobrescriban los nuevos).

A estructurar un proyecto de Vanilla TS escalable, separando la lógica de la red, el renderizado y el manejo del DOM.

A utilizar la etiqueta <dialog> nativa para crear modales accesibles y sin dependencias externas.

Hecho con ❤️ y mucho amor por John Córdoba.
