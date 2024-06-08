<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <style>
    .container{
        display: flex;
        justify-content: center;
    }
    .btn{
        margin: 40px;
        padding: 30px;
        font-size: 20px;
        font-weight: bold;
    }
  </style>
  <body>
    <h1>Start should change the Background color every second</h1>
    <div class="container">
    <button id="start" class="btn">Start</button>
    <button id="stop" class="btn">Stop</button>
</div>
  </body>

  <script>
    // Generate random color formula
    const randomColor = function () {
      hex = "0123456789ABCDEF";
      let color = "#";
      for (i = 0; i < 6; i++) {
        color += hex[Math.floor(Math.random() * 16)];
      }
      return color;
    };

    // start button and handle event
    let BgGenerator;
    const bgcolorstart = function () {
      if (!BgGenerator) {
        BgGenerator = setInterval(change, 1000);
      }
      function change() {
        document.body.style.backgroundColor = randomColor();
      }
    };
    //stop button handler
    const bgcolorStop = function () {
      clearInterval(BgGenerator);
      BgGenerator = null;
    };
    // start and stop event handler
    document.getElementById("start").addEventListener("click", bgcolorstart);
    document.getElementById("stop").addEventListener("click", bgcolorStop);
  </script>
</html>
