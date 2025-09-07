<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Loja com Botões Animados</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #000000, #1a1a1a, #333333, #000000, #fdd835);
      background-size: 400% 400%;
      animation: animarFundo 12s ease infinite;
      padding: 20px;
    }

    @keyframes animarFundo {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    .botoes-container {
      display: grid;
      grid-template-columns: 1fr; /* sempre uma coluna */
      gap: 20px;
      width: 100%;
      max-width: 500px;
    }

    .botao {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 15px;
      padding: 2rem;
      font-size: 26px;
      font-weight: bold;
      color: #fff;
      background: #000;
      border: 2px solid #fdd835;
      border-radius: 50px;
      cursor: pointer;
      position: relative;
      overflow: hidden;
      transition: all 0.3s ease;
      height: 120px;
      text-align: center;
    }

    .botao i {
      font-size: 2em;
      color: #fdd835; /* cor inicial */
      transition: transform 0.3s ease, color 0.3s ease;
    }

    /* animação "crescer e subir suavemente" */
    @keyframes growUp {
      0% { transform: scale(1) translateY(0); }
      50% { transform: scale(1.4) translateY(-10px); }
      100% { transform: scale(1) translateY(0); }
    }

    .botao:hover i {
      animation: growUp 0.5s ease forwards;
      color: #000; /* ícone fica preto no hover */
    }

    .botao::before {
      content: "";
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: rgba(253, 216, 53, 0.3);
      transition: left 0.4s ease;
    }

    .botao:hover::before {
      left: 100%;
    }

    .botao:hover {
      color: #000;
      background: #fdd835;
      box-shadow: 0 0 25px #fdd835;
      transform: scale(1.08);
    }

    /* Celulares: botões ainda maiores */
    @media (max-width: 768px) {
      .botao {
        font-size: 28px;
        padding: 2.2rem;
        height: 140px;
      }
      .botao i {
        font-size: 2.2em;
      }
    }

  </style>
</head>
<body>
  <div class="botoes-container">
    <button class="botao"><i class="fa-brands fa-apple"></i> iPhone</button>
    <button class="botao"><i class="fa-brands fa-android"></i> Samsung</button>
    <button class="botao"><i class="fa-solid fa-mobile-screen"></i> Xiaomi</button>
    <button class="botao"><i class="fa-solid fa-headphones"></i> Fone de Ouvido</button>
    <button class="botao"><i class="fa-solid fa-beer-mug-empty"></i> Copo Stanley</button>
  </div>
</body>
</html>
