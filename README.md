<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Happy Birthday - 5 Pages</title>
<style>
  * {
    margin: 0; padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
  }
  body, html {
    height: 100%;
    overflow: hidden;
    background: linear-gradient(135deg, #ff6ec4, #7873f5);
    color: white;
    perspective: 1200px;
    position: relative;
  }
  .page {
    width: 100vw;
    height: 100vh;
    display: none;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 20px;
    text-align: center;
    background: rgba(255,255,255,0.1);
    backdrop-filter: blur(5px);
    transform-style: preserve-3d;
    transition: transform 1s ease, opacity 1s ease;
    backface-visibility: hidden;
    position: absolute;
    top: 0; left: 0;
    z-index: 1;
    opacity: 0;
    pointer-events: none;
  }
  .page.active {
    display: flex;
    transform: rotateY(0deg);
    opacity: 1;
    pointer-events: auto;
    z-index: 10;
  }
  .page.inactive-left {
    display: flex;
    transform: rotateY(-90deg);
    opacity: 0;
    pointer-events: none;
    z-index: 5;
  }
  .page.inactive-right {
    display: flex;
    transform: rotateY(90deg);
    opacity: 0;
    pointer-events: none;
    z-index: 5;
  }
  h1, p {
    /* Typing effect styles */
    white-space: nowrap;
    overflow: hidden;
    border-right: 3px solid rgba(255,255,255,0.75);
    animation: typing 3.5s steps(40, end), blink-caret 0.75s step-end infinite;
  }
  h1 {
    font-size: 2.2rem;
    margin-bottom: 20px;
    text-shadow: 0 0 15px #ff00ff;
  }
  p {
    font-size: 1.1rem;
    line-height: 1.5;
    max-width: 600px;
  }
  button {
    margin-top: 30px;
    padding: 12px 30px;
    font-size: 1.2rem;
    border: none;
    border-radius: 50px;
    cursor: pointer;
    background: linear-gradient(45deg, #ff00ff, #ff9900);
    color: white;
    box-shadow: 0 5px 15px rgba(0,0,0,0.3);
    transition: transform 0.3s ease;
  }
  button:hover {
    transform: scale(1.1);
  }
  svg.cake {
    width: 90vw;
    max-width: 320px;
    margin: 20px 0;
    cursor: pointer;
    transition: transform 0.3s ease;
    border-radius: 20px;
    animation: none; /* prevent typing effect on SVG */
    border-right: none;
  }
  svg.cake:active {
    transform: scale(0.95);
  }
  /* Balloon animation */
  .balloon {
    position: absolute;
    bottom: -100px;
    width: 50px;
    animation: float 5s infinite ease-in;
    border-radius: 50%;
  }
  @keyframes float {
    0% { transform: translateY(0); }
    100% { transform: translateY(-120vh); }
  }
  /* Typing keyframes */
  @keyframes typing {
    from { width: 0 }
    to { width: 100% }
  }
  @keyframes blink-caret {
    from, to { border-color: transparent }
    50% { border-color: rgba(255,255,255,0.75) }
  }

  /* Responsive Mobile Styles */
  @media (max-width: 480px) {
    .page {
      padding: 15px 10px;
      height: 100vh;
      width: 100vw;
    }
    h1 {
      font-size: 1.6rem;
      margin-bottom: 15px;
      white-space: normal; /* allow wrapping on small screens */
      border-right: none; /* remove typing border for better UX on mobile */
      animation: none; /* disable typing animation on mobile for readability */
      text-shadow: 0 0 10px #ff00ff;
    }
    p {
      font-size: 1rem;
      max-width: 90vw;
      white-space: normal;
      border-right: none;
      animation: none;
      line-height: 1.4;
    }
    button {
      font-size: 1rem;
      padding: 10px 20px;
      margin-top: 20px;
      border-radius: 30px;
      width: 100%;
      max-width: 300px;
    }
    svg.cake {
      width: 90vw;
      max-width: 280px;
      margin: 15px 0;
    }
    /* Reduce balloon size on mobile */
    .balloon {
      width: 35px;
      height: 45px;
    }
  }
</style>
</head>
<body>

<audio id="music" loop>
  <source src="https://cdn.pixabay.com/download/audio/2022/03/23/audio_d5a8e2567c.mp3?filename=birthday-song-11246.mp3" type="audio/mpeg" />
  Your browser does not support the audio element.
</audio>

<button id="playMusicBtn" style="position: fixed; top: 20px; right: 20px; z-index: 100; background: #ff3399; padding: 12px 20px; border-radius: 50px; border: none; cursor: pointer; color: white; box-shadow: 0 4px 10px rgba(0,0,0,0.3); display:none;">
  Play Music 🎵
</button>

<div id="page1" class="page active">
  <h1>🎉 Happy Birthday Fiza & Musfira 🎉</h1>
  <p>
    Wishing you endless joy, laughter, and dreams as sweet as cake! 🎂✨<br>
    May every moment of your special day be filled with happiness and warmth.<br>
    Celebrate with smiles, fun, and the company of loved ones.<br>
    Let this year bring you closer to your dreams and fill your heart with hope.<br>
    Keep shining bright and never stop believing in magic.<br>
    Here's to a fantastic year ahead full of love and success!
  </p>
  <button onclick="goToPage(2)">Next</button>
</div>

<div id="page2" class="page inactive-right">
  <h1>Crazy Birthday Wishes 🎉</h1>
  <p>
    Fiza & Musfira, you two are the double dose of joy in this world! 🎂✨<br>
    Today is all about laughter, crazy adventures, and unforgettable moments.<br>
    Embrace every crazy idea and live life with full enthusiasm.<br>
    May your days be colorful like a rainbow and your nights full of stars.<br>
    Keep dreaming big and reaching for the sky with courage and love.<br>
    Always remember you are loved beyond measure by all around you.<br>
    Here's to many more exciting journeys together!
  </p>
  <button onclick="goToPage(3)">Next</button>
  <button onclick="goToPage(1, 'left')">Back</button>
</div>

<div id="page3" class="page inactive-right">
  <h1>Time to Cut the Cake 🎂</h1>
  <svg class="cake" onclick="cutCake()" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 300 300" aria-label="Birthday Cake" role="img">
    <rect x="50" y="150" width="200" height="100" rx="20" ry="20" fill="#f9c5d1" stroke="#d95f73" stroke-width="4"/>
    <rect x="70" y="120" width="160" height="40" rx="15" ry="15" fill="#fcd5ce" stroke="#d95f73" stroke-width="3"/>
    <rect x="90" y="90" width="120" height="40" rx="10" ry="10" fill="#f8e1e7" stroke="#d95f73" stroke-width="2"/>
    <path d="M70 120 Q80 140 90 120 T110 120 T130 120 T150 120 T170 120 T190 120 T210 120" fill="none" stroke="#ff6f91" stroke-width="6" stroke-linejoin="round"/>
    <rect x="140" y="50" width="20" height="40" fill="#ffb6b9" stroke="#d95f73" stroke-width="2" rx="3" ry="3"/>
    <path d="M150 50 Q155 40 160 50 Q155 45 150 50" fill="#ffcc33" stroke="#ff9900" stroke-width="1"/>
    <ellipse cx="150" cy="260" rx="110" ry="25" fill="#ffe3ec" stroke="#d95f73" stroke-width="3"/>
    <circle cx="90" cy="160" r="4" fill="#ff4477"/>
    <circle cx="120" cy="180" r="3" fill="#ff7744"/>
    <circle cx="180" cy="190" r="5" fill="#44ff77"/>
    <circle cx="160" cy="160" r="3" fill="#4477ff"/>
    <circle cx="210" cy="170" r="4" fill="#ff44aa"/>
    <text x="150" y="280" font-family="Poppins, sans-serif" font-size="18" fill="#d95f73" text-anchor="middle" font-weight="bold">Happy Birthday!</text>
  </svg>
  <p>
    The moment you've all been waiting for—cutting the cake! 🎂<br>
    Gather around and make a wish before slicing into this delicious treat.<br>
    May each slice bring happiness and sweet memories to share.<br>
    Celebrate every bite as a symbol of joy and togetherness.<br>
    Don’t forget to snap pictures of this magical moment.<br>
    Here's to many more cakes and celebrations ahead!
  </p>
  <button onclick="goToPage(4)">Next</button>
  <button onclick="goToPage(2, 'left')">Back</button>
</div>

<div id="page4" class="page inactive-right">
  <h1>🎈 Happy Birthday Again! 🎈</h1>
  <p>
    Once again, sending you warm birthday wishes filled with love and cheer!<br>
    May this year open doors to new opportunities and happiness.<br>
    Cherish every moment and keep your heart full of gratitude.<br>
    Surround yourself with positive vibes and inspiring people.<br>
    Believe in yourself and never stop chasing your dreams.<br>
    Here's to a year that’s brighter and better than ever before!<br>
  </p>
  <button onclick="goToPage(5)">Next</button>
  <button onclick="goToPage(3, 'left')">Back</button>
</div>

<div id="page5" class="page inactive-right">
  <h1>Celebrate & Enjoy! 🎉🎂</h1>
  <p>
    Thank you for being part of this special day and celebration.<br>
    Let’s create unforgettable memories filled with laughter and love.<br>
    Dance like no one’s watching and sing your heart out.<br>
    Appreciate every gift and every smile you receive.<br>
    The best is yet to come, so keep the party going!<br>
    Here’s to friendship, family, and joy that lasts forever.<br>
    Let’s make this birthday one for the books!
  </p>
  <button onclick="goToPage(1, 'left')">Start Over</button>
  <button onclick="goToPage(4, 'left')">Back</button>
</div>

<script>
  // Balloon confetti
  const colors = ['#ff4da6', '#ffb84d', '#ff6666', '#99e600', '#66ccff', '#cc99ff'];
  const balloonsCount = 15;
  for(let i = 0; i < balloonsCount; i++) {
    const balloon = document.createElement('div');
    balloon.className = 'balloon';
    balloon.style.left = Math.random() * 100 + 'vw';
    balloon.style.backgroundColor = colors[i % colors.length];
    balloon.style.width = '40px';
    balloon.style.height = '55px';
    balloon.style.bottom = '-60px';
    balloon.style.opacity = 0.8;
    balloon.style.animationDuration = (4 + Math.random() * 4) + 's';
    balloon.style.animationDelay = (Math.random() * 5) + 's';
    document.body.appendChild(balloon);
  }

  let currentPage = 1;
  const bgMusic = document.getElementById('music');
  const playMusicBtn = document.getElementById('playMusicBtn');

  // Try to autoplay music on load (most browsers block this)
  window.onload = () => {
    bgMusic.play().catch(() => {
      // Show play button if autoplay blocked
      playMusicBtn.style.display = 'block';
    });
  };

  // Play button click handler
  playMusicBtn.addEventListener('click', () => {
    document.getElementById("music").play();
    playMusicBtn.style.display = 'none';
  });

  function goToPage(num, direction = 'right') {
    if (num === currentPage) return;

    const current = document.getElementById('page' + currentPage);
    const next = document.getElementById('page' + num);

    // Reset all pages before transition
    document.querySelectorAll('.page').forEach(page => {
      if (page !== current && page !== next) {
        page.classList.remove('active', 'inactive-left', 'inactive-right');
        page.style.display = 'none';

        // Reset typing animation by forcing reflow
        page.querySelectorAll('h1, p').forEach(el => {
          el.style.animation = 'none';
          void el.offsetWidth; // trigger reflow
          el.style.animation = null;
        });
      }
    });

    // Animate current page out
    if (direction === 'right') {
      current.classList.remove('active');
      current.classList.add('inactive-left');
    } else {
      current.classList.remove('active');
      current.classList.add('inactive-right');
    }

    // Animate next page in
    next.style.display = 'flex'; // Make sure visible to animate
    next.classList.remove('inactive-left', 'inactive-right');
    next.classList.add('active');

    // Restart typing animation on new page
    next.querySelectorAll('h1, p').forEach(el => {
      el.style.animation = 'none';
      void el.offsetWidth; // trigger reflow
      el.style.animation = null;
    });

    currentPage = num;
  }

  function cutCake() {
    alert("🎂 Yum! Cake is cut! 🎉");
  }
</script>

</body>
</html>
