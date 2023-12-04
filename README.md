# santa-secreto
Descubre a quién le darás un regalo
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Generador de Nombres</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin: 50px;
    }

    button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <h2>Generador de Nombres</h2>

  <label for="nombre">Ingresa tu nombre:</label>
  <input type="text" id="nombre" placeholder="Escribe tu nombre">

  <br><br>

  <button onclick="generarNombre()">Generar Nombre</button>

  <h3 id="nombreGenerado"></h3>

  <script>
    // Lista de nombres disponibles
    var nombresDisponibles = ["Marcela", "Jesús", "Jesús Gabriel", "Joel", "Yeróm", "Alexa", "Mariana", "Víctor"];

    function generarNombre() {
      var inputNombre = document.getElementById("nombre");
      var nombreGenerado = document.getElementById("nombreGenerado");

      // Verificar si hay nombres disponibles
      if (nombresDisponibles.length > 0) {
        // Generar un índice aleatorio
        var indiceAleatorio = Math.floor(Math.random() * nombresDisponibles.length);

        // Obtener y mostrar el nombre generado
        var nombre = nombresDisponibles[indiceAleatorio];
        nombreGenerado.textContent = "Nombre generado: " + nombre;

        // Eliminar el nombre de la lista
        nombresDisponibles.splice(indiceAleatorio, 1);
      } else {
        // Mostrar mensaje si no hay más nombres disponibles
        nombreGenerado.textContent = "No hay más nombres disponibles";
      }

      // Limpiar el campo de entrada
      inputNombre.value = "";
    }
  </script>

</body>
</html>
