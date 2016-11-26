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


//////////////////////////////////////////////  jQuery //////////////////////////////////////////////////////////////////////



$(document).ready(function(){ 
	var valueOneData = -1;
	var valueTwoData = -1;
	var answer = -1;

function getRandomNoBetweenZeroAndFour() {
    return Math.floor(Math.random() * (4 - 0 + 1)) + 0;
}

function updateNewQuizInformation() {
	valueOneData = getRandomNoBetweenZeroAndFour();
	valueTwoData = getRandomNoBetweenZeroAndFour();
	answer = valueOneData + valueTwoData;
	$("#valueOne").empty().append(valueOneData);
	$("#valueTwo").empty().append(valueTwoData); 
	$("#answer").empty().append(answer);
	
	// hide answer to user
	$("#answer").hide(); 
	
}

function moveQuizInfoToSuccessPage(){
	$( "#valueOnePrevious" ).empty().append(valueOneData);
	$( "#valueTwoPrevious" ).empty().append(valueTwoData); 
	$( "#answerPrevious" ).empty().append(answer);
	
}

function generateApplesForValueOne(numberOfApples){
	for (i=1;i<=numberOfApples;i++){
		$('#appleForValueOne').append('<div class="draggable ui-widget-content ui-draggable"><img id="apple'+i+'" src ="Projectimage\\apple.png" alt="Apple" width=60 height=30></div>');
    };
	$("#valueOneApples").empty().append(valueOneData);
	$("#valueTwoApples").empty().append(valueTwoData);
	$("#answerApples").empty().append(answer);
}

function generateApplesForValueTwo(numberOfApples){
	for (i=1;i<=numberOfApples;i++){
		$('#appleForValueTwo').append('<div class="draggable ui-widget-content ui-draggable"><img src ="Projectimage\\apple.png" alt="Apple" width=60 height=30></div>');
    };
	$("#valueOneApples").empty().append(valueOneData);
	$("#valueTwoApples").empty().append(valueTwoData);
	$("#answerApples").empty().append(answer);
}

function generateApplesForAnswer(numberOfApples){
	for (i=1;i<=numberOfApples;i++){
		$('#appleForValueAnswer').append('<div class="draggable ui-widget-content ui-draggable"><img src ="Projectimage\\apple.png" alt="Apple" width=60 height=30></div>');
    };
	$("#valueOneApples").empty().append(valueOneData);
	$("#valueTwoApples").empty().append(valueTwoData);
	$("#answerApples").empty().append(answer);
}

$('#retryAfterSuccess').click(function(){
   location.reload();
});

$('#retryAfterFailure').click(function(){
   location.reload();
});

// Make apples draggable
$(function() {
    $( ".draggable" ).draggable();
});

 
 


// Start new Quiz
 updateNewQuizInformation();
 generateApplesForValueOne(valueOneData);
 generateApplesForValueTwo(valueTwoData);
 generateApplesForAnswer(answer);


    $("#Zero").click(function(e) {
		if (answer === 0) {
			$("#Zero").attr("href", "#success");
		} else {
			$("#Zero").attr("href", "#fail");
		}

		moveQuizInfoToSuccessPage();
		// Values for next quiz
		updateNewQuizInformation();
    });


    $("#One").click(function(e) {
		if (answer === 1) {
			$("#One").attr("href", "#success");
		} else {
			$("#One").attr("href", "#fail");
		}


		moveQuizInfoToSuccessPage();
		// Values for next quiz
		updateNewQuizInformation();
    });

    $("#Two").click(function(e) {
		if (answer === 2) {
			$("#Two").attr("href", "#success");
		} else {
			$("#Two").attr("href", "#fail");
		}

		moveQuizInfoToSuccessPage();
		// Values for next quiz
		updateNewQuizInformation();
    });


	$("#Three").click(function(e) {
		if (answer === 3) {
			$("#Three").attr("href", "#success");
		} else {
			$("#Three").attr("href", "#fail");
		}


		moveQuizInfoToSuccessPage();
		// Values for next quiz
		updateNewQuizInformation();
    });

    $("#Four").click(function(e) {
		if (answer == 4) {
			$("#Four").attr("href", "#success");
		} else {
			$("#Four").attr("href", "#fail");
		}


		moveQuizInfoToSuccessPage();
		// Values for next quiz
		updateNewQuizInformation();
    });

	$("#Five").click(function(e) {
		if (answer == 5) {
			$("#Five").attr("href", "#success");
		} else {
			$("#Five").attr("href", "#fail");
		}


		moveQuizInfoToSuccessPage();
		// Values for next quiz
		updateNewQuizInformation();
    });

	$("#Six").click(function(e) {
		if (answer == 6) {
			$("#Six").attr("href", "#success");
		} else {
			$("#Six").attr("href", "#fail");
		}


		moveQuizInfoToSuccessPage();
		// Values for next quiz
		updateNewQuizInformation();
    });


	$("#Seven").click(function(e) {
		if (answer == 7) {
			$("#Seven").attr("href", "#success");
		} else {
			$("#Seven").attr("href", "#fail");
		}


		moveQuizInfoToSuccessPage();
		// Values for next quiz
		updateNewQuizInformation();
    });

	
	$("#Eight").click(function(e) {
		if (answer == 8) {
			$("#Eight").attr("href", "#success");
		} else {
			$("#Eight").attr("href", "#fail");
		}


		moveQuizInfoToSuccessPage();
		// Values for next quiz
		updateNewQuizInformation();
    });

	
	$("#Nine").click(function(e) {
		if (answer == 9) {
			$("#Nine").attr("href", "#success");
		} else {
			$("#Nine").attr("href", "#fail");
		}


		moveQuizInfoToSuccessPage();
		// Values for next quiz
		updateNewQuizInformation();
    });

	
});  



////////////////////////////////////////////// Cascading  Style Sheet(CSS) //////////////////////////////////////////////////

