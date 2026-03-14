<!DOCTYPE html><html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>راحة للخدمات - RAHA Services</title>
<style>
body{font-family:Arial;margin:0;background:#f4f6f8;direction:rtl}
header{background:#2c7be5;color:white;text-align:center;padding:30px}
section{background:white;margin:20px;padding:20px;border-radius:12px;box-shadow:0 4px 12px rgba(0,0,0,0.08)}
h2{color:#2c7be5;margin-top:0}
.price{background:#eef6ff;padding:10px;border-radius:6px;margin:8px 0}
button{background:#2c7be5;color:white;border:none;padding:12px 18px;border-radius:8px;cursor:pointer}
button.whatsapp{background:#25D366}
input,select,textarea{width:100%;padding:10px;margin-top:8px;margin-bottom:12px;border-radius:6px;border:1px solid #ccc}
.social a{display:inline-block;margin:10px;padding:10px 16px;background:#2c7be5;color:white;text-decoration:none;border-radius:8px}
.review{background:#f8f9fa;padding:10px;border-radius:6px;margin:6px 0}
footer{text-align:center;padding:20px;color:#666}
</style>
</head>
<body><header>
<h1>راحة للخدمات</h1>
<p>RAHA Services</p>
<p>تسوق مريح وتوصيل سريع إلى باب منزلك</p>
</header><section>
<h2>الخدمات</h2>
<ul>
<li>شراء المشتريات من البقالة والمتاجر</li>
<li>شراء الأدوية من الصيدلية</li>
<li>توصيل الطلبات الصغيرة للمنزل</li>
</ul>
</section><section>
<h2>نظام التسعير</h2>
<h3>🛒 حسب عدد الأكياس</h3>
<div class="price">1 إلى 2 أكياس → 10 دراهم</div>
<div class="price">3 إلى 4 أكياس → 15 درهم</div>
<div class="price">أكثر من ذلك → 20 درهم</div>
<h3>💊 طلبات الصيدلية</h3>
<div class="price">أقل من 200 درهم → 10 دراهم</div>
<div class="price">أكثر من 200 درهم → 15 درهم</div>
<h3>📦 الطلبات الثقيلة</h3>
<div class="price">إضافة 5 دراهم</div>
<h3>🔎 الطلبات التي يصعب إيجادها</h3>
<div class="price">5 إلى 10 دراهم حسب الجهد</div>
<h3>🌙 الخدمة الليلية</h3>
<div class="price">بعد الساعة 22:00 تصبح الأسعار مضاعفة</div>
</section><section>
<h2>اطلب الخدمة</h2>
<form onsubmit="sendWhatsApp();return false;"><label>الاسم</label> <input id="name" type="text" placeholder="اسمك" required>

<label>رقم الهاتف</label> <input id="phone" type="text" placeholder="رقم الهاتف" required>

<label>عدد الأكياس</label> <input id="bags" type="number" min="1" placeholder="مثلا 2">

<label>قيمة طلب الصيدلية (درهم)</label> <input id="pharmacy" type="number" min="0" placeholder="إذا لم يوجد اتركه 0">

<label>
<input id="heavy" type="checkbox"> طلب ثقيل (قنينات ماء أو أشياء ثقيلة)
</label><label>قائمة المشتريات</label>

<textarea id="list" rows="4" placeholder="اكتب المشتريات هنا"></textarea><label>الموقع</label> <input id="locationField" type="text" placeholder="سيظهر موقعك هنا أو اكتب العنوان"> <button type="button" onclick="getLocation()">تحديد موقعي عبر GPS</button>

<br><br>

<button type="button" onclick="calculatePrice()">حساب السعر التقريبي</button>

<div id="priceResult" style="margin-top:10px;font-weight:bold"></div><br><button class="whatsapp" type="submit">إرسال الطلب عبر واتساب</button>

</form>
</section><section>
<h2>موقع الخدمة</h2>
<iframe src="https://maps.google.com/maps?q=temara&t=&z=13&ie=UTF8&iwloc=&output=embed" width="100%" height="300" style="border:0;border-radius:10px"></iframe>
</section><section>
<h2>آراء الزبناء</h2>
<div class="review">⭐ خدمة ممتازة وسريعة</div>
<div class="review">⭐ الشخص الذي قام بالتوصيل محترم جدا</div>
<div class="review">⭐ وفرت علي الوقت والتعب</div>
</section><section>
<h2>تابعنا</h2>
<div class="social">
<a href="https://www.facebook.com/share/1HxZFhvbby/" target="_blank">فيسبوك</a>
<a href="https://www.instagram.com/raha.service2026?igsh=ajZkODg0dHhtMmNq" target="_blank">انستغرام</a>
</div>
</section><footer>
RAHA Services © 2026
</footer><script>
function getLocation(){
 if(navigator.geolocation){
  navigator.geolocation.getCurrentPosition(function(pos){
   const lat=pos.coords.latitude;
   const lon=pos.coords.longitude;
   document.getElementById('locationField').value=`https://maps.google.com/?q=${lat},${lon}`;
  },function(){alert('تعذر تحديد الموقع');});
 }else{alert('المتصفح لا يدعم GPS');}
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
}, ${lon}`;
  },function(){
   alert('تعذر تحديد الموقع');
  });
 }else{
  alert('المتصفح لا يدعم GPS');
 }
}
</script></body>
</html>
