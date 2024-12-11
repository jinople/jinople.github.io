<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Countdown Timer</title>
<style>
body {
font-family: Arial, sans-serif;
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
height: 100vh;
margin: 0;
transition: background-color 0.3s, color 0.3s;
background-color: #1a1a1a; /* Dark mode by default */
color: #ffffff;
}
.timer {
font-size: 2rem;
color: #fff;
}
.toggle-button {
margin-top: 20px;
padding: 10px 20px;
background-color: #4CAF50;
color: #fff;
border: none;
cursor: pointer;
}
.bitcoin-address {
margin-top: 10px;
width: 80%;
padding: 10px;
border: none;
font-size: 1rem;
}
</style>
</head>
<body class="dark-mode">

<div class="timer" id="timer">
You will get more info when the timer expires and we reach the goal.
</div>
<button class="toggle-button" onclick="toggleDarkMode()">Toggle Dark Mode</button>

<!-- Bitcoin Address Slots -->
<input type="text" class="bitcoin-address" placeholder="Enter Bitcoin Address 1">
<input type="text" class="bitcoin-address" placeholder="Enter Bitcoin Address 2">
<input type="text" class="bitcoin-address" placeholder="Enter Bitcoin Address 3">

<script>
// Set the date we're counting down to
const targetDate = new Date("Dec 12, 2024 00:00:00").getTime();

// Update the countdown every 1 second
const countdownFunction = setInterval(() => {

// Get today's date and time
const now = new Date().getTime();

// Find the distance between now and the target date
const distance = targetDate - now;

// Time calculations for days, hours, minutes, and seconds
const days = Math.floor(distance / (1000 * 60 * 60 * 24));
const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
const seconds = Math.floor((distance % (1000 * 60)) / 1000);

// Display the result in the element with id="timer"
document.getElementById("timer").innerHTML = days + "d " + hours + "h " + minutes + "m " + seconds + "s ";

// If the countdown is over, write some text
if (distance < 0) {
clearInterval(countdownFunction);
document.getElementById("timer").innerHTML = "Timer expired. Mystery revealed!";
}
}, 1000);

function toggleDarkMode() {
document.body.classList.toggle('dark-mode');
}
</script>

</body>
</html>
