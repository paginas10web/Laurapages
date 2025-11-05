<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Recetas y Juegos de Cocina</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #fff8e1;
      margin: 0;
      padding: 0;
    }

    header {
      background-color: #ff7043;
      color: white;
      text-align: center;
      padding: 20px;
    }

    nav {
      background-color: #ffab91;
      display: flex;
      justify-content: center;
      gap: 20px;
      padding: 10px;
    }

    nav a {
      text-decoration: none;
      color: #000;
      font-weight: bold;
    }

    section {
      padding: 20px;
      display: none;
    }

    section.active {
      display: block;
    }

    .receta {
      background-color: #fff3e0;
      border: 1px solid #ffb74d;
      border-radius: 10px;
      margin-bottom: 15px;
      padding: 15px;
    }

    .receta img {
      width: 100%;
      max-width: 400px;
      border-radius: 10px;
      display: block;
      margin: 10px auto;
    }

    button {
      background-color: #ff7043;
      color: white;
      border: none;
      padding: 10px;
      border-radius: 5px;
      cursor: pointer;
    }

    button:hover {
      background-color: #e64a19;
    }

    #juego {
      text-align: center;
    }

    #palabra {
      font-size: 24px;
      letter-spacing: 5px;
      margin: 20px 0;
    }

    input[type="text"] {
      padding: 5px;
      font-size: 18px;
      width: 50px;
      text-align: center;
    }

    form {
      max-width: 400px;
      margin: auto;
      background-color: #fff3e0;
      padding: 20px;
      border-radius: 10px;
      border: 1px solid #ffb74d;
    }

    label {
      display: block;
      margin-top: 10px;
    }

    input, textarea {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
    }

    footer {
      text-align: center;
      background-color: #ffab91;
      padding: 10px;
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <header>
    <h1>Recetas y Juegos de Cocina</h1>
  </header>

  <nav>
    <a href="#" onclick="mostrarSeccion('recetas')">🍲 Recetas</a>
    <a href="#" onclick="mostrarSeccion('ahorcado')">🎮 Ahorcado</a>
    <a href="#" onclick="mostrarSeccion('registro')">📋 Registro</a>
  </nav>

  <!-- Sección de Recetas -->
  <section id="recetas" class="active">
    <h2>Recetas Gastronómicas</h2>

    <div class="receta">
      <h3>1. Paella Española</h3>
      <img src="https://cdn.pixabay.com/photo/2015/07/01/08/21/paella-827584_1280.jpg" alt="Paella Española">
      <p><strong>Ingredientes:</strong> Arroz, pollo, mariscos, pimientos, cebolla, azafrán, aceite de oliva.</p>
      <p><strong>Pasos:</strong></p>
      <ol>
        <li>Sofríe el pollo y los mariscos.</li>
        <li>Agrega las verduras y el arroz.</li>
        <li>Vierte caldo con azafrán y cocina 20 minutos.</li>
      </ol>
    </div>

    <div class="receta">
      <h3>2. Pasta Carbonara</h3>
      <img src="https://cdn.pixabay.com/photo/2017/08/06/12/38/spaghetti-2590508_1280.jpg" alt="Pasta Carbonara">
      <p><strong>Ingredientes:</strong> Pasta, huevo, panceta, queso parmesano, pimienta.</p>
      <p><strong>Pasos:</strong></p>
      <ol>
        <li>Cocina la pasta y sofríe la panceta.</li>
        <li>Mezcla huevos y queso.</li>
        <li>Combina todo y sirve caliente.</li>
      </ol>
    </div>

    <div class="receta">
      <h3>3. Arepas de Queso</h3>
      <img src="https://cdn.pixabay.com/photo/2020/05/21/22/59/arepas-5203420_1280.jpg" alt="Arepas de Queso">
      <p><strong>Ingredientes:</strong> Harina de maíz, queso rallado, mantequilla, sal.</p>
      <p><strong>Pasos:</strong></p>
      <ol>
        <li>Mezcla todos los ingredientes.</li>
        <li>Forma las arepas y cocínalas en sartén.</li>
        <li>Sirve con mantequilla derretida.</li>
      </ol>
    </div>
  </section>

  <!-- Juego del Ahorcado -->
  <section id="ahorcado">
    <h2>Juego del Ahorcado - Cocina</h2>
    <div id="juego">
      <p id="palabra"></p>
      <p>Intentos restantes: <span id="intentos"></span></p>
      <input type="text" id="letra" maxlength="1" placeholder="Letra">
      <button onclick="intentar()">Probar</button>
      <p id="mensaje"></p>
      <button onclick="nuevoJuego()">Nuevo Juego</button>
      <br><br>
      <img id="imagenAhorcado" src="https://cdn-icons-png.flaticon.com/512/685/685655.png" width="150" alt="Ahorcado">
    </div>
  </section>

  <!-- Formulario de Registro -->
  <section id="registro">
    <h2>Formulario de Registro</h2>
    <form>
      <label>Nombre completo:</label>
      <input type="text" required>

      <label>Correo electrónico:</label>
      <input type="email" required>

      <label>Contraseña:</label>
      <input type="password" required>

      <label>Mensaje o comentario:</label>
      <textarea rows="3"></textarea>

      <button type="submit">Registrarse</button>
    </form>
  </section>

  <footer>
    © 2025 Recetas y Juegos de Cocina | Desarrollado por ChatGPT
  </footer>

  <script>
    // Cambiar secciones
    function mostrarSeccion(id) {
      document.querySelectorAll("section").forEach(sec => sec.classList.remove("active"));
      document.getElementById(id).classList.add("active");
    }

    // Palabras del juego
    const palabras = ["chef", "cuchara", "receta", "sarten", "cocina", "ingrediente", "pastel", "taza", "sal", "azucar"];
    let palabraSecreta = "";
    let palabraGuiones = [];
    let intentosRestantes = 6;

    function nuevoJuego() {
      palabraSecreta = palabras[Math.floor(Math.random() * palabras.length)];
      palabraGuiones = Array(palabraSecreta.length).fill("_");
      intentosRestantes = 6;
      document.getElementById("palabra").textContent = palabraGuiones.join(" ");
      document.getElementById("intentos").textContent = intentosRestantes;
      document.getElementById("mensaje").textContent = "";
      document.getElementById("imagenAhorcado").src = "https://cdn-icons-png.flaticon.com/512/685/685655.png";
    }

    
    function intentar() {
      const letra = document.getElementById("letra").value.toLowerCase();
      document.getElementById("letra").value = "";

      if (!letra || letra.length !== 1) return;
      if (palabraSecreta.includes(letra)) {
        palabraSecreta.split("").forEach((l, i) => {
          if (l === letra) palabraGuiones[i] = letra;
        });
      } else {
        intentosRestantes--;
      }

      document.getElementById("palabra").textContent = palabraGuiones.join(" ");
      document.getElementById("intentos").textContent = intentosRestantes;

      // Cambiar imagen según intentos
      const imagenes = [
        "https://cdn-icons-png.flaticon.com/512/685/685655.png",
        "https://cdn-icons-png.flaticon.com/512/685/685649.png",
        "https://cdn-icons-png.flaticon.com/512/685/685652.png",
        "https://cdn-icons-png.flaticon.com/512/685/685653.png",
        "https://cdn-icons-png.flaticon.com/512/685/685654.png",
        "https://cdn-icons-png.flaticon.com/512/685/685656.png",
        "https://cdn-icons-png.flaticon.com/512/685/685657.png"
      ];
      document.getElementById("imagenAhorcado").src = imagenes[6 - intentosRestantes];

      if (!palabraGuiones.includes("_")) {
        document.getElementById("mensaje").textContent = "¡Ganaste! 🎉";
      } else if (intentosRestantes <= 0) {
        document.getElementById("mensaje").textContent = "Perdiste 😢 La palabra era: " + palabraSecreta;
      }
    }

    nuevoJuego();
  </script>

</body>
</html>
