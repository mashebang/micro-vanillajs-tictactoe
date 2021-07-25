# micro-vanillajs-tictactoe
a micro-tiny-little tic tac toe built with html, css and vanilla js. less than 50 lines (HTML AND CSS INCLUDED !!)

## it's so tiny that I'll put the whole source code here:

```html
<html>
  <head>
    <style type="text/css">
      * {
        border: 1px solid black;
        text-align: center;
      }
      .slots {
        width: 30%;
        flex-grow: 1;
        height: 50px;
      }
      #container {
        display: flex;
        flex-wrap: wrap;
        width: 50%;
      }
    </style>
  </head>
  <body>
    <div id="container"></div>
    <div id="title" class="slots">its your turn: </div>
    <div id="player" class="slots">x</div>
  </body>
  <script type="text/javascript">
    var slots = Array(9).fill();
    slots.forEach((i, k) => {
      const container = document.getElementById('container')
      const div = document.createElement('div');
      div.id = k;
      div.classList.add('slots');
      div.onclick = (e) => clickHandler(e.target)
      container.append(div);
    })
    function clickHandler(e) { 
      if (slots[e.id]) return;
      e.innerHTML = slots[e.id] = document.getElementById('player').innerHTML;
      ([[0, 4, 8], [2, 4, 6], [0, 3, 6], [1, 4, 7], [2, 5, 8], [0, 1, 2], [3, 4, 5], [6, 7, 8]]
        .reduce(
          (acc, b) => [
            ...acc,
            b.filter(i => slots[i] != undefined && slots[i] == document.getElementById('player').innerHTML).length
          ], []
        ).includes(3) && confirm(`player ${document.getElementById('player').innerHTML} wins !`) || (slots.filter(s => s == undefined).length < 3 && confirm(`elderlady !`))
      ) 
      document.getElementById('player').innerHTML = document.getElementById('player').innerHTML == 'x' ? 'o' : 'x';
    }
  </script>
</html>

```

# that's all folks
