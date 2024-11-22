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


    
