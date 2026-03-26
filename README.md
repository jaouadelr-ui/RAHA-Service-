<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>stayle - متجر احترافي</title>

<style>
body {
    margin: 0;
    font-family: Arial;
    direction: rtl;
    background: #f4f4f4;
}

/* الهيدر */
header {
    background: #111;
    color: white;
    padding: 15px;
    text-align: center;
}

/* القائمة */
.menu-btn {
    position: fixed;
    top: 15px;
    right: 15px;
    font-size: 30px;
    cursor: pointer;
    z-index: 1001;
    color: white;
}

.sidebar {
    position: fixed;
    right: -260px;
    top: 0;
    width: 260px;
    height: 100%;
    background: #000;
    padding-top: 60px;
    transition: 0.3s;
    z-index: 1000;
}

.sidebar a {
    display: block;
    color: white;
    padding: 15px;
    text-decoration: none;
}

.sidebar a:hover {
    background: #333;
}

/* المنتجات */
.container {
    padding: 20px;
}

.products {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 15px;
}

.card {
    background: white;
    padding: 10px;
    border-radius: 10px;
    text-align: center;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.card img {
    width: 100%;
    height: 180px;
    object-fit: cover;
    border-radius: 10px;
}

.price {
    color: green;
    font-weight: bold;
}

/* الأزرار */
button {
    margin-top: 8px;
    padding: 8px;
    border: none;
    cursor: pointer;
    border-radius: 5px;
    background: black;
    color: white;
}

/* السلة */
.cart {
    position: fixed;
    left: 10px;
    top: 10px;
    background: white;
    padding: 10px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0,0,0,0.2);
    width: 220px;
}

.login {
    position: fixed;
    bottom: 10px;
    left: 10px;
    background: white;
    padding: 10px;
    border-radius: 10px;
}
</style>
</head>

<body>

<!-- زر القائمة -->
<div class="menu-btn" onclick="toggleMenu()">☰</div>

<!-- القائمة -->
<div class="sidebar" id="sidebar">
    <a href="#home">الرئيسية</a>
    <a href="#women">نسائي</a>
    <a href="#men">رجالي</a>
    <a href="#kids">أطفال</a>
</div>

<header id="home">
    <h1>🛍️ stayle</h1>
    <p>متجر الملابس العصري</p>
</header>

<!-- السلة -->
<div class="cart">
    <h3>🛒 السلة</h3>
    <div id="cartItems"></div>
    <p>المجموع: <span id="total">0</span> درهم</p>
    <button onclick="checkout()">الدفع</button>
</div>

<!-- تسجيل دخول -->
<div class="login">
    <h4>👤 دخول</h4>
    <input id="username" placeholder="الاسم">
    <button onclick="login()">دخول</button>
    <p id="user"></p>
</div>

<div class="container">

<!-- النساء -->
<h2>👗 نسائي</h2>
<div class="products" id="women"></div>

<!-- الرجال -->
<h2>👔 رجالي</h2>
<div class="products" id="men"></div>

<!-- الأطفال -->
<h2>🧒 أطفال</h2>
<div class="products" id="kids"></div>

</div>

<script>

/* القائمة */
function toggleMenu(){
    let s = document.getElementById("sidebar");
    s.style.right = (s.style.right === "0px") ? "-260px" : "0px";
}

/* تسجيل دخول بسيط */
function login(){
    let name = document.getElementById("username").value;
    document.getElementById("user").innerText = "مرحباً " + name;
}

/* المنتجات */
const products = {
    women: [
        {name:"فستان", price:150, img:"https://images.unsplash.com/photo-1520975916090-3105956dac38"},
        {name:"عباية", price:200, img:"https://images.unsplash.com/photo-1618354691792-d1d42acfd860"}
    ],
    men: [
        {name:"قميص", price:120, img:"https://images.unsplash.com/photo-1520975682031-a5c2c6c5c5d2"},
        {name:"جينز", price:180, img:"https://images.unsplash.com/photo-1542272604-787c3835535d"}
    ],
    kids: [
        {name:"طقم أطفال", price:100, img:"https://images.unsplash.com/photo-1503919545889-aef636e10ad4"}
    ]
};

/* السلة */
let cart = JSON.parse(localStorage.getItem("cart")) || [];

function renderProducts(){
    for(let cat in products){
        let box = document.getElementById(cat);

        products[cat].forEach((p, i)=>{
            box.innerHTML += `
            <div class="card">
                <img src="${p.img}">
                <h3>${p.name}</h3>
                <p class="price">${p.price} درهم</p>
                <button onclick="addToCart('${p.name}', ${p.price})">أضف للسلة</button>
            </div>`;
        });
    }
}

function addToCart(name, price){
    cart.push({name, price});
    localStorage.setItem("cart", JSON.stringify(cart));
    updateCart();
}

function updateCart(){
    let box = document.getElementById("cartItems");
    let total = 0;
    box.innerHTML = "";

    cart.forEach((item)=>{
        box.innerHTML += `<p>${item.name} - ${item.price} درهم</p>`;
        total += item.price;
    });

    document.getElementById("total").innerText = total;
}

function checkout(){
    alert("تم الطلب بنجاح 🛍️ (نسخة تجريبية)");
    cart = [];
    localStorage.removeItem("cart");
    updateCart();
}

renderProducts();
updateCart();

</script>

</body>
</html>
