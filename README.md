<html lang="en">
<head>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Native Gaming - Latest Video Game Updates</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #121212;
            color: white;
            text-align: center;
        }
        header {
            background: #1f1f1f;
            padding: 20px;
        }
        .logo img {
            width: 200px;
            margin: 20px auto;
            display: block;
        }
        .content {
            width: 80%;
            margin: 20px auto;
            padding: 20px;
            background: #222;
            border-radius: 10px;
        }
        .video {
            margin: 20px 0;
        }
        .video iframe {
            width: 100%;
            height: 315px;
            border: none;
        }
        .updates ul {
            list-style-type: none;
            padding: 0;
        }
        .updates li {
            background: #333;
            padding: 10px;
            margin: 5px 0;
            border-radius: 5px;
        }
        .social-links {
            margin: 20px 0;
        }
        .social-links a {
            color: #1e90ff;
            text-decoration: none;
            margin: 0 10px;
            font-size: 18px;
        }
        footer {
            padding: 10px;
            background: #1f1f1f;
            margin-top: 20px;
        }
    </style>
    <script>
        async function fetchGamingNews() {
            const apiKey = "8eaae37625cb4a03accbfdc0fd8414ae";
            const url = `https://newsapi.org/v2/everything?q=video+games&sortBy=publishedAt&apiKey=${apiKey}`;

            try {
                const response = await fetch(url);
                if (!response.ok) {
                    throw new Error("Failed to fetch news");
                }
                const data = await response.json();
                const newsList = document.getElementById("news-list");

                newsList.innerHTML = ""; // Clear previous news
                data.articles.slice(0, 5).forEach(article => {
                    const listItem = document.createElement("li");
                    listItem.innerHTML = `<a href="${article.url}" target="_blank" style="color: #1e90ff; text-decoration: none;">
                        ${article.title}
                    </a>`;
                    newsList.appendChild(listItem);
                });
            } catch (error) {
                console.error("Error fetching news:", error);
                document.getElementById("news-list").innerHTML = "<li>Failed to load news.</li>";
            }
        }

        window.onload = fetchGamingNews; // Load news when the page loads
    </script>
</head>
<body>

    <header>
        <h1>The Native Gaming</h1>
        <div class="logo">
            <img src="A_stunning_4D-style_minimalistic_gaming_logo_with_.png" alt="Gaming Logo">
        </div>
    </header>

    <div class="content">
        <h2>Latest Gaming Videos</h2>
        <div class="video">
            <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" allowfullscreen></iframe>
        </div>
        <div class="video">
            <iframe src="https://www.youtube.com/embed/3sJfTtzqNFg" allowfullscreen></iframe>
        </div>

        <h2>Latest Gaming News</h2>
        <ul id="news-list">
            <li>Loading latest news...</li>
        </ul>
    </div>

    <div class="social-links">
        <h2>Follow Me</h2>
        <a href="https://linktr.ee/roosterb25" target="_blank">Twitch & YouTube</a>
    </div>

    <footer>
        &copy; 2025 The Native Gaming | All Rights Reserved
    </footer>

</body>
</html>
