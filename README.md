# Task002
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Random Quote Generator</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="quote-app">
    <h1>Random Quote Generator</h1>
    <p id="quoteText">Click the button to generate a quote!</p>
    <p id="quoteAuthor"></p>
    <button onclick="generateQuote()">New Quote</button>
    <button onclick="shareOnTwitter()">Share on Twitter</button>
  </div>

  <script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background-color: #f0f4f8;
}

.quote-app {
  text-align: center;
  max-width: 400px;
  padding: 20px;
  border-radius: 10px;
  background-color: #ffffff;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

h1 {
  color: #333;
}

#quoteText {
  font-size: 1.2em;
  color: #555;
  margin: 20px 0;
}

#quoteAuthor {
  font-size: 1em;
  color: #888;
  margin: 10px 0;
}

button {
  padding: 10px 20px;
  margin: 10px;
  font-size: 1em;
  cursor: pointer;
  border: none;
  border-radius: 5px;
}

button:hover {
  background-color: #ddd;
}
// Array of quotes
const quotes = [
  { text: "The only limit to our realization of tomorrow is our doubts of today.", author: "Franklin D. Roosevelt" },
  { text: "Do not wait to strike till the iron is hot; but make it hot by striking.", author: "William Butler Yeats" },
  { text: "The best way to predict the future is to invent it.", author: "Alan Kay" },
  { text: "Whether you think you can or you think you can’t, you’re right.", author: "Henry Ford" },
  { text: "Success usually comes to those who are too busy to be looking for it.", author: "Henry David Thoreau" }
];

// Function to generate a random quote
function generateQuote() {
  const randomIndex = Math.floor(Math.random() * quotes.length);
  const quote = quotes[randomIndex];
  
  // Display the quote and author
  document.getElementById("quoteText").textContent = quote.text;
  document.getElementById("quoteAuthor").textContent = `– ${quote.author}`;
}

// Function to share quote on Twitter
function shareOnTwitter() {
  const quoteText = document.getElementById("quoteText").textContent;
  const quoteAuthor = document.getElementById("quoteAuthor").textContent;
  
  // Create tweet text with URL encoding
  const tweet = `${quoteText} ${quoteAuthor}`;
  const tweetUrl = `https://twitter.com/intent/tweet?text=${encodeURIComponent(tweet)}`;
  
  // Open Twitter share URL in a new tab
  window.open(tweetUrl, "_blank");
}

// Initialize with a random quote
generateQuote();
# Output
Initial Screen: Shows the title, placeholder text, and buttons.
Click "New Quote":
Quote area updates with a new random quote and author.
Example:
"Do not wait to strike till the iron is hot; but make it hot by striking." – William Butler Yeats
Click "Share on Twitter":
Twitter opens in a new tab with a pre-filled tweet:
"Do not wait to strike till the iron is hot; but make it hot by striking." – William Butler Yeats
