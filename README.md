<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Letreiro Interativo</title>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700&display=swap" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/typed.js@2.0.12"></script>
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(135deg, #000000, #1a1a1a);
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
    }

    .container {
      text-align: center;
      cursor: pointer;
    }

    .write {
      font-family: 'Orbitron', sans-serif;
      font-size: 60px;
      padding: 20px;
      border-radius: 10px;
      transition: color 0.5s ease;
      text-shadow: 0 0 10px #fff;
    }
  </style>
</head>
<body>
  <div class="container">
    <span class="write"></span>
  </div>

  <audio id="clickSound" src="https://www.soundjay.com/button/sounds/button-16.mp3" preload="auto"></audio>

  <script>
    const frases = [
      "🎉 Bem-vindo ao letreiro animado!",
      "💡 Criatividade em movimento!",
      "🚀 Obrigado por visitar, Teobaldo!",
      "✨ Brilhando como nunca!"
    ];

    const cores = ["#00ffe7", "#ff00c8", "#ffd700", "#00ff88"];
    let corAtual = 0;
    let animacaoAtiva = true;

    const typed = new Typed(".write", {
      strings: frases,
      typeSpeed: 50,
      backSpeed: 30,
      backDelay: 1500,
      loop: true,
      onStringTyped: () => {
        document.getElementById("clickSound").play();
        corAtual = (corAtual + 1) % cores.length;
        document.querySelector(".write").style.color = cores[corAtual];
        document.querySelector(".write").style.textShadow = `0 0 20px ${cores[corAtual]}`;
      }
    });

    document.querySelector(".container").addEventListener("click", () => {
      if (animacaoAtiva) {
        typed.stop();
      } else {
        typed.start();
      }
      animacaoAtiva = !animacaoAtiva;
    });
  </script>
</body>
</html>