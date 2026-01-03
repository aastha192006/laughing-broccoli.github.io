KITNA THOUGHTFUL H NA YEHHH..(hsna toh bilkul bhi mtt) 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>   OPEN WHEN LETTERS  </title>
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: lavender;
      margin: 0;
      padding: 0;
    }
 
    h1 {
      text-align: center;
      color: plum;
      margin: 24px 0 4px;

    }
     #app {
      max-width: 900px;
      margin: 0 auto;
      background: rgba(255,255,255,0.9);
      border-radius: 16px;
      box-shadow: 0 0 24px #fda08555;
      padding: 30px 20px;
      min-height: 70vh;
    }

    .container {
      display: flex;
      flex-wrap: wrap;
      gap: 24px;
      justify-content: center; 
      align-items: center;  
      width: 100%; 
      
      margin-bottom: 30px;
    }

    .card {
      background: lavenderblush;
      box-shadow: 0 4px 16px rgba(0,0,0,0.12);
      border-radius: 12px;
      width: 200px;
      transition: transform 0.3s, box-shadow 0.3s;
      padding: 12px;
      text-align: center;
      overflow: hidden;
    }

    .card:hover {
      transform: scale(1.05);
      box-shadow: 0 0 24px rgba(0,0,0,0.18);
    }

    .card img {
      width: 100%;
      border-radius:8px;
      margin-bottom: 8px;
      height: 182px;
      object-fit: cover;
    }

    .card h2 {
      text-align: center;
      color: #333;
      margin: 10px 0 5px;
    }

    .card p {
      text-align: center;
      color: #666;
      padding: 0 10px 10px;
    }

    .card button {
      display: block;
      text-align: center;
      margin: 10px auto;
      padding: 10px 20px;
      background-color: plum;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    .card button:hover {
      background-color: #8e4585;
    }

    /* Modal styles */
    .modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.7);  
      justify-content: center;
      align-items: center;
      z-index: 10;
    }

    .modal-content {
      background: white; 
      padding: 20px;
      border-radius: 10px; 
      max-width: 80%;
      position: relative;
    }

    .modal-content iframe {
      width: 100%;
      height: 400px;
      border: none;
      border-radius: 8px;
    }

    .close-btn {
      position: absolute;
      top: 10px;
      right: 15px;
      font-size: 24px;
      color: #333;
      cursor: pointer;
    }

    canvas {
  position: fixed !important;
  z-index: 9999 !important;
  pointer-events: none;
}

    

    .wrapper {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-start;
      min-height: 100vh;
      width: 100%;
    }

    @media (max-width: 768px) {
      .container {
        flex-direction: column;
        align-items: center;
        gap: 15px;
      }
      .card {
        width: 90%;
        max-width: 320px;
      }
      .modal-content iframe {
        height: 300px;
      }
      h1 {
        font-size: 1.5em;
      }
      body {
        padding: 10px;
      }
    }

    @media (max-width: 480px) {
      .card {
        width: 95%;
      }
      .modal-content iframe {
        height: 250px;
      }
      h1 {
        font-size: 1.2em;
      }
      .card h2 {
        font-size: 1em;
      }
      .card p {
        font-size: 0.9em;
      }
    }
  </style>
</head>
<body>

  <div class="wrapper">
    <h1>-💌-OPEN WHEN MESSAGES-💌-</h1>

    <div class="container" id="recipeContainer">
      <!-- Cards will be injected here by JavaScript -->


    </div>
  </div>

  <!-- Modal -->
  <div class="modal" id="videoModal">
    <div class="modal-content">
      <span class="close-btn" onclick="closeModal()">&times;</span>
      <iframe id="videoFrame" src="" allowfullscreen></iframe>
    </div>
  </div>

  <script>
    const recipes = [
      {
        name: "open when you get this(since we both love cartoons)😄",
        description: "A collection of heartfelt messages to open at different times❤️.(isliye hasiyo mtt)!!!",
        image: "https://i.pinimg.com/736x/37/8e/c2/378ec2d0ec3528a0218cfce4277d1b5e.jpg",
        video: "https://player.vimeo.com/video/1151015697" 
      },
      {
        name: "open when you are sad🫂",
        description: "A reminder that it's okay to feel sad sometimes.",
        image: "https://i.pinimg.com/1200x/d7/52/2d/d7522d1a5953b0fae8e323d58710d5d1.jpg",
        video: "https://player.vimeo.com/video/1150406227"
      },
      {
        name: "open when you're lonely🥲",
        description: "but you'll never be alone.I'll be with from dusk till dawn 😎.",
        image: "https://i.pinimg.com/736x/1b/27/3e/1b273ef50512d9e07fb9d0d23af3e12c.jpg",
        video: "https://player.vimeo.com/video/1150413574"
      },
      {
        name: "open when you need motivation 💪",
        description: "A boost of motivation to help you through tough times.✌️",
        image: "https://i.pinimg.com/1200x/ce/31/30/ce31301bf40769ea5d70373efc83b9fc.jpg",

        video: "https://player.vimeo.com/video/1150404427"
      },
      {
        name: "open when you need a hug 🤗",
        description: "A virtual hug to remind you that you are loved.💗",
        image: "https://i.pinimg.com/736x/1e/55/75/1e557575364a61ed4731fd2b126de168.jpg",
        video: "https://player.vimeo.com/video/1150634482"
      },
      {
        name: "open when you're afraid of failing 😟",
        description: "Remember, failure is just a stepping stone to success.🌟",
        image: "https://i.pinimg.com/1200x/67/8a/ca/678aca6d77df8274cda5c1041757e8d5.jpg",
        video: "https://player.vimeo.com/video/1151011005"
      },
      {
        name: "open when you had a bad day",
        description: "A reminder that tomorrow is a new day.🌞 (9258910255 prr samprk karein or paaye ek haseen mauka apna mood acha krne ka)",
        image: "https://i.pinimg.com/1200x/a5/d7/21/a5d72127150cf4f5dbc674d807ff9d83.jpg",
        video: "https://player.vimeo.com/video/1105513154"
      },
      {
        name: "open whenever you feel like",  
        description: "bss lga ki yeh bhi add krna chahiye.💞",
        image: "https://i.pinimg.com/1200x/1c/83/55/1c835574b7926149349dd2e8bbbed05d.jpg",
        video: "https://player.vimeo.com/video/1150401518"
      },
      {
        name: "open when you question your existence",
        description: "you are special and your existence matters.💖",
        image: "https://i.pinimg.com/1200x/dd/a4/a7/dda4a74103828d06df0ef077d9fd6887.jpg",
        video: "https://player.vimeo.com/video/1151010647"
      },
      {
        name: "open when you feel confused about your life decisions",
        description: "trust yourself and your journey.🌈",
        image: "https://i.pinimg.com/1200x/a4/a4/77/a4a477e8715305d88d46a6bdb5d0e81e.jpg",
        video: "https://player.vimeo.com/video/1151010337"
      },
      {
        name: "open when you feel nobody loves you",
        description: "you are deeply loved and cherished by meee💘",
        image: "https://i.pinimg.com/736x/11/56/89/115689278adfa6c0bf82ee8696d5d5a7.jpg",
        video: "https://player.vimeo.com/video/1151009847"
      }

    ];

    const container = document.getElementById("recipeContainer");
    const videoModal = document.getElementById("videoModal");
    const videoFrame = document.getElementById("videoFrame");

    recipes.forEach(recipe => {
      const card = document.createElement("div");
      card.className = "card";
      card.innerHTML = `
        <img src="${recipe.image}" alt="${recipe.name}">
        <h2>${recipe.name}</h2>
        <p>${recipe.description}</p>
        <button onclick="openModal('${recipe.video}')">click me</button>
      `;
      container.appendChild(card);
    });

    function openModal(videoUrl) {
      videoFrame.src = videoUrl + "?autoplay=1";
      videoModal.style.display = "flex";
      confetti({
        shapes: ['text'],
        text: '❤️',
        particleCount: 100,
        spread: 70,
        colors: ['#ff0000', '#ff69b4', '#ffb6c1', '#ff1493', '#dc143c']
      });
    }

    function closeModal() {
      videoModal.style.display = "none";
      videoFrame.src = "";
    }

    // Optional: Close modal by clicking outside the content
    window.onclick = function(event) {
      if (event.target === videoModal) {
        closeModal();
      }
    };
  </script>
</body>
</html>
