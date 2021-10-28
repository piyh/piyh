<!-- this page will display a countdown timer to the date of September 12st, 2071 -->
<html>
	<head>
		<title>Countdown Timer</title>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1">
		<!-- Latest compiled and minified CSS -->
		<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
		<!-- jQuery library -->
		<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
		<!-- Latest compiled JavaScript -->
		<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
		<!-- font awesome -->
		<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.8.1/css/all.css" integrity="sha384-50oBUHEmvpQ+1lW4y57PTFmhCaXp0ML5d60M1M7uH2+nqUivzIebhndOJK28anvf" crossorigin="anonymous">
		<!-- custom css -->
		<link rel="stylesheet" type="text/css" href="css/countdown.css">
	</head>
	<body>
		<div class="container">
			<div class="row">
				<div class="col-md-12">
					<div class="jumbotron">
						<h1>Countdown Timer</h1>
						<!-- here we will display the countdown timer -->
						<h2 id="countdown"></h2>
					</div>
				</div>
			</div>
		</div>
		<!-- javascript -->
        <script type="text/javascript">
            // this function will display the countdown timer
            function countdown() {
                // this will get the current date and time
                var now = new Date();
                // this will get the date and time of the date and time of the event
                var eventDate = new Date(2071, 8, 12);
                // this will get the difference between the two dates
                var diff = eventDate.getTime() - now.getTime();
                // this will get the days, hours, minutes, and seconds
                var days = Math.floor(diff / (1000 * 60 * 60 * 24));
                var hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                var minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
                var seconds = Math.floor((diff % (1000 * 60)) / 1000);
                // this will display the countdown timer
                document.getElementById("countdown").innerHTML = days + "d " + hours + "h " + minutes + "m " + seconds + "s ";  
            }
            // this will call the countdown function every second
            setInterval(countdown, 1000);
        </script>
    </body> 
</html>
