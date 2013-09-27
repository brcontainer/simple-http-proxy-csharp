simple http proxy csharp
======================

Simple http proxy asp.net (csharp)

### Usage ###
Example
Load image from google.com
`http://your-domain/folder/html-proxy-csharp.ashx?url=http://www.google.com/press/zeitgeist2001/google_logo.gif`

Load image from facebook.com
`http://your-domain/folder/html-proxy-csharp.ashx?url=https://www.facebook.com/images/fb_icon_325x325.png`

Example with **[Fabric.js](https://github.com/kangax/fabric.js)**:
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>fabric.js proxy</title>
		<script src="fabric.js"></script>
	</head>
	<body>
		<p>
			<a id="fire" href="#">SnapShot</a>
		</p>

		<canvas id="myCanvasId" width="350" height="350" style="border:1px solid #aaa"></canvas>
        <script>
			var canvas = new fabric.Canvas('myCanvasId');

			fabric.Image.fromURL('html-proxy-csharp.ashx?url=http://fabricjs.com/assets/pug_small.jpg', function(img) {
				img.scale(0.5).set({
					left: 150,
					top: 190,
					angle: -15,
					clipTo: function (ctx) {
						ctx.arc(0, 0, 300, 0, Math.PI * 2, true);
					}
				});
				canvas.add(img).setActiveObject(img);
			});

			function fireSnapShot(){
				window.open(document.getElementById('myCanvasId').toDataURL("image/png"));
			}

			document.getElementById('fire').onclick = fireSnapShot;
        </script>
    </body>
</html>
```
