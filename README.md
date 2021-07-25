# micro-vanillajs-tictactoe
a micro-tiny-little tic tac toe built with html, css and vanilla js. 

## it's so tiny that I'll put the whole source code here:

```html
<html>
  <head>
    <style type="text/css">
      * {
        border: 1px solid black;
        margin: 0 auto;
        text-align: center;
      }

      td {
        width: 50px;
        height: 50px;
      }
    </style>
    <script type="text/javascript">
      var board = Array(9).fill()
      let player = 'x';
      let winBoards = [[0, 4, 8], [2, 4, 6], [0, 3, 6], [1, 4, 7], [2, 5, 8], [0, 1, 2], [3, 4, 5], [6, 7, 8]];

      function clickHandler(e) { 
        e.innerHTML = player
        if (board[e.id]) return;
        board[e.id] = player
        for (const b in winBoards) {
          if (winBoards[b].every(i => board[i] == player)) {
            confirm(`player ${player} wins !`) && location.reload()
          }
        }
        document.getElementById('player').innerHTML = player = player == 'x' ? 'o' : 'x'
      }
    </script>
  </head>
  <body>
    <table>
      <tr>
        <td onclick="clickHandler(this)" id="0"></td>
        <td onclick="clickHandler(this)" id="1"></td>
        <td onclick="clickHandler(this)" id="2"></td>
      </tr>
      <tr>
        <td onclick="clickHandler(this)" id="3"></td>
        <td onclick="clickHandler(this)" id="4"></td>
        <td onclick="clickHandler(this)" id="5"></td>
      </tr>
      <tr>
        <td onclick="clickHandler(this)" id="6"></td>
        <td onclick="clickHandler(this)" id="7"></td>
        <td onclick="clickHandler(this)" id="8"></td>
      </tr>
      <tfooter>
        <td colspan="3">
          <p id="score-title" align="center">turn:</p>
          <p id="player" align="center">x</p>
        </td>
      </tfooter>
    </table>    
  </body>
</html>
```

# that's all folks
