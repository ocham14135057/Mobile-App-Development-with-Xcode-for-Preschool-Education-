<!DOCTYPE html>
<html>
<head>

<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Mobile App Development with Xcode for Preschool Education</title>

<style type="text/css"></style>
<style>
h1{font-family: verdana, arial, helvetica, sans-serif; font-size: 35px; font-weight:bold; color:black;}
#answer{font-family: verdana, arial, helvetica, sans-serif; font-size: 50px; font-weight:bold; color:red;}
#container{background:silver;}
#champion{background:olive;}
#screensaver{background:teal;} 
#fail{background:silver;}
</style>
<meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="stylesheet" href="http://code.jquery.com/mobile/1.0.1/jquery.mobile-1.0.1.min.css"/>
<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>
<script src="http://code.jquery.com/mobile/1.0.1/jquery.mobile-1.0.1.min.js"></script>
<script src="http://code.jquery.com/ui/1.8.21/jquery-ui.min.js"></script>




</head>

<body class = "container">

<div data-role="page" id="screensaver">
	<a href="#quiz" data-transition="slide" data-rel="button"><img src="Projectimage/Homepage.gif" alt="Homepage" width=350 height=560></a>
</div>


<div data-role="page" id="quiz">
	<div id = "container">
		<a id="Zero" data-transition="pop" data-rel="button"><img src ="Projectimage\number0.png" alt="Zero" width=40 height=40></a>
		<a id="One" data-transition="pop" data-rel="button"><img src ="Projectimage\number1.png" alt="One" width=40 height=40></a>
		<a id="Two" data-transition="pop" data-rel="button"><img src ="Projectimage\number2.png" alt="Two" width=40 height=40></a>
		<a id="Three" data-transition="pop" data-rel="button"><img src ="Projectimage\number3.png" alt="Three" width=40 height=40></a>
		<a id="Four" data-transition="pop" data-rel="button"><img src ="Projectimage\number4.png" alt="Four" width=40 height=40></a><br><br>
		<a id="Five" data-transition="pop" data-rel="button"><img src ="Projectimage\number5.png" alt="Five" width=40 height=40></a>
		<a id="Six" data-transition="pop" data-rel="button"><img src ="Projectimage\number6.png" alt="Six" width=40 height=40></a>
		<a id="Seven" data-transition="flip" data-rel="button"><img src ="Projectimage\number7.png" alt="Seven" width=40 height=40></a>
		<a id="Eight" data-transition="pop" data-rel="button"><img src ="Projectimage\number8.png" alt="Eight" width=40 height=40></a>
		<a id="Nine" data-transition="pop" data-rel="button"><img src ="Projectimage\number9.png" alt="Nine" width=40 height=40></a>

		<!-- Quiz number 1-->
		<h1><span id="valueOne"> </span> + <span id="valueTwo"> </span> = ? <span id="answer"></span></h1>
	</div>

	<div id ="appleForValueOne"></div><br/>
	
	<div id ="appleForValueTwo"></div>
	
	<!-- A plate containing the apples-->
	<div id="plate">
	
		<img src ="Projectimage\plate_white.png" alt="Plate" width=300 height=100>
	</div>
</div>

<div data-role="page" id="success">
	<p id="star1"><img src ="Projectimage\star_kids1.png" alt=" Tile background image" width=50px height=50px></p>
	<p id="star2"><img src ="Projectimage\star_kids2.png" alt=" Tile background image" width=50px height=50px></p>
	<p id="star3"><img src ="Projectimage\star_kids3.png" alt=" Tile background image" width=50px height=50px></p>

	<!--ThumpUp button for choosing correct answer-->
	<p id="ThumpUp"> <img src ="Projectimage\thumbs_up.png" alt="Pass" width=90px height=90px></p> 

	<!--Next Quiz  and the answer-->
	<h1><span id="valueOnePrevious"> </span> + <span id="valueTwoPrevious"> </span> = <span id="answerPrevious"></h1>


	<!--Play Again button to restart the Game-->
	<a id="retryAfterSuccess" href="#quiz" data-ajax="false" data-transition="slide" data-rel="button"><img src="Projectimage\play_again.png." alt="Restart" width=100 height=100></a>
</div>

<div data-role="page" id="fail"> 
	<!--Fail the quiz button-->
	<a href="#quiz" data-transition="slide" data-rel="button"><img src="Projectimage\UFailImage.gif" alt="Fail" width=320 height=450></a>
	<!--Play Again button to restart the Game-->
	<a href="#quiz" id="retryAfterFailure" data-ajax="false" data-transition="slide" data-rel="button"><img src="Projectimage\play_again.png." alt="Restart" width=50 height=50></a>
</div>


<div data-role="page" id="champion">
	<a href="#screensaver" data-transition="fade" data-rel="button"><img src="Projectimage/End.gif" alt="End!" width=350 height=560></a>
</div>


<script src="calculator.js"> </script> 
</body>
</html>


