# ipad
máy zin, đẹp , check test net 
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Shop Apple iPad</title>
<style>
body {
  font-family: Arial, sans-serif;
  background: #fff;
  margin: 0;
  padding: 0;
  color: #333;
}
header {
  text-align: center;
  padding: 20px;
  background: #f7f7f7;
  border-bottom: 1px solid #ddd;
}
header h1 {
  margin: 0;
  font-size: 28px;
}
.products {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
  padding: 30px;
  box-sizing: border-box;
}
.product {
  border: 1px solid #eee;
  border-radius: 8px;
  text-align: center;
  padding: 15px;
  background: #fff;
  transition: 0.3s;
}
.product:hover {
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}
.product img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  border-radius: 5px;
}
.product h3 {
  font-size: 18px;
  margin: 10px 0 5px 0;
}
.product p {
  margin: 5px 0;
}
button {
  background: #0071e3;
  color: white;
  border: none;
  padding: 10px 15px;
  border-radius: 5px;
  cursor: pointer;
}
button:hover {
  background: #005bb5;
}
#cart {
  padding: 20px;
  border-top: 1px solid #ddd;
  background: #fafafa;
}
.cart-item {
  margin-bottom: 10px;
}
form {
  margin-top: 20px;
}
input, textarea {
  width: 100%;
  padding: 8px;
  margin: 5px 0 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}
</style>
</head>
<body>

<header>
  <h1>Shop Apple iPad</h1>
  <p>Uy tín - Chất lượng - Giá tốt nhất</p>
</header>

<section class="products" id="product-list">
  <!-- Sản phẩm mẫu -->
</section>

<section id="cart">
  <h2>Giỏ hàng</h2>
  <div id="cart-items"></div>
  <form id="order-form">
    <h3>Đặt hàng</h3>
    <input type="text" id="name" placeholder="Họ tên" required />
    <input type="text" id="phone" placeholder="Số điện thoại" required />
    <textarea id="address" placeholder="Địa chỉ nhận hàng" required></textarea>
    <button type="submit">Gửi đơn hàng</button>
  </form>
</section>

<script>
const products = [
  {name:"iPad Gen 6 (4G/32GB)", price:2990000, img:"https://cdn.tgdd.vn/Products/Images/522/291004/ipad-gen-9-thumb-1-600x600.jpg"},
  {name:"iPad Gen 7 (Wifi/32GB)", price:2890000, img:"https://cdn.tgdd.vn/Products/Images/522/247504/ipad-gen-9-silver-600x600.jpg"},
  {name:"iPad Air 3 (4G/64GB)", price:3500000, img:"https://cdn.tgdd.vn/Products/Images/522/291003/ipad-air-5-thumb-1-600x600.jpg"},
  {name:"iPad Air 4 (64GB)", price:5400000, img:"https://cdn.tgdd.vn/Products/Images/522/291003/ipad-air-5-thumb-600x600.jpg"},
  {name:"iPad Pro 11 2020", price:8900000, img:"https://cdn.tgdd.vn/Products/Images/522/244149/ipad-pro-m2-11-inch-thumb-600x600.jpg"},
  {name:"iPad Mini 5", price:4300000, img:"https://cdn.tgdd.vn/Products/Images/522/244146/ipad-mini-6-thumb-1-600x600.jpg"},
  {name:"iPad Mini 6", price:6500000, img:"https://cdn.tgdd.vn/Products/Images/522/244146/ipad-mini-6-thumb-1-600x600.jpg"},
  {name:"Cáp sạc Lightning", price:150000, img:"https://cdn.tgdd.vn/Products/Images/58/238519/cap-lightning-apple-1m-thumb-600x600.jpg"},
  {name:"Bao da iPad", price:250000, img:"https://cdn.tgdd.vn/Products/Images/58/240779/bao-da-ipad-pro-11-inch-thumb-600x600.jpg"},
  {name:"Bút Apple Pencil", price:1200000, img:"https://cdn.tgdd.vn/Products/Images/1443/232740/apple-pencil-2-thumb-600x600.jpg"}
];

const list = document.getElementById("product-list");
products.forEach((p,i)=>{
  const div = document.createElement("div");
  div.className="product";
  div.innerHTML=`
    <img src="${p.img}" alt="${p.name}">
    <h3>${p.name}</h3>
    <p><b>${p.price.toLocaleString()}₫</b></p>
    <button onclick="addToCart(${i})">Thêm vào giỏ</button>`;
  list.appendChild(div);
});

let cart = [];
function addToCart(i){
  const item = products[i];
  cart.push(item);
  renderCart();
}
function renderCart(){
  const div = document.getElementById("cart-items");
  div.innerHTML = "";
  cart.forEach((c,idx)=>{
    div.innerHTML += `<div class="cart-item">${idx+1}. ${c.name} - ${c.price.toLocaleString()}₫</div>`;
  });
}

document.getElementById("order-form").addEventListener("submit", e=>{
  e.preventDefault();
  alert("Đơn hàng của bạn đã được gửi! Cảm ơn bạn ❤️");
});
</script>

</body>
</html>
