# Tracking
Website for track
<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Order Tracking</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f6f8;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .card {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      width: 100%;
      max-width: 420px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }
    h2 {
      text-align: center;
      margin-bottom: 20px;
    }
    input {
      width: 100%;
      padding: 10px;
      margin-bottom: 10px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      width: 100%;
      padding: 10px;
      background: #2563eb;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background: #1e40af;
    }
    .result {
      margin-top: 15px;
      padding: 10px;
      border-radius: 5px;
      background: #f1f5f9;
      display: none;
    }
  </style>
</head>
<body>
  <div class="card">
    <h2>Track Your Order</h2>
    <input type="text" id="trackingId" placeholder="Enter Tracking ID" />
    <button onclick="trackOrder()">Track</button>
    <div class="result" id="result"></div>
  </div>  <script>
    const trackingData = {
      "ABC123": {
        status: "In Transit",
        location: "Colombo",
        expected: "20 Dec 2025"
      },
      "XYZ789": {
        status: "Delivered",
        location: "Dubai",
        expected: "Delivered on 10 Dec 2025"
      }
    };

    function trackOrder() {
      const id = document.getElementById("trackingId").value.trim();
      const result = document.getElementById("result");

      if (trackingData[id]) {
        result.style.display = "block";
        result.innerHTML = `
          <strong>Status:</strong> ${trackingData[id].status}<br>
          <strong>Current Location:</strong> ${trackingData[id].location}<br>
          <strong>Expected:</strong> ${trackingData[id].expected}
        `;
      } else {
        result.style.display = "block";
        result.innerHTML = "❌ Tracking ID not found";
      }
    }
  </script></body>
</html>