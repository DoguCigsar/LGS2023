<script>
	//Export Date
    export let date = new Date('June 4, 2023 09:30:00').getTime();
    //console.log("Selected date is: " + date.getTime());
    //console.log("Current date is: " + new Date().getTime());
    //console.log("Name of person is: " + name);
    //Countdown to selected Date
    let text = "";
    
    function down(){
        const now = new Date();
        const nowMillis = now.getTime();
        const second = 1000;
        const minute = second * 60;
        const hour = minute * 60;
        const day = hour * 24;
        const left = date - nowMillis;
        //console.log(`${name} Now:  ` +now)
        //console.log(`${name} NowMillis: ` + nowMillis)
        //console.log(`${name} Left: ` + left)
        //console.log(`${name} Date: ` + date)
        const leftDay = Math.floor(left / day);
        const leftHour = Math.floor((left % day) / hour);
        const leftMinute = Math.floor((left % hour) / minute);
        const leftSecond = Math.floor((left % minute) / second);
        text = `${leftDay} day(s), ${leftHour} hour(s), ${leftMinute} minute(s), ${leftSecond} second(s)`;
        
        if (left < 0) {
            clearInterval(countdown);
                
            text = `#LGS2023 is over!!`;
        }
        
    }
    //set the interval
    let countdown = setInterval(down, 1000);
</script>

<svelte:head>
	<title>#LGS2023</title>
</svelte:head>


<main>
	<div class="countdown">
		<h1>#LGS2023</h1>
		<h1 id="text">{text}</h1>
	</div>
	<h4 class="copyrightText"> Copyright © COS-Soft 2023</h4>
	<h4 class="madeBy">Doğu Çığşar</h4>
	<h1 class="dontPanic">Don't panic!</h1>
</main>

<style>
	 /*Center div Countdown on the screen center*/
	.countdown {
		position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
	}
	.copyrightText{
        color: rgb(255, 255, 255);
        font-size: 1rem;
        margin-top: 10;
        margin-bottom: 10;
        text-align: center;
        position: absolute;
        bottom: 0;  
    }
	.dontPanic{
		/*put the text on the center of screen*/
		position: absolute;
		top: 60%;
		left: 50%;
		transform: translate(-50%, -50%);
		font-size: 125px;
		color: rgba(0, 0, 0, 0.05)
		/* small screen size */
	}
	/*small screen size*/
	@media only screen and (max-width: 600px) {
		.countdown{
			top: 40%;
		}
		.dontPanic{
			font-size: 75px;
			top: 65%;
		}
	}
	.madeBy{
			/*right bottom corner*/
			position: absolute;
			bottom: 0;
			right: 0;
			color: rgb(255, 255, 255);
			font-size: 1rem;
			margin-top: 10;
			margin-bottom: 10;
			margin-right: 1rem;
			text-align: center;



		}
</style>
