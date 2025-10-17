<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MalShop - Mini Shopee</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: "Poppins", sans-serif;
    }

    body {
      background-color: #f8f8f8;
    }

    header {
      background-color: #ee4d2d;
      color: white;
      padding: 15px;
      text-align: center;
      font-size: 22px;
      font-weight: bold;
      box-shadow: 0 3px 6px rgba(0,0,0,0.1);
    }

    .container {
      max-width: 1100px;
      margin: 25px auto;
      padding: 0 15px;
    }

    .product-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 20px;
    }

    .product-card {
      background: #fff;
      border-radius: 12px;
      box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
      transition: transform 0.2s ease;
      overflow: hidden;
    }

    .product-card:hover {
      transform: translateY(-5px);
    }

    .product-card img {
      width: 100%;
      height: 180px;
      object-fit: cover;
    }

    .product-info {
      padding: 12px;
      text-align: center;
    }

    .product-info h3 {
      font-size: 16px;
      margin-bottom: 5px;
      color: #333;
    }

    .product-info p {
      color: #ee4d2d;
      font-weight: 600;
      margin-bottom: 10px;
    }

    button {
      background-color: #ee4d2d;
      color: white;
      border: none;
      border-radius: 6px;
      padding: 8px 12px;
      cursor: pointer;
      font-size: 14px;
      transition: background 0.3s;
    }

    button:hover {
      background-color: #d94426;
    }

    .cart {
      background: white;
      margin-top: 40px;
      padding: 15px;
      border-radius: 12px;
      box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
    }

    .cart h2 {
      margin-bottom: 10px;
      font-size: 18px;
      color: #333;
    }

    .cart ul {
      list-style: none;
      padding: 0;
      margin-bottom: 10px;
    }

    .cart li {
      display: flex;
      justify-content: space-between;
      margin: 5px 0;
      border-bottom: 1px solid #eee;
      padding: 5px 0;
      font-size: 14px;
    }

    .total {
      text-align: right;
      font-weight: bold;
      color: #333;
    }
  </style>
</head>
<body>
  <header>🛍️ MalShop - Mini Shopee</header>

  <div class="container">
    <div class="product-grid">
      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1606813902779-8b6b37e6a3cb?auto=format&fit=crop&w=500&q=60" alt="Sepatu Sneakers">
        <div class="product-info">
          <h3>Sepatu Sneakers</h3>
          <p>Rp 250.000</p>
          <button onclick="addToCart('Sepatu Sneakers', 250000)">Tambah ke Keranjang</button>
        </div>
      </div>

      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1618354691438-25e6e63b9a9d?auto=format&fit=crop&w=500&q=60" alt="Headset Gaming">
        <div class="product-info">
          <h3>Headset Gaming</h3>
          <p>Rp 180.000</p>
          <button onclick="addToCart('Headset Gaming', 180000)">Tambah ke Keranjang</button>
        </div>
      </div>

      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1585386959984-a4155224a1b7?auto=format&fit=crop&w=500&q=60" alt="Mouse RGB">
        <div class="product-info">
          <h3>Mouse RGB</h3>
          <p>Rp 120.000</p>
          <button onclick="addToCart('Mouse RGB', 120000)">Tambah ke Keranjang</button>
        </div>
      </div>

      <div class="product-card">
        <img src="https://images.unsplash.com/photo-1592878849122-58f3a4b7a3b3?auto=format&fit=crop&w=500&q=60" alt="Keyboard Mechanical">
        <div class="product-info">
          <h3>Keyboard Mechanical</h3>
          <p>Rp 320.000</p>
          <button onclick="addToCart('Keyboard Mechanical', 320000)">Tambah ke Keranjang</button>
        </div>
      </div>
    </div>

    <div class="cart">
      <h2>🛒 Keranjang Belanja</h2>
      <ul id="cart-list"></ul>
      <div class="total">Total: Rp <span id="total">0</span></div>
    </div>
  </div>

  <script>
    let total = 0;
    const cartList = document.getElementById("cart-list");
    const totalDisplay = document.getElementById("total");

    function addToCart(item, price) {
      const li = document.createElement("li");
      li.textContent = `${item} - Rp ${price.toLocaleString()}`;
      cartList.appendChild(li);
      total += price;
      totalDisplay.textContent = total.toLocaleString();
    }
  </script>
</body>
</html>
