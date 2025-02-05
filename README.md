# proyectoo
sanvalentin
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      background: linear-gradient(45deg, #ff6b6b, #ffd5d5);
      font-family: 'Arial', sans-serif;
      overflow: hidden;
    }
    
    .container {
      text-align: center;
      background: rgba(255, 255, 255, 0.95);
      padding: 2rem;
      border-radius: 20px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
      position: relative;
      max-width: 500px;
    }
    
    .heart-emoji {
      font-size: 80px;
      margin: 20px 0;
      animation: pulse 1.5s ease infinite;
      display: block;
    }
    
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.2); }
      100% { transform: scale(1); }
    }
    
    h1 {
      color: #ff4d6d;
      margin: 20px 0;
      font-size: 2.5em;
    }
    
    .message {
      color: #666;
      font-size: 1.2em;
      margin: 20px 0;
      line-height: 1.6;
      padding: 0 10px;
    }
    
    .buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
      margin-top: 30px;
    }
    
    .btn {
      padding: 15px 30px;
      font-size: 1.1em;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      transition: transform 0.3s ease;
    }
    
    .btn:hover {
      transform: scale(1.1);
    }
    
    .btn-yes {
      background: #ff4d6d;
      color: white;
    }
    
    .btn-no {
      background: #f8f9fa;
      color: #ff4d6d;
      border: 2px solid #ff4d6d;
    }
    
    .hearts-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: -1;
    }
    
    .floating-heart {
      position: absolute;
      font-size: 20px;
      animation: float-up 4s linear infinite;
      color: rgba(255, 77, 109, 0.3);
    }
    
    @keyframes float-up {
      0% {
        transform: translateY(100vh) rotate(0deg);
        opacity: 1;
      }
      100% {
        transform: translateY(-100px) rotate(360deg);
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <div class="hearts-bg" id="heartsBg"></div>
  
  <div class="container">
    <span class="heart-emoji">💖</span>
    <h1>¿Te gustaría ser mi San Valentín?</h1>
    <p class="message">
      Mi Tabata, este será nuestro primer San Valentín juntos, estoy tan feliz de pasar cada día más a tu lado y espero que tú también. Te amo y cada segundo de mi vida te amaré más y más <3.
    </p>
    <div class="buttons">
      <button class="btn btn-yes" onclick="showMessage('¡Sí!')">¡Sí!</button>
      <button class="btn btn-no" onclick="moveButton(this)">No</button>
    </div>
  </div>

  <script>
    function createFloatingHearts() {
      const heartsBg = document.getElementById('heartsBg');
      const heart = document.createElement('div');
      heart.innerHTML = '❤';
      heart.className = 'floating-heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (Math.random() * 2 + 3) + 's';
      heartsBg.appendChild(heart);
      
      setTimeout(() => {
        heart.remove();
      }, 4000);
    }

    setInterval(createFloatingHearts, 300);

    function moveButton(button) {
      const newX = Math.random() * (window.innerWidth - button.offsetWidth);
      const newY = Math.random() * (window.innerHeight - button.offsetHeight);
      button.style.position = 'fixed';
      button.style.left = newX + 'px';
      button.style.top = newY + 'px';
    }

    function showMessage(response) {
      alert('¡Qué felicidad! ❤ ¡Este será el mejor San Valentín!');
    }
  </script>
</body>
</html>
