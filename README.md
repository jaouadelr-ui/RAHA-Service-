<!DOCTYPE html><html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>راحة للخدمات | RAHA Services</title><link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700&display=swap" rel="stylesheet"><style>

*{
box-sizing:border-box;
margin:0;
padding:0;
}

body{
font-family:'Cairo',sans-serif;
background:#f4f6f9;
color:#333;
direction:rtl;
line-height:1.7;
}

header{
background:linear-gradient(135deg,#2c7be5,#1a5edb);
color:white;
padding:60px 20px;
text-align:center;
}

header h1{
font-size:38px;
margin-bottom:10px;
}

header p{
font-size:18px;
opacity:0.9;
}

.container{
max-width:1000px;
margin:auto;
padding:20px;
}

section{
background:white;
margin:25px 0;
padding:25px;
border-radius:14px;
box-shadow:0 10px 25px rgba(0,0,0,0.05);
}

h2{
color:#2c7be5;
margin-bottom:15px;
}

.services ul{
list-style:none;
padding-right:0;
}

.services li{
padding:10px 0;
border-bottom:1px solid #eee;
}

.pricing-grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
gap:15px;
}

.price-box{
background:#f1f6ff;
padding:15px;
border-radius:10px;
font-weight:600;
}

form label{
font-weight:600;
}

input,textarea{
width:100%;
padding:12px;
margin:8px 0 16px 0;
border-radius:8px;
border:1px solid #ddd;
font-family:'Cairo';
}

textarea{
resize:vertical;
}

button{
background:#2c7be5;
color:white;
border:none;
padding:14px 20px;
border-radius:10px;
cursor:pointer;
font-size:15px;
font-weight:600;
}

button:hover{
opacity:0.9;
}

.whatsapp{
background:#25D366;
margin-top:10px;
}

#priceResult{
font-weight:bold;
margin-top:10px;
font-size:18px;
}

.reviews{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
gap:12px;
}

.review{
background:#f7f8fa;
padding:14px;
border-radius:8px;
}

.social a{
display:inline-block;
margin:8px;
padding:10px 16px;
border-radius:8px;
text-decoration:none;
color:white;
font-weight:600;
}

.facebook{background:#1877f2}
.instagram{background:#e4405f}

footer{
text-align:center;
padding:25px;
color:#777;
font-size:14px;
}

</style></head><body><header>
<h1>راحة للخدمات</h1>
<p>خدمة التسوق والتوصيل في تمارة</p>
<p>تسوق مريح وتوصيل سريع إلى باب منزلك</p>
</header><div class="container"><section class="services">
<h2>الخدمات</h2>
<ul>
<li>شراء المشتريات من البقالة والمتاجر</li>
<li>شراء الأدوية من الصيدلية</li>
<li>توصيل الطلبات الصغيرة إلى المنزل</li>
</ul>
</section><section>
<h2>نظام التسعير</h2>
<div class="pricing-grid">
<div class="price-box">1 إلى 2 أكياس → 10 دراهم</div>
<div class="price-box">3 إلى 4 أكياس → 15 درهم</div>
<div class="price-box">أكثر من ذلك → 20 درهم</div>
<div class="price-box">طلب صيدلية أقل من 200 درهم → 10 دراهم</div>
<div class="price-box">طلب صيدلية أكثر من 200 درهم → 15 درهم</div>
<div class="price-box">طلبات ثقيلة → +5 دراهم</div>
<div class="price-box">الخدمة الليلية بعد 22:00 → السعر ×2</div>
</div>
</section><section>
<h2>اطلب الخدمة</h2><form onsubmit="sendWhatsApp();return false;"><label>الاسم</label> <input id="name" type="text" required>

<label>رقم الهاتف</label> <input id="phone" type="text" required>

<label>عدد الأكياس</label> <input id="bags" type="number" min="1">

<label>قيمة طلب الصيدلية (درهم)</label> <input id="pharmacy" type="number" min="0">

<label>
<input id="heavy" type="checkbox"> طلب ثقيل
</label><label>قائمة المشتريات</label>

<textarea id="list" rows="4"></textarea><label>الموقع</label> <input id="locationField" type="text" placeholder="اضغط لتحديد موقعك"> <button type="button" onclick="getLocation()">تحديد موقعي GPS</button>

<br><br>

<button type="button" onclick="calculatePrice()">حساب السعر</button>

<div id="priceResult"></div><button class="whatsapp" type="submit">إرسال الطلب عبر واتساب</button>

</form>
</section><section>
<h2>موقع الخدمة</h2>
<iframe src="https://maps.google.com/maps?q=temara&t=&z=13&ie=UTF8&iwloc=&output=embed" width="100%" height="300" style="border:0;border-radius:10px"></iframe>
</section><section>
<h2>آراء الزبناء</h2>
<div class="reviews">
<div class="review">⭐ خدمة سريعة ومحترفة</div>
<div class="review">⭐ وفرت علي الوقت والتعب</div>
<div class="review">⭐ توصيل سريع وثقة كبيرة</div>
</div>
</section><section>
<h2>تابعنا</h2>
<div class="social">
<a class="facebook" href="https://www.facebook.com/share/1HxZFhvbby/" target="_blank">فيسبوك</a>
<a class="instagram" href="https://www.instagram.com/raha.service2026?igsh=ajZkODg0dHhtMmNq" target="_blank">انستغرام</a>
</div>
</section></div><footer>
RAHA Services © 2026 | خدمة التسوق في تمارة
</footer><script>

function getLocation(){
 if(navigator.geolocation){
  navigator.geolocation.getCurrentPosition(function(pos){
   const lat=pos.coords.latitude;
   const lon=pos.coords.longitude;
   document.getElementById('locationField').value=`https://maps.google.com/?q=${lat},${lon}`;
  });
 }
}

function calculatePrice(){
 let bags=parseInt(document.getElementById('bags').value)||0;
 let pharmacy=parseInt(document.getElementById('pharmacy').value)||0;
 let heavy=document.getElementById('heavy').checked;

 let price=0;

 if(bags>0){
  if(bags<=2) price=10;
  else if(bags<=4) price=15;
  else price=20;
 }

 if(pharmacy>0){
  if(pharmacy<200) price=10;
  else price=15;
 }

 if(heavy) price+=5;

 const hour=new Date().getHours();
 if(hour>=22) price=price*2;

 document.getElementById('priceResult').innerText="السعر التقريبي: "+price+" درهم";

 return price;
}

function sendWhatsApp(){

 const price=calculatePrice();
 const name=document.getElementById('name').value;
 const phone=document.getElementById('phone').value;
 const list=document.getElementById('list').value;
 const location=document.getElementById('locationField').value;

 const message=`طلب جديد%0Aالاسم: ${name}%0Aالهاتف: ${phone}%0Aالمشتريات: ${list}%0Aالموقع: ${location}%0Aالسعر التقريبي: ${price} درهم`;

 const number="212XXXXXXXXX";

 window.open(`https://wa.me/${number}?text=${message}`,'_blank');
}

</script></body>
</html>
