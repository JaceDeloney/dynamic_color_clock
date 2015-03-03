# dynamic_color_clock
This blue clock gets lighter during the day and darker at night.

<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" 
	"http://www.w3.org/TR/html4/strict.dtd">

<html>
<head>
<style>
h1 {
	height: 100px;
	width: 100%;
	color: #FFFF75;
	position: absolute;
	text-align: center;
	font-size: 100px;
	font-family: helvetica;
}
#clockTime {
	height: 100px;
	width: 100%;
	margin: auto;
	position: absolute;
	top:0; left:0; bottom:0; right:0;
	padding-top: 70px;
	text-align: center;
	color: white;
	font-size: 110px;
	font-family: ambroise;
	}
</style>
</head>
<body>
	<h1>Color Clock</h1>
	<div id=clockTime>
	<script type="text/javascript">

	function displayTime() {
		var d = new Date();
		var h = d.getHours();
		var m = d.getMinutes();
		var s = d.getSeconds();
		var meridiem = "AM";
		
		if((h > 7) && (h < 19)){
			document.body.style.backgroundColor="#80d4ea";
			}else{document.body.style.backgroundColor="#000099";
			}
		
		if(h>= 12) {
   			h = h - 12;
    		meridiem = "PM";
		    }
		if(h === 0) {
    		h = 12;    
		    }
    if(h > 12) {
    		h = h - 12;
    		}
		if(m <= 9) {
			m = '0'+m;
			}
		if(s <= 9) {
			s = '0'+s;
			}
		
		var clockTime = document.getElementById('clockTime');

	
		
		clockTime.innerText = h+':'+m+':'+s+' '+meridiem;
}
displayTime();
setInterval("displayTime()", 1000);
</script>
</div>
</body>
</html>
