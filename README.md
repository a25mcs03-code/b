<!DOCTYPE html>
<html lang="en">
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>AI Gift Recommendation</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,Helvetica,sans-serif;
}

body{
background:#fff5f8;
}

/* Header */

header{
background:#ff4f87;
padding:15px 8%;
display:flex;
justify-content:space-between;
align-items:center;
}

.logo{
font-size:28px;
font-weight:bold;
color:white;
}

nav ul{
display:flex;
list-style:none;
}

nav ul li{
margin-left:25px;
}

nav ul li a{
color:white;
text-decoration:none;
font-size:18px;
font-weight:bold;
}

nav ul li a:hover{
color:yellow;
}

.login-btn{
background:white;
color:#ff4f87;
padding:10px 25px;
border-radius:25px;
text-decoration:none;
font-weight:bold;
}

/* Form */

.container{
max-width:900px;
margin:40px auto;
background:white;
padding:40px;
border-radius:20px;
box-shadow:0 10px 20px rgba(0,0,0,.15);
}

.container h1{
text-align:center;
color:#ff4f87;
margin-bottom:30px;
}

.row{
display:grid;
grid-template-columns:1fr 1fr;
gap:20px;
margin-bottom:20px;
}

.input-box label{
display:block;
margin-bottom:8px;
font-weight:bold;
}

.input-box input,
.input-box select{

width:100%;
padding:14px;
border:2px solid #ff4f87;
border-radius:10px;
font-size:16px;
outline:none;

}

textarea{

width:100%;
padding:15px;
border:2px solid #ff4f87;
border-radius:10px;
resize:none;
font-size:16px;

}

button{

width:100%;
padding:15px;
margin-top:25px;
background:#ff4f87;
color:white;
font-size:20px;
border:none;
border-radius:30px;
cursor:pointer;
transition:.3s;

}

button:hover{

background:#e6005c;

}

#result{

margin-top:40px;

display:none;

}

.card{

background:#fff0f5;

padding:20px;

border-radius:15px;

margin-bottom:20px;

box-shadow:0 5px 10px rgba(0,0,0,.15);

}

.card h2{

color:#ff2f73;

margin-bottom:10px;

}

.card a{

display:inline-block;

margin-top:10px;

padding:10px 20px;

background:#ff4f87;

color:white;

text-decoration:none;

border-radius:25px;

}

.card button{

width:auto;

padding:10px 20px;

margin-left:10px;

font-size:15px;

}

footer{

background:#ff4f87;

color:white;

text-align:center;

padding:20px;

margin-top:40px;

}

@media(max-width:768px){

.row{

grid-template-columns:1fr;

}

nav{

display:none;

}

.container{

margin:20px;

}

}

</style>

</head>

<body>

<header>

<div class="logo">
🎁 AI Gift
</div>

<nav>

<ul>

<li><a href="index.html">Home</a></li>

<li><a href="favorites.html">Favorites</a></li>

<li><a href="about.html">About</a></li>

<li><a href="contact.html">Contact</a></li>

</ul>

</nav>

<a href="login.html" class="login-btn">
Login
</a>

</header>

<div class="container">

<h1>🤖 AI Gift Recommendation</h1>

<div class="row">

<div class="input-box">

<label>Recipient Name</label>

<input type="text" id="name" placeholder="Enter Name">

</div>

<div class="input-box">

<label>Occasion</label>

<select id="occasion">

<option>Birthday</option>
<option>Anniversary</option>
<option>Festival</option>
<option>Graduation</option>
<option>Wedding</option>

</select>

</div>

</div>

<div class="row">

<div class="input-box">

<label>Age</label>

<input type="number" id="age">

</div>

<div class="input-box">

<label>Gender</label>

<select id="gender">

<option>Male</option>
<option>Female</option>

</select>

</div>

</div>

<div class="row">

<div class="input-box">

<label>Relationship</label>

<select id="relation">

<option>Friend</option>
<option>Brother</option>
<option>Sister</option>
<option>Mother</option>
<option>Father</option>
<option>Husband</option>
<option>Wife</option>

</select>

</div>

<div class="input-box">

<label>Budget (₹)</label>

<input type="number" id="budget">

</div>

</div>

<div class="input-box">

<label>Interests</label>

<textarea id="interest" rows="4"
placeholder="Books, Technology, Sports, Fashion..."></textarea>

</div>

<button onclick="recommendGift()">

🎁 Recommend Gift

</button>

<div id="result">

</div>

</div
  <script>

function recommendGift(){

let name=document.getElementById("name").value;
let occasion=document.getElementById("occasion").value;
let age=document.getElementById("age").value;
let gender=document.getElementById("gender").value;
let relation=document.getElementById("relation").value;
let budget=document.getElementById("budget").value;
let interest=document.getElementById("interest").value;

if(name=="" || age=="" || budget=="" || interest==""){

alert("Please fill all fields.");
return;

}

let gift="";
let price="";
let amazon="";
let match="";

if(interest.toLowerCase().includes("technology")){

gift="Smart Watch";
price="₹2,999";
match="98%";
amazon="https://www.amazon.in/s?k=smart+watch";

}

else if(interest.toLowerCase().includes("books")){

gift="Best Selling Book Set";
price="₹999";
match="95%";
amazon="https://www.amazon.in/s?k=books+gift";

}

else if(interest.toLowerCase().includes("fashion")){

gift="Fashion Gift Combo";
price="₹1,499";
match="96%";
amazon="https://www.amazon.in/s?k=fashion+gift";

}

else if(interest.toLowerCase().includes("sports")){

gift="Sports Kit";
price="₹1,999";
match="97%";
amazon="https://www.amazon.in/s?k=sports+kit";

}

else{

gift="Premium Gift Hamper";
price="₹1,299";
match="92%";
amazon="https://www.amazon.in/s?k=gift+hamper";

}

document.getElementById("result").style.display="block";

document.getElementById("result").innerHTML=`

<div class="card">

<h2>🎁 Recommended Gift</h2>

<p><b>Recipient :</b> ${name}</p>

<p><b>Occasion :</b> ${occasion}</p>

<p><b>Relationship :</b> ${relation}</p>

<p><b>Suggested Gift :</b> ${gift}</p>

<p><b>Price :</b> ${price}</p>

<p><b>AI Match :</b> ⭐ ${match}</p>

<button onclick="saveFavorite()">
❤️ Save Favorite
</button>

<a href="${amazon}" target="_blank">
🛒 Buy on Amazon
</a>

</div>

`;

}

function saveFavorite(){

alert("❤️ Gift Saved Successfully!");

}

</script>

<footer>

<h2>🎁 AI Gift Recommendation System</h2>

<p style="margin-top:10px;">
Find the perfect gift with Artificial Intelligence.
</p>

<p style="margin-top:15px;">
© 2026 AI Gift Recommendation System
</p>

</footer>

</body>
</html>
