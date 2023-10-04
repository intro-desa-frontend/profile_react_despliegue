# Ejercitación Práctica: Creación de un Perfil de Usuario con React y Bootstrap

**Objetivo General**: 
Desarrollar una aplicación React que simule una página de perfil de usuario, utilizando múltiples componentes y navegación con React Router DOM. La aplicación debe estar estilizada con Bootstrap y finalmente, se desplegará en GitHub Pages.

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
   - La aplicación debe ser desplegada en GitHub Pages.

## Creación y Configuración del Proyecto React
1. Crear el proyecto:
```bash
npx create-react-app profile_react_despliegue
cd profile_react_despliegue
```

2. Instalar las dependencias necesarias:
```bash
npm install react-router-dom bootstrap
```

3. Importar Bootstrap en src/index.css:
```css
@import "~bootstrap/dist/css/bootstrap.min.css";
```


## Agregando Código al Proyecto React

### 1. Crear los componentes:

Dentro de la carpeta `src`, crea una carpeta llamada `components`.

### 2. Componente Encabezado (`Header.jsx`):

Dentro de `src/components`, crea un archivo llamado `Header.jsx`.

```jsx
import React from 'react';
import { Link } from 'react-router-dom';

function Header() {
    return (
        <nav className="navbar navbar-expand-lg navbar-light bg-light">
            <Link className="navbar-brand" to="/">Perfil de Usuario</Link>
            <div className="collapse navbar-collapse">
                <ul className="navbar-nav mr-auto">
                    <li className="nav-item">
                        <Link className="nav-link" to="/">Inicio</Link>
                    </li>
                    <li className="nav-item">
                        <Link className="nav-link" to="/about">Acerca de</Link>
                    </li>
                    <li className="nav-item">
                        <Link className="nav-link" to="/hobbies">Hobbies</Link>
                    </li>
                </ul>
            </div>
        </nav>
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
    return (
        <div className="container mt-5">
            <h2>Información Personal</h2>
            <p>Nombre: [Tu Nombre]</p>
            <p>Edad: [Tu Edad]</p>
            <p>Ocupación: [Tu Ocupación]</p>
            <p>Biografía: [Escribe una breve biografía aquí]</p>
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
    return (
        <div className="container mt-5">
            <h2>Mis Hobbies</h2>
            <ul>
                <li> Hobby 1: [Descripción del Hobby 1]</li>
                <li> Hobby 2: [Descripción del Hobby 2]</li>
                <li> Hobby 3: [Descripción del Hobby 3]</li>
                {/* Agrega más hobbies si es necesario */}
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
            <p>Puedes contactarme completando el siguiente formulario:</p>
            <form>
                <div className="form-group">
                    <label htmlFor="nombre">Nombre:</label>
                    <input type="text" className="form-control" id="nombre" />
                </div>
                <div className="form-group">
                    <label htmlFor="email">Email:</label>
                    <input type="email" className="form-control" id="email" />
                </div>
                <div className="form-group">
                    <label htmlFor="mensaje">Mensaje:</label>
                    <textarea className="form-control" id="mensaje" rows="4"></textarea>
                </div>
                <button type="submit" className="btn btn-primary">Enviar Mensaje</button>
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


## Despliegue en GitHub Pages
1. Instala gh-pages:

Abre una terminal en la carpeta raíz de tu proyecto y ejecuta el siguiente comando para instalar la herramienta gh-pages, que facilitará el despliegue en GitHub Pages:

```bash
npm install gh-pages --save-dev
```

2. Agrega el campo homepage en package.json:

En tu archivo package.json, agrega un campo homepage con la URL de tu repositorio de GitHub. Debería verse como esto:

```json
"homepage": "https://nombredeusuario.github.io/nombre-de-repo"

Sustituye nombredeusuario por tu nombre de usuario de GitHub y nombre-de-repo por el nombre de tu repositorio.

3. Modifica scripts en package.json:

En package.json, modifica la sección de scripts para agregar dos nuevos comandos:

```json
"scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build",
    // ...otros comandos...
}
```

Estos comandos le indicarán a gh-pages que primero construya la aplicación antes de desplegarla.

4. Ejecuta el despliegue:

Ahora puedes ejecutar el comando para desplegar tu aplicación en GitHub Pages:

```bash
npm run deploy
```

Esto construirá la aplicación y la desplegará en una rama llamada gh-pages de tu repositorio de GitHub.

5. Accede a tu aplicación desplegada:

Una vez que el proceso de despliegue haya finalizado sin errores, puedes acceder a tu aplicación en la URL https://nombredeusuario.github.io/nombre-de-repo, reemplazando nombredeusuario y nombre-de-repo por tus propios datos.

6. Actualiza y comparte:

Cada vez que realices cambios en tu aplicación, repite los pasos 3 y 4 para actualizar la versión desplegada en GitHub Pages.

¡Eso es todo! Tu aplicación React debería estar ahora desplegada en GitHub Pages y accesible en línea.