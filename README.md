<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>IA Júnior Martins</title>
  <style>
    /* Estilos gerais */
    html, body {
      margin: 0;
      padding: 0;
      height: 100%;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(to bottom right, #003300, #000000);
      color: #ffffff;
      text-align: center;
      padding: 50px 20px;
      height: 100%;
    }

    .logo {
      font-size: 36px;
      font-weight: bold;
      color: #00ffcc;
      margin-bottom: 40px;
      letter-spacing: 2px;
    }

    button {
      padding: 15px 40px;
      font-size: 22px;
      background-color: #00ffcc;
      color: #000;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    button:hover {
      background-color: #00ccaa;
    }

    /* Box de resultado */
    .sinal-box {
      margin-top: 50px;
      font-size: 28px;
      font-weight: bold;
      height: 100px;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: all 0.3s ease;
      color: white;
      white-space: pre-line;
    }

    /* Efeitos e animações */
    .buscando {
      color: #cccccc;
      animation: piscar 1s infinite;
    }

    @keyframes piscar {
      0% { opacity: 1; }
      50% { opacity: 0.3; }
      100% { opacity: 1; }
    }

    .azul {
      color: white;
      text-shadow: none;
      animation: none;
    }

    .vermelho {
      color: white;
      text-shadow: none;
      animation: none;
    }

    /* Estilo do iframe para exibir o site de apostas */
    .apostas-container {
      margin-top: 50px;
      width: 100%;
      height: 600px;
      border: none;
    }

    /* Responsividade */
    @media (max-width: 768px) {
      .logo {
        font-size: 28px;
      }
      button {
        font-size: 18px;
        padding: 12px 30px;
      }
      .sinal-box {
        font-size: 24px;
      }
      .apostas-container {
        height: 400px;
      }
    @media (max-width: 480px) {
      button {
        font-size: 16px;
        padding: 10px 20px;
      }
      .sinal-box {
        font-size: 20px;
      }
      .apostas-container {
        height: 350px;
      }
    }
  </style>
</head>
<body>

  <div class="logo">IA Júnior Martins</div>

  <!-- Exibe a senha -->
  <div id="conteudo">
    <button onclick="buscarSinal()">BUSCAR SINAL</button>
    <div class="sinal-box" id="resultado"></div>

    <iframe class="apostas-container" src="https://m.reals.bet.br/live-casino" title="Casa de Apostas Real's Bet" allowfullscreen></iframe>
  </div>

  <script>
    const senhaCorreta = "1234"; // Senha correta
    let isSenhaCorreta = false;

    // Função de verificação da senha
    const verificarSenha = () => {
      const senha = prompt("Digite a senha para acessar o conteúdo:");

      if (senha === senhaCorreta) {
        document.getElementById("conteudo").style.display = "block"; // Exibe o conteúdo
        isSenhaCorreta = true;
      } else {
        alert("Senha incorreta. Acesso negado.");
      }
    };

    // Função para buscar o sinal
    function buscarSinal() {
      const resultadoDiv = document.getElementById('resultado');
      resultadoDiv.textContent = "Buscando entrada...";
      resultadoDiv.classList.add('buscando');
      resultadoDiv.classList.remove('azul', 'vermelho');

      setTimeout(() => {
        const sorteio = Math.random() < 0.5 ? 'azul' : 'vermelho';

        if (sorteio === 'azul') {
          resultadoDiv.textContent = "🔵PLAYER - PROBABILIDADE SEM GALE🎯";
          resultadoDiv.classList.add('azul');
        } else {
          resultadoDiv.textContent = "🔴BANKER - PROBABILIDADE SEM GALE🎯";
          resultadoDiv.classList.add('vermelho');
        }
      }, 2000);
    }

    window.onload = verificarSenha;
  </script>

</body>
</html>
    
