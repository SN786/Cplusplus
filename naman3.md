<html>

<head>
  <title>Connect 4</title>
  <link rel="stylesheet" href="../static/css/c4styles.css">
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
  <script src="//cdnjs.cloudflare.com/ajax/libs/socket.io/2.2.0/socket.io.js"
    integrity="sha256-yr4fRk/GU1ehYJPAs8P4JlTgu0Hdsp4ZKrx8bDEDC3I=" crossorigin="anonymous"></script>
  <script src="../static/js/connect4.js"></script>
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"
    integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
</head>

<body>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <a class="navbar-brand" href="#">Multiplayer Game Server</a>
  </nav>

  <div id='2xFailAlert' class="alert alert-danger" role="alert" hidden>
    You don't have any 2x Multipliers!
  </div>

  <div id='2xPassAlert' class="alert alert-success" role="alert" hidden>
    Multiplier used!
  </div>

  <div id="connect4"></div>
  <script type="text/javascript">
    const user = `{{ email }}`;
    const playerColor = `{{ color }}`;
  </script>

  <!-- waiting message -->
  <div class="navbar-dark bg-dark" id="waiting">
      <b class="navbar-brand">Opponent is playing...</b>
  </div>

  <div id="parent">
    <div id="player1Color"></div>
    <div id="playerName">
      {% if color=="red" %}
      {{ fullName }}
      {% else %}
      {{ paired_email }}
      {% endif %}
    </div>
  </div>
  <div id="parent">
    <div id="player2Color"></div>
    <div id="playerName">
      {% if color=="red" %}
      {{ paired_email }}
      {% else %}
      {{ fullName }}
      {% endif %}
    </div>
  </div>

  <div class="modal fade" id="endModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle"
    aria-hidden="true" data-backdrop="static">
    <div class="modal-dialog modal-dialog-centered" role="document">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalCenterTitle">Game over!</h5>
        </div>
        <div class="modal-body">
          <b id='gameResult'></b>
          <br>
          <br>
          Your Earnings:
          <br>
          <img src="../static/images/cash.png" style="height: 4vh;">
          <b id='playerCash'></b>
          <br>
          <img src="../static/images/gold.jpeg" style="height: 3vh;">
          <b id='playerGold'></b>

</html>
