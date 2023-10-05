# Ejercitación Práctica: Creación de un Perfil de Usuario con React y Bootstrap

**Objetivo General**: 
Desarrollar una aplicación React que simule una página de perfil de usuario, utilizando múltiples componentes y navegación con React Router DOM. La aplicación debe estar estilizada con Bootstrap y finalmente, se desplegará en Netlify.

## Especificaciones:

### 1. Componentes Principales:
   - **Encabezado**: Debe contener el nombre de la aplicación y un menú de navegación.
   - **Página Principal (`Home`)**: Una breve introducción o bienvenida al perfil del usuario.
   - **Información Personal (`About`)**: Detalles como nombre, edad, ocupación y una breve biografía.
   - **Hobbies (`Hobbies`)**: Una lista o galería de hobbies o intereses del usuario.
   - **Contacto (`Contact`)**: Un formulario ficticio para contactar al usuario (no es necesario que funcione).

### 2. Navegación:
   - Implementar React Router DOM para navegar entre los diferentes componentes.
   - El menú en el encabezado debe permitir al usuario cambiar entre las páginas principales, información personal, hobbies y contacto.

### 3. Estilización:
   - Utilizar Bootstrap para estilizar la aplicación, asegurándose de que sea responsiva.

### 4. Despliegue:
   - La aplicación debe ser desplegada en Netlify.

## Creación y Configuración del Proyecto React
1. Crear el proyecto:
```bash
npx create-react-app profile_react_despliegue
cd profile_react_despliegue
```

2. Instalar las dependencias necesarias:
```bash
npm install react-router-dom react-bootstrap bootstrap react-router-bootstrap
```

- `react-router-dom`: Librería de enrutamiento para aplicaciones React.

- `bootstrap`: Estilos CSS y componentes de Bootstrap para aplicaciones web.
  
- `react-bootstrap`: Componentes de interfaz de usuario de Bootstrap diseñados para React.

- `react-router-bootstrap` es una integración entre React Router v6 y React Bootstrap. 

3. Importar Bootstrap en src/App.js:
   
```js
...
import 'bootstrap/dist/css/bootstrap.min.css';
...
```


## Agregando Código al Proyecto React

### 1. Crear los componentes:

Dentro de la carpeta `src`, crea una carpeta llamada `components`.

### 2. Componente Encabezado (`Header.jsx`):

Dentro de `src/components`, crea un archivo llamado `Header.jsx`.

```jsx
import React from 'react';
import { Navbar, Nav } from 'react-bootstrap';
import { LinkContainer } from 'react-router-bootstrap';

function Header() {
    return (
        <Navbar bg="light" expand="lg">
            <LinkContainer to="/">
                <Navbar.Brand>Perfil de Usuario</Navbar.Brand>
            </LinkContainer>
            <Navbar id="basic-navbar-nav">
                <Nav className="ml-auto">
                    <LinkContainer to="/">
                        <Nav.Link>Inicio</Nav.Link>
                    </LinkContainer>
                    <LinkContainer to="/about">
                        <Nav.Link>Acerca de</Nav.Link>
                    </LinkContainer>
                    <LinkContainer to="/hobbies">
                        <Nav.Link>Hobbies</Nav.Link>
                    </LinkContainer>
                    <LinkContainer to="/contact">
                        <Nav.Link>Contacto</Nav.Link>
                    </LinkContainer>
                </Nav>
            </Navbar>
        </Navbar>
    );
}

export default Header;


```
### 3. Componente Página Principal (`Home.jsx`):

Dentro de `src/components`, crea un archivo llamado `Home.jsx`.

```jsx
import React from 'react';

function Home() {
    return (
        <div className="container mt-5">
            <h1>Bienvenido al Perfil de Usuario</h1>
            <p>Esta es la página principal del perfil. Aquí puedes encontrar una breve introducción o bienvenida al perfil del usuario.</p>
        </div>
    );
}

export default Home;
```

### 4. Componente Información Personal (`About.jsx`):

Dentro de `src/components`, crea un archivo llamado `About.jsx`.

```jsx
import React from 'react';

function About() {
    // Datos ficticios para el componente "Acerca de"
    const aboutData = {
        nombre: 'Juan Pérez',
        edad: 30,
        profesion: 'Desarrollador Web',
        descripcion: 'Soy un apasionado desarrollador web con experiencia en tecnologías como React, Node.js y Bootstrap. Me encanta crear aplicaciones web creativas y funcionales para mis clientes. Fuera del trabajo, disfruto de la música, la lectura y el senderismo en la naturaleza.',
    };

    return (
        <div className="container">
            <h2>Acerca de Mí</h2>
            <div className="card">
                <div className="card-body">
                    <h3 className="card-title">{aboutData.nombre}</h3>
                    <p className="card-text">Edad: {aboutData.edad} años</p>
                    <p className="card-text">Profesión: {aboutData.profesion}</p>
                    <p className="card-text">{aboutData.descripcion}</p>
                </div>
            </div>
        </div>
    );
}

export default About;

```

### 5. Componente Hobbies (`Hobbies.jsx`):

Dentro de `src/components`, crea un archivo llamado `Hobbies.jsx`.

```jsx
import React from 'react';

function Hobbies() {
    // Datos ficticios de hobbies
    const hobbies = [
        {
            id: 1,
            nombre: 'Senderismo',
            descripcion: 'Explorar montañas y disfrutar de la naturaleza.',
        },
        {
            id: 2,
            nombre: 'Fotografía',
            descripcion: 'Capturar momentos especiales con mi cámara.',
        },
        {
            id: 3,
            nombre: 'Pintura al óleo',
            descripcion: 'Crear obras de arte en lienzo.',
        },
        {
            id: 4,
            nombre: 'Jardinería',
            descripcion: 'Cultivar plantas y flores en mi jardín.',
        },
    ];

    return (
        <div className="container">
            <h2>Mis Hobbies</h2>
            <ul className="list-group">
                {hobbies.map((hobby) => (
                    <li key={hobby.id} className="list-group-item">
                        <h3>{hobby.nombre}</h3>
                        <p>{hobby.descripcion}</p>
                    </li>
                ))}
            </ul>
        </div>
    );
}

export default Hobbies;


```

### 6. Componente Contacto (`Contact.jsx`):

Dentro de `src/components`, crea un archivo llamado `Contact.jsx`.

```jsx
import React from 'react';

function Contact() {
    return (
        <div className="container mt-5">
            <h2>Contacto</h2>
            <form>
                <div className="form-group">
                    <label htmlFor="nombre">Nombre:</label>
                    <input type="text" className="form-control" id="nombre" />
                </div>
                <div className="form-group">
                    <label htmlFor="email">Correo Electrónico:</label>
                    <input type="email" className="form-control" id="email" />
                </div>
                <div className="form-group">
                    <label htmlFor="mensaje">Mensaje:</label>
                    <textarea className="form-control" id="mensaje" rows="4"></textarea>
                </div>
                <div className="mb-3 mt-3"> {/* Espacio adicional antes del botón */}
                    <button type="submit" className="btn btn-primary">Enviar</button>
                </div>
            </form>
        </div>
    );
}

export default Contact;

```

### 7. Componente Footer (`Footer.jsx`):

Dentro de `src/components`, crea un archivo llamado `Footer.jsx`.

```jsx
import React from 'react';

function Footer() {
    return (
        <footer className="bg-dark text-white text-center py-3">
            &copy; {new Date().getFullYear()} Perfil de Usuario - Todos los derechos reservados
        </footer>
    );
}

export default Footer;
```

### 8. Componente NotFound (`NotFound.jsx`):

Dentro de `src/components`, crea un archivo llamado `NotFound.jsx`.

```jsx
import React from 'react';

function NotFound() {
    return (
        <div className="container mt-5">
            <h2>Página no encontrada</h2>
            <p>Lo sentimos, la página que estás buscando no existe.</p>
        </div>
    );
}

export default NotFound;
```

### 9. Archivo `App.js`:

Dentro de la raíz de tu proyecto, encuentra el archivo `src/App.js` y reemplaza su contenido con el siguiente código:

```jsx
import React from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import Header from './components/Header';
import Home from './components/Home';
import About from './components/About';
import Hobbies from './components/Hobbies';
import Contact from './components/Contact';
import Footer from './components/Footer';
import NotFound from './components/NotFound';

function App() {
    return (
        <Router>
            <div>
                <Header />
                <Routes>
                    <Route path="/" element={<Home />} />
                    <Route path="/about" element={<About />} />
                    <Route path="/hobbies" element={<Hobbies />} />
                    <Route path="/contact" element={<Contact />} />
                    <Route path="*" element={<NotFound />} />
                </Routes>
                <Footer />
            </div>
        </Router>
    );
}

export default App;

```


## Despliegue en Netlify

Netlify es una plataforma de automatización moderna para el desarrollo web que permite desplegar sitios y aplicaciones web de manera rápida y sencilla. Ofrece características como despliegue continuo desde repositorios git, funciones sin servidor, y mucho más.

Para continuar es necesario crear una cuenta gratuita en https://www.netlify.com/.


1. Instalar Netlify CLI:

Abre una terminal en la carpeta raíz de tu proyecto y ejecuta el siguiente comando para instalar la herramienta netlify-cli, que facilitará el despliegue en Netlify:

```bash
npm install netlify-cli -g
```

2. Modificar scripts en package.json:

En package.json, modifica la sección de scripts para actualizar la variable PUBLIC_URL:

```json
"scripts": {
    "build": "PUBLIC_URL= react-scripts build",
    // ...otros comandos...
}
```

3. Ejecuta el despliegue:

Ahora puedes ejecutar el comando para desplegar tu aplicación en Netlify:

```bash
npm run build

netlify deploy
```
Seguir las instrucciones y indicar la carpeta `./build` como fuente para desplegar el sitio. Esto construirá la aplicación y la desplegará.

4. Accede a tu aplicación desplegada:

Una vez que el proceso de despliegue haya finalizado sin errores, puedes acceder a tu aplicación en la URL que indica en el resultado.

5. Actualiza y comparte:

Cada vez que realices cambios en tu aplicación, repite el paso 3 para actualizar la versión desplegada en Netlify.

¡Eso es todo! Tu aplicación React debería estar ahora desplegada en Netlify y accesible en línea.
