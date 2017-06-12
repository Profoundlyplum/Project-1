# Project-1
The first challege
The brief for their tutorial:
1 - Make the headline and inputs
2 - Style the background and text
3 - Add a background image and logo
4 - Build your own personal website

I'm happy with this project, except that I have to resize the background image to show more of the rocket.
Unsure if the code needs tidying.


<!DOCTYPE html>
<head>
<link href="https://fonts.googleapis.com/css?family=Raleway:700" rel="stylesheet">
  <title>Plum Moore</title>
  <style>

      img {
      margin: 40px 0px 0px 0px;
      border: 8px solid orange;
      border-radius: 50px; 
    }
  
      body{
	text-align: center;
	color: white;
	background: url('http://imgur.com/KDjPNlZ.png');
	margin: auto;
  font-weight: 100;
  font-family: 'Raleway', sans-serif;
}
   
    p {
      font-size: 22px;
    }
   h1{
  font-family: 'Raleway', sans-serif;
  color: #16D77E;
  font-weight: 100;
  font-size: 40px;
  margin: 40px 0px 20px;
}
    input {
      padding: 10px;
      font-family: 'Raleway', sans-serif;
      font-size: 18px;
      border: 6px solid orange;
      border-radius: 80px;
      margin: 0px 0px 40px 0px;
    }
    input[type="submit"] {
      background: #ff6600; ;
      color: white;
    }
    
  



#clockdiv{
	ffont-family: 'Raleway', sans-serif;
	color: #fff;
	display: inline-block;
	font-weight: 300;
	text-align: center;
	font-size: 40px;
}

#clockdiv > div{
	padding: 10px;
	border-radius: 3px;
	background: #00BF96;
	display: inline-block;
}

#clockdiv div > span{
	padding: 15px;
	border-radius: 3px;
	background: #00816A;
	display: inline-block;
}

.smalltext{
	padding-top: 5px;
	font-size: 16px;
}
    
  </style>
</head>
<header>
<img src="http://i.imgur.com/MzAOI9m.png">
</header>
<body>
  <h1>Plum Moore</h1>
  <h2>Web developer extraordinaire</br>Coming soon...</h2>
  <h1>Countdown Clock</h1>
<div id="clockdiv">
  <div>
    <span class="days"></span>
    <div class="smalltext">Days</div>
  </div>
  <div>
    <span class="hours"></span>
    <div class="smalltext">Hours</div>
  </div>
  <div>
    <span class="minutes"></span>
    <div class="smalltext">Minutes</div>
  </div>
  <div>
    <span class="seconds"></span>
    <div class="smalltext">Seconds</div>
  </div>
</div>

  

  
 <p> Can't wait, that long? Get in touch!</p>
  <input type="email" placeholder=New@horizons.com>
  <input type="submit">
</body>

<script>
function getTimeRemaining(endtime) {
  var t = Date.parse(endtime) - Date.parse(new Date());
  var seconds = Math.floor((t / 1000) % 60);
  var minutes = Math.floor((t / 1000 / 60) % 60);
  var hours = Math.floor((t / (1000 * 60 * 60)) % 24);
  var days = Math.floor(t / (1000 * 60 * 60 * 24));
  return {
    'total': t,
    'days': days,
    'hours': hours,
    'minutes': minutes,
    'seconds': seconds
  };
}

function initializeClock(id, endtime) {
  var clock = document.getElementById(id);
  var daysSpan = clock.querySelector('.days');
  var hoursSpan = clock.querySelector('.hours');
  var minutesSpan = clock.querySelector('.minutes');
  var secondsSpan = clock.querySelector('.seconds');

  function updateClock() {
    var t = getTimeRemaining(endtime);

    daysSpan.innerHTML = t.days;
    hoursSpan.innerHTML = ('0' + t.hours).slice(-2);
    minutesSpan.innerHTML = ('0' + t.minutes).slice(-2);
    secondsSpan.innerHTML = ('0' + t.seconds).slice(-2);

    if (t.total <= 0) {
      clearInterval(timeinterval);
    }
  }

  updateClock();
  var timeinterval = setInterval(updateClock, 1000);
}

var deadline = 'December 15 2017';
initializeClock('clockdiv', deadline);
</script>
