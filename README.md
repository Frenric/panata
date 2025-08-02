<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Panata Lyrics with Music</title>
  <style>
    body {
      background-color: #000;
      color: #00ffee;
      font-family: 'Courier New', monospace;
      font-size: 28px;
      padding: 40px;
      text-align: center;
    }

    #lyrics {
      white-space: pre-wrap;
      border-right: 2px solid #00ffee;
      animation: blink 0.5s infinite;
      margin-top: 30px;
      text-align: left;
    }

    @keyframes blink {
      0%, 100% { border-color: #00ffee; }
      50% { border-color: transparent; }
    }

    button {
      background-color: #00ffee;
      color: #000;
      border: none;
      padding: 12px 24px;
      font-size: 18px;
      cursor: pointer;
      border-radius: 10px;
      font-weight: bold;
      margin-bottom: 20px;
    }

    button:hover {
      background-color: #00ccbb;
    }
  </style>
</head>
<body>

  <button onclick="startMusic()">▶ Play</button>
  <audio id="bgMusic" src="panata.mp3"></audio>

  <div id="lyrics"></div>

  <script>
    const lyrics = `Litrato man natin ay kumupas
Ikaw aking noon, ngayon, at bukas
Kung paboritong kuwento nati'y magwakas
Ay uulitin kong ikuwento bukas
Sa pagdating ay siyang ating
Buong pusong salubungin
'Di man ngayon tulad ng dati
Ang panata ko'y mananatili`;

    const speed = 160; // adjust if needed
    let i = 0;

    function typeLyrics() {
      if (i < lyrics.length) {
        document.getElementById("lyrics").innerHTML += lyrics.charAt(i);
        i++;
        setTimeout(typeLyrics, speed);
      }
    }

    function startMusic() {
      document.getElementById("bgMusic").play();
      typeLyrics();
    }
  </script>

</body>
</html>
