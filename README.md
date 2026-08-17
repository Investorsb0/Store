<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="NovaStore - Quality products at great prices.">
<title>NovaStore | Quality Products</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial,sans-serif}
body{background:#f5f6f8;color:#222}
button,input{font:inherit}
button{cursor:pointer;border:0}
a{text-decoration:none;color:inherit}

.header{background:#111827;color:#fff;position:sticky;top:0;z-index:20}
.top{max-width:1200px;margin:auto;padding:16px 20px;display:flex;align-items:center;gap:18px}
.logo{font-size:25px;font-weight:800;color:#fff;white-space:nowrap}
.logo span{color:#22c55e}

.search{flex:1;display:flex;background:#fff;border-radius:8px;overflow:hidden}
.search input{width:100%;padding:12px;border:0;outline:0}
.search button{padding:0 16px;background:#22c55e;color:#fff}

.nav{display:flex;gap:10px}
.nav button{background:#1f2937;color:#fff;padding:10px 12px;border-radius:7px}
.nav button:hover{background:#374151}
.badge{background:#ef4444;border-radius:20px;padding:2px 7px;font-size:11px}

.hero{background:linear-gradient(135deg,#111827,#1f2937);color:white;padding:60px 20px}
.hero-inner{max-width:1200px;margin:auto}
.hero h1{font-size:42px;margin-bottom:12px}
.hero p{font-size:18px;color:#d1d5db;max-width:600px;line-height:1.6}
.hero button{margin-top:22px;background:#22c55e;color:#fff;padding:13px 22px;border-radius:8px;font-weight:bold}

.section{max-width:1200px;margin:auto;padding:35px 20px}
.section-title{display:flex;justify-content:space-between;align-items:center;margin-bottom:20px}
.section-title h2{font-size:25px}

.categories{display:flex;gap:10px;overflow:auto;padding-bottom:8px}
.cat{padding:10px 16px;border-radius:25px;background:#fff;border:1px solid #ddd;white-space:nowrap}
.cat.active,.cat:hover{background:#111827;color:#fff}

.products{display:grid;grid-template-columns:repeat(4,1fr);gap:18px}
.card{background:#fff;border-radius:12px;overflow:hidden;box-shadow:0 2px 10px #00000012;border:1px solid #eee}

.pic{height:190px;background:#eef2f7;display:flex;align-items:center;justify-content:center;font-size:75px}

.info{padding:15px}
.info h3{font-size:17px;margin-bottom:8px}
.info p{color:#666;font-size:13px;min-height:34px}

.price{font-weight:800;font-size:19px;margin:12px 0}
.add{width:100%;background:#111827;color:#fff;padding:11px;border-radius:7px}
.add:hover{background:#22c55e}
.old{font-size:13px;color:#999;text-decoration:line-through;margin-left:6px}

.empty{text-align:center;padding:30px;grid-column:1/-1;color:#777}

footer{background:#111827;color:#d1d5db;padding:40px 20px;margin-top:20px}
.footer-inner{max-width:1200px;margin:auto;display:grid;grid-template-columns:repeat(3,1fr);gap:30px}
footer h3{color:#fff;margin-bottom:12px}
footer p{line-height:1.8;font-size:14px}

.modal-bg{display:none;position:fixed;inset:0;background:#0008;z-index:50;align-items:center;justify-content:center;padding:20px}
.modal{background:#fff;width:100%;max-width:430px;border-radius:12px;padding:24px;position:relative;max-height:90vh;overflow:auto}
.close{position:absolute;right:15px;top:12px;background:#eee;width:32px;height:32px;border-radius:50%}
.modal h2{margin-bottom:18px}

.form-group{margin-bottom:13px}
.form-group label{display:block;font-size:13px;margin-bottom:6px}
.form-group input{width:100%;padding:12px;border:1px solid #ccc;border-radius:7px;outline:0}

.form-btn{width:100%;padding:12px;background:#111827;color:#fff;border-radius:7px;margin-top:5px}
.form-btn:hover{background:#22c55e}

.switch{margin-top:15px;text-align:center;font-size:14px}
.switch a{color:#16a34a;font-weight:bold;cursor:pointer}

.cart-item{display:flex;gap:12px;padding:12px 0;border-bottom:1px solid #eee;align-items:center}
.cart-icon{font-size:35px}
.cart-details{flex:1}

.qty{display:flex;align-items:center;gap:8px;margin-top:6px}
.qty button{width:27px;height:27px;border-radius:5px;background:#eee}

.cart-total{font-size:20px;font-weight:bold;text-align:right;margin:18px 0}
.checkout{width:100%;padding:13px;background:#22c55e;color:#fff;border-radius:7px;font-weight:bold}

.account{background:#f0fdf4;border:1px solid #bbf7d0;padding:12px;border-radius:8px;margin-bottom:15px}

@media(max-width:900px){
.products{grid-template-columns:repeat(3,1fr)}
}

@media(max-width:650px){
.top{flex-wrap:wrap}
.logo{width:100%}
.search{order:3;flex-basis:100%}
.nav{position:absolute;right:10px;top:12px}
.hero h1{font-size:32px}
.products{grid-template-columns:repeat(2,1fr);gap:12px}
.pic{height:150px;font-size:58px}
.info{padding:11px}
.footer-inner{grid-template-columns:1fr}
.section{padding:25px 12px}
}
</style>
</head>

<body>

<header class="header">
<div class="top">

<a class="logo" href="#">
Nova<span>Store</span>
</a>

<div class="search">
<input id="searchInput" type="search" placeholder="Search products...">
<button onclick="searchProducts()">Search</button>
</div>

<div class="nav">
<button onclick="openLogin()">👤 <span id="accountText">Login</span></button>
<button onclick="openCart()">🛒 <span class="badge" id="cartCount">0</span></button>
</div>

</div>
</header>

<section class="hero">
<div class="hero-inner">

<h1>Welcome to NovaStore</h1>

<p>
Discover quality products, great prices and a simple shopping experience.
</p>

<button onclick="document.getElementById('products').scrollIntoView({behavior:'smooth'})">
Shop Now
</button>

</div>
</section>

<section class="section">

<div class="section-title">
<h2>Categories</h2>
</div>

<div class="categories">

<button class="cat active" onclick="filterCategory('All',this)">
All
</button>

<button class="cat" onclick="filterCategory('Electronics',this)">
Electronics
</button>

<button class="cat" onclick="filterCategory('Fashion',this)">
Fashion
</button>

<button class="cat" onclick="filterCategory('Home',this)">
Home
</button>

<button class="cat" onclick="filterCategory('Accessories',this)">
Accessories
</button>

</div>
</section>

<section class="section" id="products">

<div class="section-title">
<h2>Featured Products</h2>
</div>

<div class="products" id="productGrid"></div>

</section>

<footer>

<div class="footer-inner">

<div>
<h3>NovaStore</h3>
<p>Quality products for everyday life.</p>
</div>

<div>
<h3>Customer Service</h3>
<p>
Contact us through your preferred channel for help with orders and products.
</p>
</div>

<div>
<h3>Quick Links</h3>
<p>
<a href="#products">Products</a><br>
<a href="#" onclick="openCart();return false">Shopping Cart</a><br>
<a href="#" onclick="openLogin();return false">My Account</a>
</p>
</div>

</div>
</footer>

<!-- LOGIN / REGISTER -->

<div class="modal-bg" id="loginModal">

<div class="modal">

<button class="close" onclick="closeModal('loginModal')">
×
</button>

<h2 id="authTitle">Login to NovaStore</h2>

<div id="loggedInBox" style="display:none"></div>

<form id="authForm" onsubmit="handleAuth(event)">

<div class="form-group" id="nameGroup" style="display:none">

<label>Full name</label>

<input
id="nameInput"
type="text"
placeholder="Your name"
>

</div>

<div class="form-group">

<label>Email</label>

<input
id="emailInput"
type="email"
required
placeholder="you@example.com"
>

</div>

<div class="form-group">

<label>Password</label>

<input
id="passwordInput"
type="password"
required
minlength="6"
placeholder="At least 6 characters"
>

</div>

<button class="form-btn" id="authButton">
Login
</button>

</form>

<div class="switch" id="switchBox">
Don't have an account?
<a onclick="toggleAuth()">Create one</a>
</div>

</div>
</div>

<!-- CART -->

<div class="modal-bg" id="cartModal">

<div class="modal">

<button class="close" onclick="closeModal('cartModal')">
×
</button>

<h2>Your Cart</h2>

<div id="cartItems"></div>

<div class="cart-total">
Total: ₦<span id="cartTotal">0</span>
</div>

<button class="checkout" onclick="checkout()">
Proceed to Checkout
</button>

</div>
</div>

<script>const products = [

{id:1,name:"Wireless Headphones",price:25000,old:30000,cat:"Electronics",icon:"🎧",desc:"Comfortable wireless headphones with clear sound."},

{id:2,name:"Smart Watch",price:35000,old:42000,cat:"Electronics",icon:"⌚",desc:"Smart everyday watch with useful features."},

{id:3,name:"Bluetooth Speaker",price:28000,old:33000,cat:"Electronics",icon:"🔊",desc:"Portable speaker for music at home or outdoors."},

{id:4,name:"Smartphone",price:180000,old:200000,cat:"Electronics",icon:"📱",desc:"Modern smartphone for work, study and entertainment."},

{id:5,name:"Laptop",price:450000,old:500000,cat:"Electronics",icon:"💻",desc:"Reliable laptop for everyday tasks."},

{id:6,name:"Sneakers",price:30000,old:38000,cat:"Fashion",icon:"👟",desc:"Casual sneakers for everyday use."},

{id:7,name:"Backpack",price:22000,old:27000,cat:"Fashion",icon:"🎒",desc:"Practical backpack with plenty of room."},

{id:8,name:"Hoodie",price:25000,old:30000,cat:"Fashion",icon:"🧥",desc:"Comfortable casual hoodie."},

{id:9,name:"Table Lamp",price:18000,old:22000,cat:"Home",icon:"💡",desc:"Simple modern lamp for your room or desk."},

{id:10,name:"Coffee Maker",price:55000,old:65000,cat:"Home",icon:"☕",desc:"Easy-to-use coffee maker for home."},

{id:11,name:"Storage Box",price:12000,old:15000,cat:"Home",icon:"📦",desc:"Useful storage solution for your home."},

{id:12,name:"Phone Case",price:8000,old:10000,cat:"Accessories",icon:"📱",desc:"Protective case for your smartphone."},

{id:13,name:"Power Bank",price:20000,old:25000,cat:"Accessories",icon:"🔋",desc:"Portable power for your devices."},

{id:14,name:"Sunglasses",price:15000,old:19000,cat:"Accessories",icon:"🕶️",desc:"Stylish everyday sunglasses."},

{id:15,name:"USB Cable",price:6000,old:8000,cat:"Accessories",icon:"🔌",desc:"Durable charging and data cable."},

{id:16,name:"Wireless Mouse",price:12000,old:15000,cat:"Electronics",icon:"🖱️",desc:"Comfortable wireless mouse for your computer."}

];

let cart = JSON.parse(localStorage.getItem("novaCart") || "[]");

let currentCategory = "All";

let registerMode = false;

let currentUser = JSON.parse(
localStorage.getItem("novaUser") || "null"
);

function money(n){
return Number(n).toLocaleString("en-NG");
}

function renderProducts(list=products){

const grid=document.getElementById("productGrid");

if(!list.length){

grid.innerHTML=
'<div class="empty">No products found.</div>';

return;
}

grid.innerHTML=list.map(p=>`

<div class="card">

<div class="pic">
${p.icon}
</div>

<div class="info">

<h3>${p.name}</h3>

<p>${p.desc}</p>

<div class="price">
₦${money(p.price)}
<span class="old">
₦${money(p.old)}
</span>
</div>

<button class="add" onclick="addToCart(${p.id})">
Add to Cart
</button>

</div>
</div>

`).join("");

}

function addToCart(id){

const found=cart.find(x=>x.id===id);

if(found)
found.qty++;
else
cart.push({id,qty:1});

saveCart();

updateCartCount();

alert("Product added to your cart.");

}

function saveCart(){

localStorage.setItem(
"novaCart",
JSON.stringify(cart)
);

}

function updateCartCount(){

document.getElementById("cartCount").textContent=
cart.reduce((a,b)=>a+b.qty,0);

}

function openCart(){

renderCart();

document.getElementById("cartModal").style.display="flex";

}

function renderCart(){

const box=document.getElementById("cartItems");

if(!cart.length){

box.innerHTML=
'<p style="padding:20px 0;text-align:center">Your cart is empty.</p>';

document.getElementById("cartTotal").textContent="0";

return;

}

let total=0;

box.innerHTML=cart.map(item=>{

const p=products.find(x=>x.id===item.id);

total+=p.price*item.qty;

return `

<div class="cart-item">

<div class="cart-icon">
${p.icon}
</div>

<div class="cart-details">

<b>${p.name}</b>

<div>
₦${money(p.price)}
</div>

<div class="qty">

<button onclick="changeQty(${p.id},-1)">
−
</button>

<span>${item.qty}</span>

<button onclick="changeQty(${p.id},1)">
+
</button>

<button onclick="removeItem(${p.id})">
Remove
</button>

</div>

</div>

</div>

`;

}).join("");

document.getElementById("cartTotal").textContent=
money(total);

}

function changeQty(id,amount){

const item=cart.find(x=>x.id===id);

if(!item)return;

item.qty+=amount;

if(item.qty<=0)
cart=cart.filter(x=>x.id!==id);

saveCart();

updateCartCount();

renderCart();

}

function removeItem(id){

cart=cart.filter(x=>x.id!==id);

saveCart();

updateCartCount();

renderCart();

}

function checkout(){

if(!cart.length){

alert("Your cart is empty.");

return;
}

if(!currentUser){

closeModal("cartModal");

openLogin();

alert(
"Please login or create an account before checkout."
);

return;
}

alert(
"Checkout is ready. Connect your preferred payment system to receive real payments."
);

}

function filterCategory(cat,btn){

currentCategory=cat;

document.querySelectorAll(".cat")
.forEach(x=>x.classList.remove("active"));

btn.classList.add("active");

applyFilters();

}

function searchProducts(){

applyFilters();

}

function applyFilters(){

const q=
document.getElementById("searchInput")
.value
.toLowerCase()
.trim();

renderProducts(

products.filter(p=>
(currentCategory==="All" || p.cat===currentCategory)
&&
(
!q ||
p.name.toLowerCase().includes(q) ||
p.cat.toLowerCase().includes(q)
)
)

);

}

document.getElementById("searchInput")
.addEventListener("input",applyFilters);


function openLogin(){

updateAuthUI();

document.getElementById("loginModal")
.style.display="flex";

}

function closeModal(id){

document.getElementById(id)
.style.display="none";

}

function toggleAuth(){

registerMode=!registerMode;

document.getElementById("authTitle")
.textContent=
registerMode
?"Create a NovaStore Account"
:"Login to NovaStore";

document.getElementById("nameGroup")
.style.display=
registerMode
?"block"
:"none";

document.getElementById("nameInput")
.required=registerMode;

document.getElementById("authButton")
.textContent=
registerMode
?"Create Account"
:"Login";

document.getElementById("switchBox")
.innerHTML=
registerMode
?
'Already have an account? <a onclick="toggleAuth()">Login</a>'
:
'Don\'t have an account? <a onclick="toggleAuth()">Create one</a>';

}function handleAuth(e){

e.preventDefault();

const email=
document.getElementById("emailInput")
.value.trim();

const password=
document.getElementById("passwordInput")
.value;

const name=
document.getElementById("nameInput")
.value.trim()
||
email.split("@")[0];

/*
This demo stores the session in this browser.

For REAL account authentication,
replace this section with Firebase
Authentication after adding your
Firebase project's configuration.
*/

currentUser={
name,
email
};

localStorage.setItem(
"novaUser",
JSON.stringify(currentUser)
);

alert(
registerMode
?"Account created successfully."
:"Login successful."
);

registerMode=false;

document.getElementById("authForm")
.reset();

updateAuthUI();

closeModal("loginModal");

}


function updateAuthUI(){

const account=
document.getElementById("accountText");

if(currentUser)
account.textContent=
currentUser.name || "Account";
else
account.textContent="Login";


const box=
document.getElementById("loggedInBox");


if(currentUser){

box.style.display="block";

box.innerHTML=`

<div class="account">

Logged in as
<b>${currentUser.name}</b>

<br>

${currentUser.email}

<br><br>

<button
onclick="logout()"
style="background:#111827;color:#fff;padding:8px 12px;border-radius:6px"
>
Logout
</button>

</div>

`;

document.getElementById("authForm")
.style.display="none";

document.getElementById("switchBox")
.style.display="none";

}

else{

box.style.display="none";

document.getElementById("authForm")
.style.display="block";

document.getElementById("switchBox")
.style.display="block";

}

}


function logout(){

currentUser=null;

localStorage.removeItem("novaUser");

updateAuthUI();

closeModal("loginModal");

alert("You have been logged out.");

}


window.onclick=function(e){

if(e.target.classList.contains("modal-bg"))
e.target.style.display="none";

};


renderProducts();

updateCartCount();

updateAuthUI();


/*
========================================================
FIREBASE SETUP
========================================================

Your Firebase file can be kept in the repository,
but GitHub Pages will not automatically connect
this page to Firebase.

When you are ready to use REAL Firebase Login
and Database, replace the demo login above with
Firebase Authentication and add your project's
Firebase configuration.

Example:

const firebaseConfig = {

apiKey: "YOUR_API_KEY",

authDomain:
"YOUR_PROJECT.firebaseapp.com",

projectId:
"YOUR_PROJECT_ID",

storageBucket:
"YOUR_PROJECT.appspot.com",

messagingSenderId:
"YOUR_SENDER_ID",

appId:
"YOUR_APP_ID"

};

Never put private server keys or passwords
in this HTML file.

========================================================
*/

</script>

</body>
</html>
