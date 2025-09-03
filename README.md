# Minha-vida-

<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Site Motivacional</title>
<style>
  html, body {
    margin: 0;
    padding: 0;
    height: 100%;
    overflow-x: hidden;
    scroll-behavior: smooth;
    font-family: Arial, sans-serif;
    color: white;
    background: black;
  }

  section {
    position: relative;
    height: 100vh;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    opacity: 0;
    transition: opacity 1s ease-in-out;
  }

  section.active {
    opacity: 1;
  }

  .text-section {
    background: rgba(0, 0, 0, 0.5);
    padding: 20px;
    border-radius: 10px;
    max-width: 90%;
    animation: fadeIn 2s ease forwards;
  }

  h1 {
    font-size: 2rem;
    margin-bottom: 15px;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.7);
  }

  p {
    font-size: 1.5rem;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.7);
  }

  .arrow {
    font-size: 3rem;
    position: absolute;
    bottom: 20px;
    animation: bounce 1.5s infinite;
    opacity: 1;
    transition: opacity 0.5s ease;
  }

  @keyframes fadeIn {
    0% {opacity: 0; transform: translateY(20px);}
    100% {opacity: 1; transform: translateY(0);}
  }

  @keyframes bounce {
    0%, 100% {transform: translateY(0);}
    50% {transform: translateY(-15px);}
  }
</style>
</head>
<body>

  <!-- Seção 1 -->
  <section class="active" style="background-image: url('https://i.imgur.com/mO81FM5.jpg');">
    <div class="text-section">
      <h1>Vida eu sei que não está sendo fácil para você, mas tudo isso vai passar e só é uma fase.</h1>
      <p>Eu sei que você não está nada bem, mas com o tempo você vai melhorar. Eu te amo muito ⬇️</p>
    </div>
    <div class="arrow" id="arrow">⬇️</div>
  </section>

  <!-- Seção 2 -->
  <section style="background-image: url('https://i.imgur.com/XOvhPMq.jpg');">
    <div class="text-section">
      <h1>Não é justo você estar comigo nos momentos bons e ruins, e eu estar com você só nos bons.</h1>
      <p>Nos ruins eu te deixar sozinha? Agente é um casal e vamos passar tudo isso junto, minha princesa. Eu te amo muito e esse site é pra você ver uma pequena demonstração do meu amor.</p>
    </div>
  </section>

  <!-- Seção 3 -->
  <section style="background-image: url('https://i.imgur.com/Eh4WKpM.jpg');">
    <div class="text-section">
      <h1>💓❤️💝</h1>
    </div>
  </section>

<script>
  const sections = document.querySelectorAll('section');
  const arrow = document.getElementById('arrow');
  let currentIndex = 0;

  function showSection(index) {
    sections.forEach((sec, i) => {
      sec.classList.remove('active');
      if(i === index) sec.classList.add('active');
    });

    // Esconde a seta quando não estamos na primeira seção
    if(index !== 0){
      arrow.style.opacity = 0;
    } else {
      arrow.style.opacity = 1;
    }
  }

  window.addEventListener('wheel', function(event) {
    if(event.deltaY > 0){
      currentIndex = (currentIndex + 1) % sections.length;
      showSection(currentIndex);
    } else if(event.deltaY < 0){
      currentIndex = (currentIndex - 1 + sections.length) % sections.length;
      showSection(currentIndex);
    }
  });
</script>

</body>
</html>
