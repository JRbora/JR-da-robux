html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Roblox Rewards — Demonstração</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 24px;
      color: white;
      background:
        radial-gradient(circle at top, #303b72, transparent 45%),
        linear-gradient(135deg, #101426, #171b35);
    }

    .card {
      width: 100%;
      max-width: 460px;
      padding: 30px;
      border: 1px solid rgba(255,255,255,.15);
      border-radius: 22px;
      background: rgba(20, 25, 52, .9);
      box-shadow: 0 20px 60px rgba(0,0,0,.35);
      text-align: center;
    }

    .logo {
      width: 76px;
      height: 76px;
      margin: 0 auto 16px;
      display: grid;
      place-items: center;
      border-radius: 18px;
      background: linear-gradient(135deg, #ff3d81, #7657ff);
      font-size: 38px;
      box-shadow: 0 10px 25px rgba(118,87,255,.35);
    }

    h1 {
      margin-bottom: 8px;
      font-size: 28px;
    }

    .subtitle {
      margin-bottom: 22px;
      color: #b9c0df;
      line-height: 1.5;
    }

    .notice {
      margin-bottom: 20px;
      padding: 12px;
      border-radius: 12px;
      color: #ffe9a8;
      background: rgba(255, 193, 7, .12);
      border: 1px solid rgba(255, 193, 7, .35);
      font-size: 13px;
      line-height: 1.4;
    }

    label {
      display: block;
      margin-bottom: 8px;
      text-align: left;
      font-weight: bold;
    }

    input, select {
      width: 100%;
      padding: 14px;
      margin-bottom: 16px;
      border: 1px solid #414a78;
      border-radius: 12px;
      outline: none;
      color: white;
      background: #11162c;
      font-size: 15px;
    }

    input:focus, select:focus {
      border-color: #8b7cff;
      box-shadow: 0 0 0 3px rgba(139,124,255,.15);
    }

    button {
      width: 100%;
      padding: 15px;
      border: none;
      border-radius: 12px;
      color: white;
      background: linear-gradient(135deg, #ff3d81, #7657ff);
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      transition: .2s;
    }

    button:hover {
      transform: translateY(-2px);
      filter: brightness(1.1);
    }

    .result {
      display: none;
      margin-top: 22px;
      padding: 18px;
      border-radius: 14px;
      background: rgba(255,255,255,.07);
      line-height: 1.6;
    }

    .avatar {
      width: 82px;
      height: 82px;
      margin: 0 auto 12px;
      display: grid;
      place-items: center;
      border-radius: 50%;
      background: linear-gradient(135deg, #ffc857, #ff7b54);
      font-size: 40px;
    }

    .result strong {
      color: #9f92ff;
    }

    .small {
      margin-top: 18px;
      color: #8f98bd;
      font-size: 12px;
    }
  </style>
</head>

<body>
  <main class="card">
    <div class="logo">🎁</div>

    <h1>Rewards Center</h1>
    <p class="subtitle">
      Faça uma simulação de recompensa para um jogador.
    </p>

    <div class="notice">
      Demonstração educativa: nenhum Robux, dinheiro, roupa ou item real será enviado.
    </div>

    <form id="rewardForm">
      <label for="nickname">Digite o nick</label>
      <input
        id="nickname"
        type="text"
        placeholder="Exemplo: Player123"
        maxlength="30"
        required
      />

      <label for="reward">Escolha uma recompensa</label>
      <select id="reward">
        <option value="100 Robux virtuais">100 Robux virtuais</option>
        <option value="500 Robux virtuais">500 Robux virtuais</option>
        <option value="Uma roupa demonstrativa">Uma roupa demonstrativa</option>
        <option value="Um item demonstrativo">Um item demonstrativo</option>
        <option value="Dinheiro virtual de demonstração">
          Dinheiro virtual de demonstração
        </option>
      </select>

      <button type="submit">Iniciar simulação</button>
    </form>

    <section class="result" id="result">
      <div class="avatar">🙂</div>
      <p>Jogador: <strong id="playerName"></strong></p>
      <p>Recompensa: <strong id="rewardName"></strong></p>
      <p style="margin-top: 10px;">
        Simulação concluída! Nenhum item real foi enviado.
      </p>
    </section>

    <p class="small">
      Protótipo escolar sem login, senha, códigos ou dados privados.
    </p>
  </main>

  <script>
    const form = document.getElementById("rewardForm");
    const result = document.getElementById("result");
    const nickname = document.getElementById("nickname");
    const reward = document.getElementById("reward");
    const playerName = document.getElementById("playerName");
    const rewardName = document.getElementById("rewardName");

    form.addEventListener("submit", function(event) {
      event.preventDefault();

      const nick = nickname.value.trim();

      if (!nick) {
        alert("Digite um nick para fazer a simulação.");
        return;
      }

      playerName.textContent = nick;
      rewardName.textContent = reward.value;
      result.style.display = "block";
      result.scrollIntoView({ behavior: "smooth" });
    });
  </script>
</body>
</html>
