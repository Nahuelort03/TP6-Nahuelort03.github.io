<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login</title>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
    <link rel="stylesheet" href="styles.css">
</head>
<body class="index">
    <div class="login-container">
        <h2>Iniciar Sesión</h2>
        <form id="loginForm">
            <label for="username">Usuario:</label>
            <input type="text" id="username" name="username" placeholder="Ingresa tu usuario" required>
                        <label for="password">Contraseña:</label>
            <input type="password" id="password" name="password" placeholder="Ingresa tu contraseña" required>
                        <button type="submit">Ingresar</button>
        </form>
        <p id="error-message" style="display: none; color: red;">Usuario o contraseña incorrectos.</p>
    </div>

   <script src="script.js"></script>
</body>
</html>

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página Principal</title>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
    <link rel="stylesheet" href="styles.css">
</head>
<body class="pagina1">
    <div class="container">        <h1>¡Bienvenido a mi WEB!</h1>        <p>En esta página encontrarás:         </p>      
<ul>
<li><strong>Página 2:</strong> Formulario que envíe los datos personales de una persona</li>
            <li><strong>Página 3:</strong> Formulario que envíe un mensaje de texto largo</li>
        </ul>
        <div id="user-welcome"></div>
        <div class="buttons">
            <button onclick="navigateTo('pagina2.html')" class="animated-button">Ir a Página 2</button>
            <button onclick="navigateTo('pagina3.html')" class="animated-button">Ir a Página 3</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página 2 - Formulario</title>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
    <link rel="stylesheet" href="styles.css">
</head>
<body class="pagina2">
    <div class="container">
        <h1>Formulario de Datos Personales</h1>
        <form id="personal-data-form">
            <label for="nombre">Nombre:</label>
            <input type="text" id="nombre" name="nombre" required><br>
            <label for="apellido">Apellido:</label>
            <input type="text" id="apellido" name="apellido" required><br>
            <label for="edad">Edad:</label>
            <input type="number" id="edad" name="edad" required><br>
            <label for="direccion">Dirección:</label>
            <input type="text" id="direccion" name="direccion" required><br>
           <label for="celular">Celular:</label>
            <input type="tel" id="celular" name="celular" required><br>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required><br>
            <label for="ciudad">Ciudad:</label>
            <input type="text" id="ciudad" name="ciudad" required><br>
            <label for="pais">País:</label>
            <input type="text" id="pais" name="pais" required><br>
            <div class="form-buttons">
                <button type="submit">Enviar</button>
                <button type="reset">Limpiar</button>
            </div>
        </form>
      <p id="responseMessage" style="display: none;"></p>
        <div class="buttons">
            <button onclick="navigateTo('pagina1.html')" class="animated-button">Ir a Página Principal</button>
            <button onclick="navigateTo('pagina3.html')" class="animated-button">Ir a Página 3</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página 3 - Enviar Mensaje</title>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
    <link rel="stylesheet" href="styles.css">
</head>
<body class="pagina3">
    <div class="container">
        <h1>Formulario para Enviar Mensaje</h1>
        <form id="message-form">
            <label for="nombre">Nombre:</label>
            <input type="text" id="nombre" name="nombre" required><br>
            <label for="apellido">Apellido:</label>
            <input type="text" id="apellido" name="apellido" required><br>
            <label for="celular">Celular:</label>
            <input type="tel" id="celular" name="celular" required><br>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required><br>
            <label for="mensaje">Mensaje:</label>
            <textarea id="mensaje" name="mensaje" rows="5" required></textarea><br>
            <div class="form-buttons">
                <button type="submit">Enviar</button>
                <button type="reset">Limpiar</button>
            </div>
        </form>
        <p id="responseMessage" style="display: none;"></p>
        <div class="buttons">
            <button onclick="navigateTo('pagina1.html')" class="animated-button">Ir a Página Principal</button>
            <button onclick="navigateTo('pagina2.html')" class="animated-button">Ir a Página 2</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

document.addEventListener("DOMContentLoaded", function() {
    // Inicializar EmailJS (asegúrate de configurarlo previamente)
    (function() {
        emailjs.init("wrBOMNdDfuDldH6k1"); // Reemplaza con tu User ID de EmailJS
    })();

    // ----------------------------
    // Funcionalidad de LOGIN (Index)
    // ----------------------------
document.getElementById("loginForm")?.addEventListener("submit", function(event) {
        event.preventDefault(); // Evitar el envío predeterminado del formulario
        const username = document.getElementById("username").value;
        const password = document.getElementById("password").value;
        // Simular usuario y contraseña válidos
        const validUsername = "admin";
        const validPassword = "1234";
        console.log("Datos ingresados:", username, password);
        if (username === validUsername && password === validPassword) {
            console.log("Login exitoso, redirigiendo...");
            alert(`Bienvenido, ${username}. Has ingresado correctamente.`);
            // Enviar correo informando quién ingresó
            emailjs.send("service_6ao64uc","template_ex25q5f", {
                username: username
            })
            .then(function() {
                console.log("Correo enviado con éxito.");
            })
            .catch(function(error) {
                console.error("Error al enviar el correo:", error);
            });

ñ            // Redirigir a la página principal (Página 1)
            window.location.href = "pagina1.html";  // Redirigir correctamente a la página 1
        } else {
            console.log("Credenciales incorrectas.");
            document.getElementById("error-message").style.display = "block";
        }
    });
    // ----------------------------
    // Funcionalidad de PÁGINA 1 - Bienvenida al Usuario
    // ----------------------------
    if (window.location.pathname.includes("pagina1.html")) {
        const userName = prompt("Por favor, ingresa tu nombre:");
        if (userName) {
            alert(`¡Bienvenido, ${userName}!`);
            const welcomeMessageElement = document.getElementById("user-welcome");
            if (welcomeMessageElement) {
                welcomeMessageElement.textContent = `Hola, ${userName}. ¡Bienvenido a la página principal!`;
            }
        }
    }
    // ----------------------------
    // Funcionalidad de PÁGINA 2 - Enviar Formulario de Datos Personales
    // ----------------------------
    document.getElementById("personal-data-form")?.addEventListener("submit", function(event) {
        event.preventDefault(); // Prevenir el envío del formulario por defecto
        const nombre = document.getElementById("nombre").value;
        const apellido = document.getElementById("apellido").value;
        const edad = document.getElementById("edad").value;
        const direccion = document.getElementById("direccion").value;
        const celular = document.getElementById("celular").value;
        const email = document.getElementById("email").value;
        const ciudad = document.getElementById("ciudad").value;
        const pais = document.getElementById("pais").value;
        // Enviar datos mediante EmailJS
        emailjs.send("service_6ao64uc", "template_f6nqa0k", {
            nombre: nombre,
            apellido: apellido,
            edad: edad,
            direccion: direccion,
            celular: celular,
            email: email,
            ciudad: ciudad,
            pais: pais
        })
        .then(function(response) {
            console.log("Correo enviado con éxito", response);
            const responseMessage = document.getElementById("responseMessage");
            if (responseMessage) {
                responseMessage.textContent = "¡Formulario enviado correctamente!";
            }
        }, function(error) {
            console.error("Error al enviar el correo:", error);
            const responseMessage = document.getElementById("responseMessage");
            if (responseMessage) {
                responseMessage.textContent = "Error al enviar el formulario.";
            }
        });
    });
    // ----------------------------
    // Funcionalidad de PÁGINA 3 - Formulario de Mensaje
    // ----------------------------
    document.getElementById("message-form")?.addEventListener("submit", function(event) {
        event.preventDefault(); // Prevenir el envío predeterminado del formulario
        const nombre = document.getElementById("nombre").value;
        const apellido = document.getElementById("apellido").value;
        const celular = document.getElementById("celular").value;
        const email = document.getElementById("email").value;
        const mensaje = document.getElementById("mensaje").value;
        // Enviar datos mediante EmailJS

emailjs.send("service_6ao64uc", "template_ex25q5f", {
            nombre: nombre,
            apellido: apellido,
            celular: celular,
            email: email,
            mensaje: mensaje
        })
        .then(function(response) {
            console.log("Correo enviado con éxito", response);
            const responseMessage = document.getElementById("responseMessage");
            if (responseMessage) {
                responseMessage.textContent = "¡Formulario enviado correctamente!";
            }
        }, function(error) {
            console.error("Error al enviar el correo:", error);
            const responseMessage = document.getElementById("responseMessage");
            if (responseMessage) {
                responseMessage.textContent = "Error al enviar el formulario.";
            }
        });
    });
});

// Función para limpiar el formulario (Página 3)
function clearMessageForm() {
    document.getElementById("message-form").reset();
}

// Función para limpiar el formulario (Página 3)
function clearPersonalForm() {
    document.getElementById("personal-data-form").reset();
}

// ----------------------------
// Función para navegar entre páginas
// ----------------------------

function navigateTo(url) {
    window.location.href = url;
    }

/* Index */
body.index {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

body.index .login-container {
    background-color: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

body.index h2 {
    margin-bottom: 20px;
}

body.index label,
body.index input {
    display: block;
    width: 100%;
    margin-bottom: 10px;
}

body.index button {
    width: 100%;
    padding: 10px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

body.index button:hover {
    background-color: #45a049;
}

/* Página 1 */
body.pagina1 {
    font-family: 'Arial', sans-serif;
    margin: 0;
    padding: 0;
    background: linear-gradient(to bottom, #e0f7fa, #b2ebf2);
    color: #003d5b;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

body.pagina1 .container {
    text-align: center;
    padding: 20px;
    border: 2px solid #00796b;
    border-radius: 10px;
    background: #ffffff;
    box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.2);
}

body.pagina1 ul {
    text-align: left;
}

#user-welcome {
    font-size: 1.2rem;
    font-weight: bold;
    color: #00796b;
    margin-top: 20px;
}

/* Página 2 */
body.pagina2 {
    font-family: 'Georgia', serif;
    margin: 0;
    padding: 0;
    background: linear-gradient(to bottom, #ffe082, #ffcc80);
    color: #4e342e;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

body.pagina2 .container {
    text-align: center;
    padding: 20px;
    border: 2px solid #d84315;
    border-radius: 10px;
    background: #ffffff;
    box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.2);
}

body.pagina2 form label {
    color: #4e342e;
    font-weight: bold;
}

body.pagina2 form button[type="submit"] {
    background-color: #d84315;
    color: #fff;
}

body.pagina2 form button[type="submit"]:hover {
    background-color: #bf360c;
}

/* Página 3 */
body.pagina3 {
    font-family: 'Comic Sans MS', cursive, sans-serif;
    margin: 0;
    padding: 0;
    background: linear-gradient(to bottom, #c8e6c9, #a5d6a7);
    color: #1b5e20;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

body.pagina3 .container {
    text-align: center;
    padding: 20px;
    border: 2px solid #388e3c;
    border-radius: 10px;
    background: #ffffff;
    box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.2);
}

body.pagina3 textarea {
    width: 70%;
    height: 200px;
    border: 1px solid #1b5e20;
    border-radius: 5px;
}

body.pagina3 form button[type="submit"] {
    background-color: #c8e6c9;
    color: #fff;
}

body.pagina3 form button[type="submit"]:hover {
    background-color: #a5d6a7;
}

/* General */

.buttons {
    margin-top: 20px;
}

.animated-button {
    margin: 10px;
    padding: 15px 30px;
    font-size: 16px;
    color: #fff;
    background-color: #0078d4;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: transform 0.2s, background-color 0.3s;
}

.animated-button:hover {
    background-color: #005bb5;
    transform: scale(1.1);
}

.animated-button:active {
    transform: scale(1.05);
}

input {
    width: 100%;
    padding: 8px;
    margin-bottom: 15px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 14px;
}
