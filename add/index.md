---
---
<html lang="en">
<head>
<title>Add to Domain Shortner</title>

<meta name="description" content="Static domain name shortner, page to add new urls" />
<meta charset="utf-8">
<meta name="author" content="7 Blink" />
<style type="text/css">
	div.fixedwidth {
		font-family: Arial, Helvetica, sans-serif ;
		font-size: 1em ;
		width: 800px ;
		margin-left: auto ;
		margin-right: auto ;
		padding: 10px ;
		background-color: white ;
		color: black ;
		border: 1px solid black ;
		word-wrap: break-word;
	}
	div.left {
		width: 390px;
		float: left;
		padding: 5px;
		text-align: right;
	}
	div.right {
		width: 360px;
		float: right;
		padding: 5px;
		text-align: left;
	}
	div.top{
		height: 40px;
	}
	h2.top{
		padding-top: 10px
		margin: auto;
	}
	#button {
		margin: auto;
	}
</style>

</head>

<body onload="framebreaker()">

<div class="fixedwidth">

<div class="top">
<h2 class="top">Add a new link
<a href="{{ site.add }}" target="_blank">
<button id="button" type="button">Add New Link</button>
</a>
</h2>
</div>

<h2>What is This Page About?</h2>

<hr>
{% for item in site.data.short %}
<div class="left">
{{ site.url}}/#{{ item.from }} <button data-clipboard-text="{{ site.url}}/#{{ item.from }}">Copy to clipboard</button>
</div>
<div class="right">
{{ item.to }}
</div>
<div style="clear: both;"></div>
<hr>
{% endfor %}

<br />
<div style="clear: both;"></div>


<br /><br />
<p>
This page is to provide an easy list of all the short links as well as one-click coping to clipboard.  <br />To add a new short link, click on the "Add New" button.  For detailed instructions, check out <br /><a href="{{ site.readme }}">{{ site.readme }}</a>
</p>

<script src="https://cdnjs.cloudflare.com/ajax/libs/clipboard.js/1.5.10/clipboard.min.js"></script>


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

