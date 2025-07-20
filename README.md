# Age 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Age Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 50px;
      background-color: #f2f2f2;
    }
    .container {
      background: white;
      padding: 30px;
      max-width: 400px;
      margin: auto;
      border-radius: 10px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }
    input, button {
      padding: 10px;
      margin-top: 15px;
      width: 100%;
      font-size: 16px;
    }
    #result {
      margin-top: 20px;
      font-weight: bold;
      font-size: 20px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Age Calculator</h2>
    <label for="dob">Enter Your Date of Birth:</label><br />
    <input type="date" id="dob" /><br />
    <button onclick="calculateAge()">Calculate Age</button>
    <div id="result"></div>
  </div>

  <script>
    function calculateAge() {
      const dob = document.getElementById('dob').value;
      if (!dob) {
        alert('Please select your birth date');
        return;
      }
      const birthDate = new Date(dob);
      const today = new Date();
      let age = today.getFullYear() - birthDate.getFullYear();
      const m = today.getMonth() - birthDate.getMonth();
      if (m < 0 || (m === 0 && today.getDate() < birthDate.getDate())) {
        age--;
      }
      document.getElementById('result').innerText = `Your age is: ${age} years`;
    }
  </script>
</body>
</html>
