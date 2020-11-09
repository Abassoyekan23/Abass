# DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=320, initial-scale=1">
    <style>
      body {
        padding:0;
        margin:0;
      }
      #button
      {
        position: absolute;
        border: solid 1px gray;
        border-radius: 4px;
        left: calc(50% - 75px);
        top: calc(50% - 20px);
        width: 150px;
        height: 40px;
        background: #def;
        text-align: center;
        line-height: 40px;
        transition-duration:3s;
      }
      #button.triggered
      {
        transform: rotate(3600deg);
        background: #fed;
      }
      </style>
    </head>
  <body>
    <div id="button"></div>

    <script>
      Intesticial
      var button = document.getElementById("button")
      var language = (window.EasyHTML ? EasyHTML.applicationLanguage : null) || "en"
      var logtext
      var classname = "triggered"
      
      switch(language) {
          case "ru":
            button.innerText = "Нажми меня";
            logtext = "Кнопка нажата";
          break;
          default:
            button.innerText = "Touch me";
            logtext = "Button touched";
          break;
      }
    
      var buttonTouched = function() {
          var e = button.classList
          
          if(e.contains(classname)) {
            
              e.remove(classname)
          } else {
              e.add(classname)
          }
          
          console.info(logtext)
      }
    
      button.addEventListener("touchend", buttonTouched)
    </script>
  </body>
</html>
