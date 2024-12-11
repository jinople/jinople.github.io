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
justify-content: center;
align-items: center;
height: 100vh;
background-color: #f3f4f6;
margin: 0;
}
.timer {
font-size: 2rem;
color: #333;
}
</style>
</head>
<body>

<div class="timer" id="timer">
Loading timer...
</div>

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
document.getElementById("timer").innerHTML = days + "d " + hours + "h "
+ minutes + "m " + seconds + "s ";

// If the countdown is over, write some text
if (distance < 0) {
clearInterval(countdownFunction);
document.getElementById("timer").innerHTML = "EXPIRED";
}
}, 1000);
</script>

</body>
</html>
