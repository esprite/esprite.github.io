---
---
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>constructor-nodelist</title>

	<style>
	#wrapper {
		width: 700px;
		margin-left: auto;
		margin-right; auto;
		text-align: center;
	}
	.left {
		width: 300px;
		float: left;
	}
	.right {
		width: 300px;
		float: right;
	}
	</style>

</head>
<body>
    <!-- 1. Define some markup -->
    <button data-clipboard-text="test1">Copy to clipboard</button>
    <button data-clipboard-text="2">Copy</button>
    <button data-clipboard-text="3">Copy</button>

	<!-- Build Table -->
	<br />
	<div style="clear: both;"></div>
	<div id="wrapper">
		{% for item in site.data.short %}
		<div class="left">
		{{ item.from }}
		</div>
		<div class="right">
		{{ item.to }}
		</div>
		{% endfor %}
	</div>
	<br />
	<div style="clear: both;"></div>

    <!-- 2. Include library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/1.5.10/clipboard.min.js"></script>

    <!-- 3. Instantiate clipboard by passing a list of HTML elements -->
    <script>
    var btns = document.querySelectorAll('button');
    var clipboard = new Clipboard(btns);
    clipboard.on('success', function(e) {
        console.log(e);
    });
    clipboard.on('error', function(e) {
        console.log(e);
    });
    </script>
</body>
</html>


Hello World
<input id="foo" value="https://github.com/zenorocha/clipboard.js.git">

<!-- Trigger -->
<button class="btn" data-clipboard-target="#foo">
    <img src="assets/clippy.svg" alt="Copy to clipboard">
</button>

<button class="btn" data-clipboard-text="Just because you can doesn't mean you should — clipboard.js">
    Copy to clipboard
</button>


{% for item in site.data.short %}
<br />
{{ item.from }} \t {{ item.to }}


{% endfor %}
