$(function(){
 
  var computerScore=0,
      playerScore=0;
  
  function setText(txt){
    $("#playerScore").text(playerScore);
    $("#computerScore").text(computerScore);
    $("#result").text(txt);
  }
  
  function makeComputerChoice(){
      var computerChoice = "";
      var r = Math.random();
      if (r < .33) {
        computerChoice = "rock";
      } else if (r < .66) {
        computerChoice = "paper";
      } else {
        computerChoice = "scissors";   
      };
      return computerChoice;
  }


    function makeUserChoice(userChoice){
      var computerChoice = makeComputerChoice();
      var outcome = "";
    if (userChoice == computerChoice) {
        outcome="Tie!";
    } else if (userChoice == "rock") {
        if (computerChoice == "scissors") {
            outcome="You win!"; playerScore=playerScore+1;
        } else {
            outcome="You lose."; computerScore=computerScore+1;
        };
    } else if (userChoice == "paper") {
        if (computerChoice == "rock") {
            outcome="You win!"; playerScore=playerScore+1;
        } else {
            outcome="You lose."; computerScore=computerScore+1;
        };
    } else if (userChoice == "scissors") {
        if (computerChoice == "paper") {
            outcome="You win!"; playerScore=playerScore+1;
        } else {
            outcome="You lose"; computerScore=computerScore+1;
        };
    };
      setText(userChoice+" vs "+computerChoice+" = "+outcome);
    };
  
  //add event listeners:
  $('#rock').click(function() {
            makeUserChoice("rock");
        });
        $('#paper').click(function() {
            makeUserChoice("paper");
        });
        $('#scissors').click(function() {
            makeUserChoice("scissors");
        });
});
body {
    font-family: Roboto, Arial; 
}

.choose img {
    width: 150px;
    margin: 20px;   
}
#result {color:red}
<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>
<div class="choose" align="center">
    <h1 id="question">Let's play rock paper scissors! Choose a move</h1>
  <h2 id="result"></h2>
<h2>[Player One] <span id="playerScore">0</span> - <span id="computerScore">0</span> [Computer]</h2>
    <img alt="Dwayne THE ROCK Johnson" src="http://d39ya49a1fwv14.cloudfront.net/wp-content/uploads/2015/06/The-Rock-4.png" id="rock">
    <img alt="Lined paper" src="http://images.clipartpanda.com/writing-on-paper-clipart-black-and-white-1206556249326967385nexxuz_Loose_Leaf_Paper.svg" id="paper">
    <img alt="Scissors" src="http://www.wpclipart.com/education/supplies/scissors/round-tip_scissors_blue.png" id="scissors">
</div>
