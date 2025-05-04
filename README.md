
<!DOCTYPE html>
<html>
<head>
  <title>Interactive GEC Image</title>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://cdn.jsdelivr.net/npm/viewerjs@1.11.5/dist/viewer.min.css" rel="stylesheet"/>
  <style>
    body {
      background-color: #b0e0e6;
      text-align: center;
      font-family: Arial, sans-serif;
    }
    .image-container {
      display: inline-block;
      max-width: 90%;
      margin-top: 30px;
      border: 3px solid #333;
    }
    .image-container img {
      width: 100%;
      height: auto;
      cursor: zoom-in;
    }
    #label {
      font-weight: bold;
      margin-top: 30px;
      display: block;
    }
    input[type="text"] {
      width: 300px;
      height: 25px;
      font-size: 16px;
    }
    .verify-btn {
      background-color: pink;
      padding: 10px 20px;
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
      border: none;
      cursor: pointer;
      box-shadow: 4px 4px 0px black;
    }
    #message {
      margin-top: 10px;
      font-size: 16px;
      font-weight: bold;
      color: red;
    }
  </style>
</head>
<body>

  <div class="image-container" id="imageViewer">
    <img src="gec-building.jpg" alt="GEC Campus">
  </div>

  <div id="label">
    Enter 10-digit Reg. Number + DOB (ddmmyy)
    <input type="text" id="inputField" placeholder="">
  </div>

  <div id="message"></div>

  <button class="verify-btn" onclick="validateInput()">Verify</button>

  <!-- Viewer.js Script -->
  
  <script>
   
 

    // Validation logic
    function validateInput() {
      const input = document.getElementById('inputField').value.trim();
      const pattern = /^\d{10}\d{8}$/;  // 10-digit reg + 6-digit DOB
      const messageDiv = document.getElementById('message');

      if (pattern.test(input)) {
        window.location.href = "gec1.html";
      } else {
        messageDiv.textContent = "Access Denied";
        messageDiv.style.color = "red";
      }
    }
  </script>

</body>
</html>
