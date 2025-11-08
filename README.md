# SBbricks
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>S B Bricks Manufacturers</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f8f4ef;
      margin: 0;
      padding: 0;
    }

    header {
      background-color: #a83232;
      color: white;
      text-align: center;
      padding: 15px 0;
    }

    .container {
      max-width: 600px;
      background: #fff;
      margin: 30px auto;
      padding: 25px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
    }

    h2 {
      text-align: center;
      color: #a83232;
    }

    label {
      display: block;
      margin: 10px 0 5px;
      font-weight: bold;
    }

    input, textarea, select, button {
      width: 100%;
      padding: 10px;
      margin-bottom: 15px;
      border-radius: 5px;
      border: 1px solid #ccc;
      font-size: 16px;
    }

    button {
      background-color: #a83232;
      color: white;
      border: none;
      cursor: pointer;
    }

    button:hover {
      background-color: #c44545;
    }

    footer {
      text-align: center;
      padding: 10px;
      background-color: #a83232;
      color: white;
      margin-top: 20px;
    }

    .logo {
      width: 100%;
      text-align: center;
      margin-bottom: 20px;
    }
    /* 💡 Add your logo image later:
       <img src="logo.png" alt="S B Bricks Logo" width="200"> */
  </style>
</head>
<body>
  <header>
    <h1>S B Bricks Manufacturers</h1>
    <p>Wood-fired Red & Orange Bricks with deep "S*B" mark</p>
  </header>

  <div class="container">
    <div class="logo">
      <!-- 🧱 Add your logo here later with <img> -->
    </div>

    <h2>Order / Inquiry Form</h2>

    <form id="orderForm">
      <label for="name">Full Name</label>
      <input type="text" id="name" name="name" placeholder="Enter your name" required />

      <label for="phone">Phone Number</label>
      <input type="tel" id="phone" name="phone" placeholder="Enter your phone number" required />

      <label for="area">Delivery Area</label>
      <select id="area" name="area" required>
        <option value="">Select your area</option>
        <option>Hubballi</option>
        <option>Dharwad</option>
        <option>haliyal</option>
        <option>savadatti</option>
        <option>Other</option>
      </select>
      <label for="quantity">Quantity (Number of Bricks)</label>
      <input type="number" id="quantity" name="quantity" placeholder="Enter quantity" required />


      <label for="message">Additional Message</label>
      <textarea id="message" name="message" rows="4" placeholder="E.g., Quantity or delivery date..."></textarea>

      <button type="submit">Send via WhatsApp</button>
    </form>
  </div>

  <footer>
    <p>📞 Contact: +91 6363788297,8310812864 | 🚚 Delivery: Hubballi, Dharwad, haliyal, savadatti</p>
    <p>© 2025 S B Bricks Manufacturers</p>
  </footer>

  <script>
document.querySelector("form").addEventListener("submit", function(e){
  e.preventDefault();

  const data = {
    name: document.getElementById("name").value,
    phone: document.getElementById("phone").value,
    area: document.getElementById("area").value,
    quantity: document.getElementById("quantity").value,
    message: document.getElementById("message").value
  };

  // ✅ 1. Save to Google Sheet
  fetch("https://script.google.com/macros/s/AKfycbxzQ7Cjwz3zjP1P96INYvofwv00mi7PDS9tGR-i-2koTY7Z0ympRPCVN4cyUYI7a6VRtA/exec", {
    method: "POST",
    body: JSON.stringify(data),
    headers: {"Content-Type": "application/json"}
  })
  .then(res => res.text())
  .then(txt => {
    alert("Order saved successfully!");

    // ✅ 2. Send message to WhatsApp
    const whatsappNumber = "916363788297"; // <-- Replace with your WhatsApp number
    const msg = `🧱 *New Brick Order* 🧱

Name: ${data.name}
Phone: ${data.phone}
Area: ${data.area}
Quantity: ${data.quantity}
Message: ${data.message}`;

    const whatsappURL = `https://wa.me/${whatsappNumber}?text=${encodeURIComponent(msg)}`;
    window.open(whatsappURL, "_blank");
  })
  .catch(err => alert("Error: " + err));
});
</script>

</body>
</html>
