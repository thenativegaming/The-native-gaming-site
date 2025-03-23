<!DOCTYPE html>
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
            const apiKey = "8eaae37625cb4a03accbfdc0fd8414ae"; // Use your actual API key here
            const url = `https://newsapi.org/v2/everything?q=video+games&sortBy=publishedAt&apiKey=${apiKey}`;

            try {
                const response = await fetch(url);
                if (!response.ok) {
                    throw new Error("Failed to fetch news");
                }
                const data = await response.json();
                const newsList = document.getElementById("news-list");

                newsList.innerHTML = ""; // Clear previous news

                // Check if there are articles
                if (data.articles.length === 0) {
                    newsList.innerHTML = "<li>No recent gaming news available.</li>";
                } else {
                    // Display the first 5 latest articles
                    data.articles.slice(0, 5).forEach(article => {
                        const listItem = document.createElement("li");
                        listItem.innerHTML = `<a href="${article.url}" target="_blank" style="color: #1e90ff; text-decoration: none;">
                            ${article.title}
                        </a>`;
                        newsList.appendChild(listItem);
                    });
                }
            } catch (error) {
                console.error("Error fetching news:", error);
                document.getElementById("news-list").innerHTML = "<li>Failed to load news.</li>";
            }
        }

        // Update the news every 24 hours (86,400,000 ms)
        setInterval(fetchGamingNews, 86400000); // 24 hours in milliseconds

        // Run the fetch function when the page loads
        window.onload = fetchGamingNews;
    </script>
</head>
<body>

    <header>
        <h1>The Native Gaming</h1>
        <div class="logo">
            <!-- Replace with your logo image -->
            <img src="A_stunning_4D-style_minimalistic_gaming_logo_with_.png" alt="Gaming Logo">
        </div>
    </header>

    <div class="content">
        <h2>Latest Gaming Videos</h2>
        <div class="video">
            <!-- Replace with actual gaming trailer link -->
            <iframe src="https://www.youtube.com/embed/3sJfTtzqNFg" allowfullscreen></iframe>
        </div>
        <div class="video">
            <!-- Another example gaming trailer -->
            <iframe src="https://www.youtube.com/embed/example_game_trailer" allowfullscreen></iframe>
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
