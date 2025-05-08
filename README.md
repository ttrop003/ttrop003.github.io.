<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <title>ถึงคนที่ฉันรัก</title>
  <style>
    body {
      margin: 0;
      background: #ffeef0;
      overflow: hidden;
      font-family: 'Prompt', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
    }
    .heart {
      width: 100px;
      height: 90px;
      position: relative;
      background: red;
      transform: rotate(-45deg);
      animation: pulse 1s infinite;
    }
    .heart::before,
    .heart::after {
      content: "";
      width: 100px;
      height: 90px;
      position: absolute;
      background: red;
      border-radius: 50%;
    }
    .heart::before {
      top: -50px;
      left: 0;
    }
    .heart::after {
      left: 50px;
      top: 0;
    }
    @keyframes pulse {
      0% { transform: scale(1) rotate(-45deg); }
      50% { transform: scale(1.1) rotate(-45deg); }
      100% { transform: scale(1) rotate(-45deg); }
    }
    .floating-heart {
      position: absolute;
      width: 15px;
      height: 15px;
      background-color: pink;
      transform: rotate(45deg);
      animation: float 4s linear infinite;
      border-radius: 50% 50% 0 0;
      opacity: 0.8;
    }
    @keyframes float {
      0% {
        bottom: 0;
        opacity: 1;
      }
      100% {
        bottom: 100%;
        opacity: 0;
      }
    }
    h1 {
      color: #d1003f;
      margin-top: 20px;
      font-size: 24px;
    }
  </style>
</head>
<body>
  <div class="heart"></div>
  <h1>ฉันรักเธอในทุกฐานะ 💌</h1>

  <script>
    // สร้างหัวใจลอย
    setInterval(() => {
      const heart = document.createElement('div');
      heart.className = 'floating-heart';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.backgroundColor = ['#ff6699', '#ff3366', '#ff99cc'][Math.floor(Math.random() * 3)];
      heart.style.width = '15px';
      heart.style.height = '15px';
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 4000);
    }, 300);
  </script>
</body>
</html>
