<!DOCTYPE html>
<html>
<head>
  <title>Content Management Tool</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 10px;
    }

    h1 {
      margin-bottom: 10px;
    }

    form {
      margin-bottom: 10px;
    }

    label {
      display: block;
      margin-bottom: 10px;
    }

    textarea, input[type="text"] {
      width: 100%;
      padding: 5px;
      margin-bottom: 10px;
    }

    input[type="submit"] {
      padding: 10px 20px;
      background-color: #28bd2f;
      color: #181f21;
      border: none;
      cursor: pointer;
    }

    #detailsContainer {
      margin-top: 30px;
    }

    #detailsContainer h1 {
      font-size: 24px;
      margin-bottom: 10px;
    }

    #detailsContainer h2 {
      font-size: 18px;
      margin-bottom: 5px;
    }

    #detailsContainer p {
      margin-bottom: 10px;
    }

    #detailsContainer img {
      max-width: 100%;
      margin-bottom: 10px;
    }
  </style>
  <script>
    // Access the form and register the form submission event
    document.addEventListener('DOMContentLoaded', function() {
      var form = document.querySelector('#blogForm');
      form.addEventListener('submit', function(event) {
        event.preventDefault(); // Prevent the form from submitting

        // Retrieve the form values
        var title = document.querySelector('#title').value;
        var content = document.querySelector('#content').value;
        var image = document.querySelector('#image').value;
        var video = document.querySelector('#video').value;

        // Display the filled details on the webpage
        var detailsContainer = document.querySelector('#detailsContainer');
        detailsContainer.innerHTML = `
          <h1>Blog Details</h1>
          <h2>Title: ${title}</h2>
          <p>Content: ${content}</p>
          <img src="${image}" alt="Blog Image">
          <p>Video URL: ${video}</p>
        `;
      });
    });
  </script>
</head>
<body>
  <h1>Content Management Tool</h1>
  <form id="blogForm">
    <label for="title">Title:</label>
    <input type="text" id="title" name="title">

    <label for="content">Content:</label>
    <textarea id="content" name="content" rows="4"></textarea>

    <label for="image">Image:</label>
    <input type="text" id="image" name="image">

    <label for="video">Video URL:</label>
    <input type="text" id="video" name="video">

    <input type="submit" value="Create Blog">
  </form>

  <div id="detailsContainer"></div>
</body>
</html>
