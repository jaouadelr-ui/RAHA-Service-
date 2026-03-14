<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>حاسبة عمولة التسوق</title>
<style>
body{font-family:Arial;text-align:center;margin-top:40px}
input,button{font-size:18px;padding:10px;margin:10px}
</style>
</head>

<body>

<h2>حاسبة عمولة خدمة التسوق</h2>

<input id="price" type="number" placeholder="أدخل ثمن الطلبية بالدرهم">

<br>

<button onclick="calc()">احسب العمولة</button>

<h3 id="result"></h3>

<script>
function calc(){

let price = document.getElementById("price").value;

let percent = 10 - (price / 200);

if(percent < 2.5){
percent = 2.5;
}

let commission = price * percent / 100;

if(commission < 10){
commission = 10;
}

document.getElementById("result").innerHTML =
"العمولة هي: " + commission.toFixed(2) + " درهم";
}
</script>

</body>
</html>
