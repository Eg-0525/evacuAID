<!DOCTYPE html>
<html>

<head>

<title>EvacuAID</title>

<link href="https://fonts.googleapis.com/css2?family=Lora:wght@400;500;600&display=swap" rel="stylesheet">

<style>

body{
margin:0;
font-family:'Lora', serif;
background:#F8F4EC;
display:flex;
justify-content:center;
align-items:center;
height:100vh;
}

.phone{

width:360px;
height:640px;
background:#F8F4EC;
border-radius:30px;
box-shadow:0 12px 30px rgba(0,0,0,0.25);
overflow:hidden;
position:relative;

}

header{

background:#1E3A5F;
color:white;
text-align:center;
padding:16px;
font-size:24px;
font-weight:600;

}

.alert{

background:#C44536;
color:white;
text-align:center;
padding:10px;
font-size:14px;

}

.content{

padding:18px;
height:450px;
overflow:auto;

}

button{

width:100%;
padding:14px;
margin-top:12px;
border:none;
border-radius:12px;
background:#5DA9E9;
color:white;
font-size:16px;
cursor:pointer;
font-family:'Lora', serif;

}

button:hover{

background:#4a94d1;

}

.card{

background:#FDFBF7;
padding:16px;
margin-top:12px;
border-radius:12px;
box-shadow:0 4px 10px rgba(0,0,0,0.08);

}

input{

width:100%;
padding:10px;
margin-top:8px;
border-radius:8px;
border:1px solid #ccc;
font-family:'Lora', serif;

}

.navbar{

position:absolute;
bottom:0;
width:100%;
display:flex;
background:#1E3A5F;

}

.navbar button{

flex:1;
background:none;
border:none;
color:white;
padding:12px;
font-size:14px;

}

.bigText{

font-size:22px;

}

ul{
text-align:left;
}

</style>

</head>

<body>

<div class="phone">

<header>EvacuAID</header>

<div class="alert">
⚠ Emergency Alerts Enabled
</div>

<div class="content" id="content">

<h3>Welcome</h3>

<p>Enter a few details so we can personalize your emergency plan.</p>

<div class="card">

ZIP Code
<input id="zip">

Household Size
<input id="people">

Pets (yes/no)
<input id="pets">

Accessibility Needs
<input id="access">

<button onclick="startApp()">Start EvacuAID</button>

</div>

</div>

<div class="navbar">

<button onclick="home()">Home</button>
<button onclick="alerts()">Alerts</button>
<button onclick="training()">Training</button>

</div>

</div>

<script>

let userZip;
let household;
let pets;
let access;

function startApp(){

userZip=document.getElementById("zip").value;
household=document.getElementById("people").value;
pets=document.getElementById("pets").value;
access=document.getElementById("access").value;

home();

}

function home(){

document.getElementById("content").innerHTML=`

<h3>Dashboard</h3>

<div class="card">
ZIP Code: ${userZip}<br>
Household: ${household}<br>
Pets: ${pets}<br>
Accessibility: ${access}
</div>

<button onclick="showSupplies()">Emergency Supplies</button>

<button onclick="findShelter()">Find Shelter</button>

<button onclick="personalPlan()">Emergency Plan</button>

<button onclick="training()">Training Simulator</button>

<button onclick="accessibility()">Accessibility Mode</button>

`;

}

function alerts(){

document.getElementById("content").innerHTML=`

<h3>Active Alerts</h3>

<div class="card">
<strong>Tornado Warning</strong>
<p>Seek shelter in a basement or interior room.</p>
</div>

<div class="card">
<strong>Flood Risk</strong>
<p>Avoid low elevation roads.</p>
</div>

`;

}

function showSupplies(){

document.getElementById("content").innerHTML=`

<h3>Emergency Supplies</h3>

<div class="card">

<ul>
<li>Water (3-day supply)</li>
<li>Non-perishable food</li>
<li>Flashlight</li>
<li>First aid kit</li>
<li>Portable charger</li>
<li>Important documents</li>
</ul>

</div>

`;

}

function findShelter(){

if(userZip=="75075"){

document.getElementById("content").innerHTML=`

<h3>Nearby Shelters</h3>

<div class="card">
Red Cross Shelter — 3 miles away
</div>

<div class="card">
Community Center Shelter — 7 miles away
</div>

`;

}

else{

document.getElementById("content").innerHTML=`

<h3>Shelter Results</h3>

<div class="card">
Emergency shelter within 10 miles.
</div>

`;

}

}

function personalPlan(){

document.getElementById("content").innerHTML=`

<h3>Your Emergency Plan</h3>

<div class="card">

Household size: ${household}<br>
Pets: ${pets}<br>
Accessibility needs: ${access}

<h4>Checklist</h4>

<ul>
<li>Pack emergency supplies</li>
<li>Prepare evacuation routes</li>
<li>Save emergency contacts</li>
<li>Locate nearby shelters</li>
</ul>

</div>

`;

}

function training(){

let answer=prompt("Flood approaching. What should you pack? (water / tv / toys)");

if(answer=="water"){

document.getElementById("content").innerHTML=`

<h3>Correct</h3>

<div class="card">
Water is essential during disasters.
</div>

`;

}

else{

document.getElementById("content").innerHTML=`

<h3>Try Again</h3>

<div class="card">
Focus on survival essentials.
</div>

`;

}

}

function accessibility(){

document.body.classList.toggle("bigText");

}

</script>

</body>

</html>
