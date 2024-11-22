# TP6-Nahuelort03.github.io

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

            // Redirigir a la página principal (Página 1)
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
