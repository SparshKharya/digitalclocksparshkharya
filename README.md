<html lang="en" dir="ltr">
   <head>
      <meta charset="utf-8">
      <title>Clock</title>
      <link rel="stylesheet" href="styleclock.css">
   </head>
  <style>
    *{
  margin: 0;
  padding: 0;
  font-family: 'Poppins', sans-serif;
}
html,body{
  display: grid;
  height: 100%;
  place-items: center;
  background: #000;
}
.wrapper{
  height: 100px;
  width: 360px;
  position: relative;
  background: linear-gradient(135deg, #14ffe9, #ffeb3b, #ff00e0);
  border-radius: 10px;
  cursor: default;
  animation: animate 1.5s linear infinite;
}
.wrapper .display,
.wrapper span{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.wrapper .display{
  z-index: 999;
  height: 85px;
  width: 345px;
  background: #1b1b1b;
  border-radius: 6px;
  text-align: center;
}
.display #time{
  line-height: 85px;
  color: #fff;
  font-size: 50px;
  font-weight: 600;
  letter-spacing: 1px;
  background: linear-gradient(135deg, #14ffe9, #ffeb3b, #ff00e0);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: animate 1.5s linear infinite;
}
@keyframes animate {
  100%{
    filter: hue-rotate(360deg);
  }
}
.wrapper span{
  height: 100%;
  width: 100%;
  border-radius: 10px;
  background: inherit;
}
.wrapper span:first-child{
  filter: blur(7px);
}
.wrapper span:last-child{
  filter: blur(20px);
}
     footer{
    background: #111;
    padding: 15px 23px;
    color: #fff;
    text-align: center;
}
footer span a{
    color: #ffff00;
    text-decoration: none;
}
footer span a:hover{
    text-decoration: underline;
}
  </style>
   <body>
      <div class="wrapper">
         <div class="display">
            <div id="time"></div>
         </div>
         <span></span>
         <span></span>
      </div>
      <script>
         setInterval(()=>{
           const time = document.querySelector(".display #time");
           let date = new Date();
           let hours = date.getHours();
           let minutes = date.getMinutes();
           let seconds = date.getSeconds();
           let day_night = "AM";
           if(hours > 12){
             day_night = "PM";
             hours = hours - 12;
           }
           if(seconds < 10){
             seconds = "0" + seconds;
           }
           if(minutes < 10){
             minutes = "0" + minutes;
           }
           if(hours < 10){
             hours = "0" + hours;
           }
           time.textContent = hours + ":" + minutes + ":" + seconds + " "+ day_night;
         });
      </script>
         <footer>
        <span>Created By <a href="#">SparshKharya</a> | <span class="far fa-copyright"></span>&#169 2021 All rights reserved.</span>
    </footer>
   </body>
</html>
