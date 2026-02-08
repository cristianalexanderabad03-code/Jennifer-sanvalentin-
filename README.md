<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>San Valentín 💘</title>
  <style>
    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: url('fondo.png') no-repeat center center fixed;
      background-size: cover;
      font-family: Arial, sans-serif;
    }

    .card {
      background: rgba(255, 255, 255, 0.9);
      padding: 60px;
      border-radius: 30px;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.25);
      max-width: 560px;
      width: 90%;
    }

    h1 {
      color: #e63946;
      font-size: 32px;
      margin-bottom: 15px;
    }

    #mensaje {
      font-size: 20px;
      color: #555;
      min-height: 28px;
      margin: 10px 0;
    }

    img {
      width: 100%;
      max-width: 320px;
      margin: 15px auto;
      display: none;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 25px;
      margin-top: 20px;
    }

    button {
      font-size: 20px;
      padding: 14px 36px;
      border: none;
      border-radius: 40px;
      cursor: pointer;
      transition: transform 0.3s;
    }

    #si {
      background-color: #e63946;
      color: white;
      font-size: 22px;
    }

    #no {
      background-color: #adb5bd;
      color: black;
    }

    #final {
      display: none;
      margin-top: 20px;
    }

    #final h2 {
      color: #e63946;
      margin-top: 10px;
    }
  </style>
</head>
<body>

  <audio id="musica" autoplay loop>
    <source src="music.mp3" type="audio/mpeg">
  </audio>

  <div class="card">
    <h1>¿Quieres ser mi San Valentín, mi Jennifer bebecita? 💘</h1>
    <p id="mensaje"></p>
    <img id="meme" src="" alt="imagen">
    <div class="buttons">
      <button id="si" onclick="aceptar()">Sí</button>
      <button id="no" onclick="rechazar()">No</button>
    </div>
    <div id="final">
      <img src="minion.png" alt="Minion feliz" style="display:block;">
      <h2>💛 ¡Ahora soy tuyo y tu cerdita! 💛</h2>
    </div>
  </div>

  <script>
    let escalaSi = 1;
    let clicsNo = 0;

    const mensajes = [
      "¿Segura bebecita? 🥺",
      "Piénsalo bien 💔",
      "Elige otra vez pofa 😢",
      "No me rompas el corazón 😭",
      "Última oportunidad por mi papoi💘"
    ];

    const imagenesNo = [
      "no1.png",
      "no2.png",
      "no3.png",
      "no4.png"
    ];

    function rechazar() {
      const mensaje = document.getElementById("mensaje");
      const meme = document.getElementById("meme");
      const botonSi = document.getElementById("si");
      const botonNo = document.getElementById("no");

      mensaje.textContent = mensajes[clicsNo % mensajes.length];
      meme.src = imagenesNo[clicsNo % imagenesNo.length];
      meme.style.display = "block";

      escalaSi += 0.3;
      botonSi.style.transform = `scale(${escalaSi})`;

      clicsNo++;
      if (clicsNo >= 5) {
        botonNo.style.display = "none";
      }
    }

    function aceptar() {
      document.querySelector(".buttons").style.display = "none";
      document.getElementById("mensaje").style.display = "none";
      document.getElementById("meme").style.display = "none";
      document.getElementById("final").style.display = "block";
    }
  </script>

</body>
</html>
