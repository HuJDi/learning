<!DOCTYPE html>
<html>

	<head>
		<meta charset="UTF-8">
		<title></title>
		<style>
			* {
				margin: 0;
				padding: 0;
			}
			
			input {
				font: 14px/30px "";
				text-indent: 10px;
				margin: 10px 0 0 10px;
			}
			
			ul {
				width: 100px;
				background: palegoldenrod;
				margin-left: 10px;
				display: none;
			}
			
			li {
				font: 14px/30px "";
				list-style: none;
				text-indent: 10px;
			}
		</style>
	</head>

	<body>
		<input placeholder="选择人物职业" />
		<ul>
			<li>刀客</li>
			<li>医师</li>
			<li>魅者</li>
			<li>异人</li>
			<li>甲士</li>
			<li>偃师</li>
		</ul>
		<script>
			"use strict";
			var input = document.querySelector("input");
			var ul = document.querySelector("ul")
			var li = document.querySelectorAll("li");
			input.onmouseover = function() {
					ul.style.display = "block";
					for(var i = 0; i < li.length; i++) {
						li[i].onmouseover = function() {
							ul.style.display = "block";
							console.log(i);
							this.style.backgroundColor = "gainsboro";
						}
						li[i].onmouseout = function() {
							this.style.backgroundColor = "palegoldenrod";
						}
						li[i].onmousedown = function() {
							var p = this.innerHTML;
							console.log(p)
							input.value = p;
						}
					}
					ul.onmouseout = function() {
						ul.style.display = "none";
					}
				input.onmouseout = function() {
					ul.style.display = "none";
				}
			}
		</script>
	</body>

</html>
