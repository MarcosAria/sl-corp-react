# SL Corp – Sitio Web Corporativo y Carrusel de Equipo

[![React](https://img.shields.io/badge/React-18.2.0-blue)](https://reactjs.org/)
[![Vite](https://img.shields.io/badge/Vite-4.4.0-yellow)](https://vitejs.dev/)

Sitio web corporativo de **SL Corp**, desarrollado con **React** y **Vite**. Contiene secciones informativas, un diseño responsivo y un carrusel dinámico con navegación individual a detalle de cada miembro del equipo.

---

## 🧩 Características principales

- Componente **TeamSlider** con navegación a detalles (`/member/:id`)
- Estructura **modular** y organizada por componentes
- Conexión a datos dinámicos mediante **JSON Server**
- Diseño **responsivo** adaptable a todos los dispositivos
- Estilos encapsulados con **CSS Modules**
- Uso de **React Hooks** (`useState`, `useEffect`) para lógica interactiva
- Navegación interna usando **React Router**

---

## 🚀 Descripción del Funcionamiento

### 🧑‍🤝‍🧑 Carrusel TeamSlider

El componente `TeamSlider` muestra tarjetas con información de cada miembro del equipo (foto, nombre, rol). Cada tarjeta incluye un botón que lleva a una página de detalle usando React Router. Los datos se consumen desde un archivo JSON (`teamData.json`) simulado como API mediante **JSON Server**.

### 🏢 Sitio Web Corporativo

El resto del sitio está dividido en secciones como *servicios, misión y visión, testimonios*, etc., organizadas como componentes reutilizables. El diseño es intuitivo y adaptable, con menús interactivos y uso extensivo de hooks para cargar y manejar datos dinámicos.

---

## 🛠️ Tecnologías utilizadas

- **React 18** – Biblioteca principal para construir la UI
- **Vite** – Herramienta de desarrollo rápida
- **React Router** – Navegación por rutas dinámicas
- **CSS Modules** – Estilos locales encapsulados
- **React Icons** – Íconos vectoriales
- **JSON Server** – Mock API para datos locales

---

## 📦 Instalación

1. Clona el repositorio:
   ```bash
   git clone https://github.com/MarcosAria/sl-corp-react.git
   cd sl-corp-react

2. Instala dependencias:
    ```bash
    npm install
    ```

3. Inicia el servidor de desarrollo:
    ```bash
    npm run dev
    ```



## Estructura del proyecto
A continuación, se muestra la estructura del directorio del proyecto, destacando los archivos y carpetas clave:

```bash
sl-corp-react/
├── data/
│   └── services.json                # Servicios simulados con JSON Server
├── public/
│   ├── IMG/                         # Imágenes del sitio
│   ├── imgs/                        # Imágenes del equipo
│   └── teamData.json                # Datos de miembros del equipo
├── src/
│   ├── components/
│   │   ├── AboutUs/
│   │   ├── Footer/
│   │   ├── Header/
│   │   ├── Hero/
│   │   ├── Layout/
│   │   ├── MissionVision/
│   │   ├── ServiceCard/
│   │   ├── Services/
│   │   ├── ServicesOverview/
│   │   ├── TeamSlider/
│   │   └── Testimonials/
│   ├── pages/
│   │   ├── Home/
│   │   ├── MemberDetail/           # Página individual por miembro
│   │   └── TeamSliderPage/
│   ├── App.jsx
│   ├── main.jsx
│   ├── index.css
├── index.html
├── package.json
├── vite.config.js
└── README.md

```

## Conexión a Datos
La aplicación obtiene información dinámica (como los servicios ofrecidos) utilizando **fetch** para consumir datos desde un archivo JSON simulado con **JSON Server**. Esto permite separar la lógica de presentación de los datos, facilitando la actualización del contenido sin modificar los componentes.

**Pasos para simular la API:**
1. Instala JSON Server de forma global (si no lo tienes):
  ```bash
  npm install -g json-server
  ```
2. Ejecuta el servidor apuntando al archivo de datos:
  ```bash
  json-server --watch data/services.json --port 3000
  ```
3. Accede a los datos desde tu aplicación React usando:
  ```js
  fetch('http://localhost:3000/services')
    .then(response => response.json())
    .then(data => setServices(data));
  ```

Esto permite que los componentes de React consuman y muestren datos de manera dinámica, simulando una API real durante el desarrollo.


## Retos Enfrentados y Soluciones Implementadas
Este fue nuestro primer sitio web desarrollado con React, por lo que comenzamos con conocimientos muy básicos. Si bien ya teníamos una versión previa del sitio construida en HTML y CSS puro, la transición a JSX fue un desafío inicial. Afortunadamente, contar con experiencia previa en HTML/CSS facilitó la adaptación de nuestro código al formato JSX, ya que los conceptos fundamentales de estructura y estilo eran familiares.

Uno de los principales desafíos fue entender cómo se estructuran y conectan los archivos en un proyecto React. El concepto de componentes, así como el sistema de import y export, no era claro al principio. Sin embargo, a través de investigación y experimentación práctica, logramos comprender la arquitectura del proyecto y cómo mantener una estructura ordenada.

Otro reto importante fue la sección de servicios, donde intentamos trabajar con datos dinámicos utilizando JSON Server para practicar su uso. Aprender a manejar los React Hooks como useState y useEffect fue clave para lograr la carga y renderizado dinámico de los servicios desde un archivo JSON. Inicialmente, fue complejo entender cómo y cuándo se ejecutaban estos hooks, pero con práctica logramos integrarlos correctamente para simular una llamada a una API y dividir los datos en grupos visuales.

Gracias al proceso de prueba y error, al apoyo de la documentación en el curso y al hecho de tener un diseño base, pudimos superar estas barreras y completar el proyecto.

SLIDER:

Este carrusel de equipo fue una de nuestras primeras experiencias trabajando con React de forma modular y estructurada. Uno de los principales retos fue organizar los componentes para que el slider conviviera dentro de una arquitectura escalable, manteniendo una buena separación de responsabilidades y un flujo de datos claro.

Implementar la navegación entre el carrusel principal y las páginas individuales para cada miembro del equipo también representó un desafío. Para resolverlo, integramos react-router-dom, lo cual nos permitió crear rutas dinámicas sin comprometer la estructura general del sitio. La solución incluyó configurar el componente principal (App.jsx) con un sistema de rutas que mantiene elementos globales como la barra de navegación y el pie de página visibles en todas las vistas.

Otro aspecto clave fue hacer que el slider fuera completamente responsivo. Utilizamos CSS modular y media queries para adaptar el diseño a todos los dispositivos, además de React Hooks como useState y useEffect para manejar los datos del equipo de manera dinámica, simulando una llamada a una API con un archivo JSON local.

A través de prueba y error, lectura de documentación y una base de diseño clara, logramos superar los desafíos técnicos y completar un componente atractivo, funcional y adaptable para futuros proyectos.



## Autores
Desarrollado por Maribel Paulina Sánchez Jiménez, Marcos Daniel Arias Cerino, José Antonio Arce Zabala y Gabriel Domínguez Gómez.

## Licencia
Este proyecto está bajo la licencia MIT.


