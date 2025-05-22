<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' https://en.wikipedia.org; style-src 'self' 'unsafe-inline' https://fonts.googleapis.com; font-src https://fonts.gstatic.com; connect-src https://en.wikipedia.org;">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>The Great Zero - Knowledge Hub</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;600;900&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: linear-gradient(to bottom, #0f0c29, #302b63, #24243e);
      color: #fff;
      min-height: 100vh;
    }

    header {
      text-align: center;
      padding: 2rem;
    }

    header h1 {
      font-size: 3rem;
      background: linear-gradient(90deg, #00dbde, #fc00ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    header p {
      color: #ccc;
      margin-top: 0.5rem;
    }

    .search-section {
      text-align: center;
      margin-top: 2rem;
    }

    .search-section input {
      padding: 1rem;
      width: 70%;
      max-width: 500px;
      font-size: 1rem;
      border: none;
      border-radius: 30px;
      outline: none;
    }

    .search-section button {
      padding: 1rem 2rem;
      margin-left: 1rem;
      border: none;
      border-radius: 30px;
      background: linear-gradient(to right, #2575fc, #6a11cb);
      color: white;
      font-weight: bold;
      cursor: pointer;
      transition: transform 0.2s ease;
    }

    .search-section button:hover {
      transform: scale(1.05);
    }

    .result {
      max-width: 800px;
      margin: 3rem auto;
      background-color: rgba(255, 255, 255, 0.05);
      padding: 2rem;
      border-radius: 20px;
      backdrop-filter: blur(10px);
      box-shadow: 0 0 10px rgba(255, 255, 255, 0.1);
    }

    .result h2 {
      margin-bottom: 1rem;
      font-size: 2rem;
      color: #00dbde;
    }

    .result p {
      font-size: 1.1rem;
      line-height: 1.6;
    }

    .error-screen {
      max-width: 700px;
      margin: 5rem auto;
      text-align: center;
      background: rgba(255, 0, 0, 0.1);
      padding: 2rem;
      border-radius: 15px;
      display: none;
    }

    .error-screen h2 {
      color: #ff4d4d;
      font-size: 2rem;
      margin-bottom: 1rem;
    }

    .error-screen p {
      font-size: 1.2rem;
    }

    footer {
      text-align: center;
      padding: 2rem;
      color: #aaa;
    }
  </style>
</head>
<body>
  <header>
    <h1>The Great Zero</h1>
    <p>Explore the world's knowledge with a designer-crafted Wikipedia hub</p>
  </header>

  <section class="search-section">
    <input type="text" id="searchInput" placeholder="Search anything...">
    <button onclick="searchWikipedia()">Search</button>
  </section>

  <section class="result" id="resultSection" style="display: none;">
    <h2 id="resultTitle"></h2>
    <p id="resultSummary"></p>
  </section>

  <section class="error-screen" id="errorScreen">
    <h2>We're sorry</h2>
    <p>It looks like you're offline, not signed in, or this site is a demo sample.<br>
    Please check your internet connection, or register to access the full experience.<br>
    This site is not currently hosted live — it's a static preview only.</p>
  </section>

  <footer>
    &copy; 2025 The Great Zero — All rights reserved.
  </footer>

  <script>
    async function searchWikipedia() {
      const query = document.getElementById('searchInput').value.trim();
      const resultSection = document.getElementById('resultSection');
      const errorScreen = document.getElementById('errorScreen');
      resultSection.style.display = 'none';
      errorScreen.style.display = 'none';

      if (!query) return;

      const apiUrl = `https://en.wikipedia.org/api/rest_v1/page/summary/${encodeURIComponent(query)}`;

      try {
        const response = await fetch(apiUrl);
        if (!response.ok) throw new Error('Page not found');

        const data = await response.json();
        document.getElementById('resultTitle').textContent = data.title;
        document.getElementById('resultSummary').textContent = data.extract;
        resultSection.style.display = 'block';
      } catch (error) {
        errorScreen.style.display = 'block';
      }
    }
  </script>
</body>
</html>
