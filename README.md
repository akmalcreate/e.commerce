# e.commerce
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Toko Online MalShop</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
      background-color: #f7f7f7;
    }
    h1 {
      text-align: center;
    }
    .container {
      display: flex;
      justify-content: space-between;
    }
    .products, .cart {
      width: 48%;
      background: white;
      padding: 15px;
      border-radius: 10px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .product {
      display: flex;
      justify-content: space-between;
      margin: 10px 0;
    }
    button {
      background-color: #007bff;
      color: white;
      border: none;
      padding: 5px 10px;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background-color: #0056b3;
    }
  </style>
</head>
<body>

  <h1>🛒 MalShop - Mini E-Commerce</h1>
  <div class="container">
    <div class="products">
      <h2>Produk</h2>
      <div class="product">
        <span>Kaos Gaming</span>
        <span>Rp 75.000</span>
        <button onclick="addToCart('Kaos Gaming', 75000)">Tambah</button>
      </div>
      <div class="product">
        <span>Mouse RGB</span>
        <span>Rp 120.000</span>
        <button onclick="addToCart('Mouse RGB', 120000)">Tambah</button>
      </div>
      <div class="product">
        <span>Headset Pro</span>
        <span>Rp 250.000</span>
        <button onclick="addToCart('Headset Pro', 250000)">Tambah</button>
      </div>
    </div>

    <div class="cart">
      <h2>Keranjang Belanja</h2>
      <ul id="cart-list"></ul>
      <h3>Total: Rp <span id="total">0</span></h3>
    </div>
  </div>

  <script>
    let total = 0;
    const cartList = document.getElementById('cart-list');
    const totalDisplay = document.getElementById('total');

    function addToCart(item, price) {
      const li = document.createElement('li');
      li.textContent = `${item} - Rp ${price.toLocaleString()}`;
      cartList.appendChild(li);
      total += price;
      totalDisplay.textContent = total.toLocaleString();
    }
  </script>

</body>
</html>
