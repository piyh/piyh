<!-- a countdown timer ending at September 21st 2071
    written with vanilla javascript and no external libraries
-->
<html>
    <head>
        <script type="text/javascript">
            // the date to count down to
            var targetDate = new Date("September 21, 2071").getTime();
            // current date
            var currentDate = new Date().getTime();
            // difference between the two dates
            var timeLeft = targetDate - currentDate;
            // time left in days
            var daysLeft = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
            // time left in hours
            var hoursLeft = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            // time left in minutes
            var minutesLeft = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
            // time left in seconds
            var secondsLeft = Math.floor((timeLeft % (1000 * 60)) / 1000);
            // update the timer every second
            var timer = setInterval(function() {
                // update the time left
                timeLeft = targetDate - new Date().getTime();
                // update the days left
                daysLeft = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
                // update the hours left
                hoursLeft = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                // update the minutes left
                minutesLeft = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
                // update the seconds left
                secondsLeft = Math.floor((timeLeft % (1000 * 60)) / 1000);
                // update the html
                document.getElementById("days").innerHTML = daysLeft;
                document.getElementById("hours").innerHTML = hoursLeft;
                document.getElementById("minutes").innerHTML = minutesLeft;
                document.getElementById("seconds").innerHTML = secondsLeft;
                // if the time is up
                if (timeLeft < 0) {
                    // stop the timer
                    clearInterval(timer);
                    // update the html
                    document.getElementById("days").innerHTML = "0";
                    document.getElementById("hours").innerHTML = "0";
                    document.getElementById("minutes").innerHTML = "0";
                    document.getElementById("seconds").innerHTML = "0";
                }
            }, 1000);
        </script>
        <style>
            .countdown {
                font-size: 2em;
                font-weight: bold;
                text-align: center;
            }
            .countdown span {
                display: inline-block;
                width: 2em;
                text-align: center;
            }
        </style>
    </head>
    <body>
        <div class="countdown">
            <span id="days">0</span>
            <span id="hours">0</span>
            <span id="minutes">0</span>
            <span id="seconds">0</span>
        </div>
    </body>
</html>
