<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Jacques le Febure</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header>
    <h1>Jacques le Febure</h1>
    <p>Exclusive Retail for the Elegant. Price per T-Shirt: R4300</p>
  </header>

  <main>
    <section id="product">
      <h2>Product: Luxury T-Shirt</h2>
      <p>Price: <strong>R4300</strong></p>
      <img src="tshirt.jpg" alt="Luxury T-Shirt" id="product-img">
    </section>

    <section id="comments">
      <h2>Customer Comments</h2>
      <div id="comments-list"></div>

      <h3>Leave a Comment</h3>
      <form id="comment-form">
        <input type="text" id="username" placeholder="Your Name" required>
        <textarea id="comment" placeholder="Write your comment here..." required></textarea>
        <button type="submit">Post Comment</button>
      </form>
    </section>
  </main>

  <footer>
    <p>&copy; 2024 Jacques le Febure</p>
  </footer>

  <script src="scripts.js"></script>
</body>
</html>

body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f5f5f5;
  color: #333;
}

header {
  background-color: #333;
  color: #fff;
  padding: 20px;
  text-align: center;
}

h1 {
  margin: 0;
}

main {
  padding: 20px;
}

#product {
  text-align: center;
}

#product-img {
  width: 300px;
  height: auto;
  margin: 20px 0;
}

#comments {
  margin-top: 40px;
}

#comments-list {
  background-color: #fff;
  padding: 10px;
  border-radius: 5px;
  margin-bottom: 20px;
}

#comment-form {
  display: flex;
  flex-direction: column;
}

#comment-form input,
#comment-form textarea {
  margin-bottom: 10px;
  padding: 10px;
  font-size: 16px;
}

#comment-form button {
  padding: 10px;
  background-color: #333;
  color: #fff;
  border: none;
  cursor: pointer;
  font-size: 16px;
}

#comment-form button:hover {
  background-color: #555;
}

footer {
  text-align: center;
  padding: 10px;
  background-color: #333;
  color: #fff;
}

document.getElementById('comment-form').addEventListener('submit', function (e) {
  e.preventDefault();

  const username = document.getElementById('username').value.trim();
  const comment = document.getElementById('comment').value.trim();

  if (username && comment) {
    const commentList = document.getElementById('comments-list');
    
    const newComment = document.createElement('div');
    newComment.classList.add('comment');
    newComment.innerHTML = `<strong>${username}</strong>: ${comment}`;
    
    commentList.appendChild(newComment);

    // Clear form inputs
    document.getElementById('username').value = '';
    document.getElementById('comment').value = '';
  }
});
