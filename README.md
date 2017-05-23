
<!DOCTYPE html>		<!-- 這是註解 -->
<html>				<!-- 這是html開頭的tag -->
<head>				<!-- 這是head開頭的tag -->
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />	<!-- 宣告編碼 -->
<title>這是要教給大家的Javascript程式</title>							<!-- 放在視窗列的文字 -->

    <!-- CSS Base -->
     <link rel="stylesheet" type='text/css' media='all' href="css/base.css"> 
    <!-- CSS Colors -->
     <link rel="stylesheet" type='text/css' media='all' href="css/colors.css"> 
    <!-- Optional - CSS SVG Icons (Font Awesome) -->
     <link rel="stylesheet" type='text/css' media='all' href="css/svg-icons.css"> 


</head>				<!-- 這是head結束的tag -->
<body>
    <main role="main">
        <article id="webslides" class="vertical">
<section class="bg-black aligncenter">
<!-- 下面是選項的語法 -->
<div class="wrap  fadeInUp" id="sec1">
	<div class="content-left">
		<input type="radio" name="option" value="跑步" checked>跑步<br>
		<input type="radio" name="option" value="鐵軌">鐵軌<br>
		<input type="radio" name="option" value="山巔">山巔<br>
		<select name="test" class="opts" id="myselect">
		  <option selected value=1>舒宇宸</option>
		  <option value=2>劉之中</option>
		  <option value=3>李昱勳</option>
		</select>
		名言一:<input id="quote_input1" value="數學建模教育之道無它, 唯數學與榜樣"> <br>
		名言二:<input id="quote_input2" value="Mathematical Modeling is nothing, but Mathematics and Model!"> <br>
		名言三:<input id="quote_input3" value="舒大ㄅ土, me"> <br>
		<button type="button" id="mybutton" onclick=showopt()>產生名言</button>	<!-- 按了之後要執行showopt() -->
	</div>
</div>
<div id="sec2">	
	<span id="teacher" class="background-right-bottom" style="background-image:url('images/ycshu.png'); z-index:5;"></span>
	<span id="bgimage" class="background light" style="background-image:url('images/road-dawn-mountains-sky.jpeg');"></span>
	<div class="wrap  fadeInUp">
		<div class="content-left">
			<blockquote>
				<h3 id="quote_line1">"數學建模教育之道無它<br>唯數學與榜樣"</h3>
				<p id="author1"><cite>舒大ㄅ土</cite></p>
			</blockquote>
			<blockquote>
				<h3 id="quote_line2">"Mathematical Modeling is nothing<br>but Mathematics and Model!"</h3>
				<p id="author2"><cite>me</cite></p>				
			</blockquote>
		</div>
	</div>
</div>
</section>
<!-- 改成一頁囉 :D
<section class="bg-black aligncenter" id="section_output">
<div id="sec2">
	<span id="teacher" class="background-right-bottom" style="background-image:url('images/ycshu.png'); z-index:5;"></span>
	<span id="bgimage" class="background light" style="background-image:url('images/road-dawn-mountains-sky.jpeg');"></span>
	
	<div class="wrap  fadeInUp">
		<div class="content-left">
			<blockquote>
				<h3 id="quote_line1">"數學建模教育之道無它<br>唯數學與榜樣"</h3>
				<p id="author1"><cite>舒大ㄅ土</cite></p>
			</blockquote>
			<blockquote>
				<h3 id="quote_line2">"Mathematical Modeling is nothing<br>but Mathematics and Model!"</h3>
				<p id="author2"><cite>me</cite></p>				
			</blockquote>
		</div>
	</div>
</div>
</section>
-->
        </article>
        <!-- end article -->
    </main>

<!-- 以下就真的是Javascript的程式了 -->
<script src="js/webslides.js"></script>
<script src="js/jquery.min.js"></script>
<script src="js/html2canvas.js"></script>
<script>
	const ws = new WebSlides();
	//
	$( "#sec2" ).hide();

function showopt() {

	var x;
	x = document.getElementById("quote_input1").value;
	x = x.split(',');
	x = x.join('<br>');
	document.getElementById("quote_line1").innerHTML = x;
	x = document.getElementById("quote_input2").value;
	x = x.split(',');
	x = x.join('<br>');
	document.getElementById("quote_line2").innerHTML = x;
	x = document.getElementById("quote_input3").value;
	x = x.split(',');
	document.getElementById("author1").innerHTML = "<cite>" + x[0] + "</cite>";
	
	var teacher_no = document.getElementById("myselect").value;
	if(teacher_no == 1) {
		document.getElementById("teacher").style = "background-image:url('images/ycshu.png'); z-index:5;";
	} else if (teacher_no == 2) {
		document.getElementById("teacher").style = "background-image:url('images/ccliu.png'); z-index:5;";
	} else if (teacher_no == 3) {
		document.getElementById("teacher").style = "background-image:url('images/andylee.png'); z-index:5;";
	}
	
	var y = document.getElementsByName("option");
	for(var i=0; i<y.length; ++i) {
		if(y[i].checked) {
			document.getElementById("author2").innerHTML = "<cite>" + x[1] + "</cite>";
			if(i==1) {
				document.getElementById("bgimage").style = "background-image:url('images/road-2.jpg');";
			} else if(i==2) {
				document.getElementById("bgimage").style = "background-image:url('images/road-3.jpg');";
			} else {
				document.getElementById("bgimage").style = "background-image:url('images/road-dawn-mountains-sky.jpeg');";
			}
		}
	}
	$( "#sec1" ).hide();
	$( "#sec2" ).show();
	/*
	//老師準備要產生圖檔用的 XD
	html2canvas(document.body, {
		onrendered: function(canvas) {
		var myImage = canvas.toDataURL("image/png");
            window.open(myImage);
		//y = document.getElementById("section-3");
		//y.appendChild(canvas);
		//document.body.appendChild(canvas);
		}
	});
	*/
	
}
</script>
</body>
</html>
