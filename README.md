<!DOCTYPE html>
<html lang="ja">
  <head>
    <meta charset="utf-8">
    <title>JavaScript Practice</title>
    <style>
      body{
      display:flex;
      flex-wrap:wrap;
    }

      .box{
        width:100px;
        height:100px;
        background:skyblue;
        cursor:pointer;
        transition: 0.8s;
        margin:0 8px 8px 0;
        text-align:center;
        line-height:100px;
      }

      .circle{
        background:pink;
        border-radius:50%;
        transform: rotate(360deg);
      }

      .win{
        background:pink;
        border-radius:50%;
        transform: rotate(360deg);
      }

      .lose{
        transform:scale(0.9);
      }

    </style>
  </head>
  <body>


  <script>
    'use strict';

    const num = 5 ;
    const winner = Math.floor(Math.random()*num);

    for(let i = 0; i < num; i++){
      const div = document.createElement('div');
      div.classList.add('box');
      if( i === winner){
        div.dataset.result='win'
      } else{
        div.dataset.result='lose'
      };
      div.addEventListener('click',function(){
        if(div.dataset.result === 'win'){
          div.textContent = 'win!';
          div.classList.add('win');
        }else{
          div.textContent = 'lose!';
          div.classList.add('lose');
        }

      });
      document.body.appendChild(div);
    }


  </script>

  </body>
</html>
