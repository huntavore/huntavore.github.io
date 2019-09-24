<html><head>
<title>Huntavore Deers Scoring System</title>

<meta name="GENERATOR" content="Internet Assistant for Microsoft Word 2.0z Beta">
</head>

<body>
<h1><center>Huntavore Deer Scoring System</center></h1>
<h4><center>What did your deer really score?</center></h4>

<form method="post">

<script type="text/javascript">
    function myFunction() { 
      var total = 0;
      total += parseInt(document.querySelector('input[name="recovered"]:checked').value); //50 points for recovered deer
      total += parseInt(document.querySelector('input[name="public"]:checked').value); //15 bonus points for public
      total += parseInt(document.getElementById("points").value); //1 pt for each ring
      total += (parseInt(document.getElementById("stickers").value) * 5); //5 bonus points for each sticker
      total += (parseInt(document.getElementById("organs").value) * 5); //5 pts for each organ
      var weight = parseInt(document.getElementById("weight").value);
      if(weight > 100){
        total += (weight-100); //1 pt for every pound above 100
      }
      var usable = ((parseInt(document.getElementById("weight").value) /1.331)*.67*.7);
      var meat = parseInt(document.getElementById("meat").value);
      if(meat > usable){
        total += ((meat-usable)*2); //2 pt for every pound above realistic
      }
      total += (parseInt(document.getElementById("distance").value)/.25); //1 pt for every .25 miles of drag
      document.getElementById("score").innerHTML = "Total Score: " + total;
    }
</script>

<p>
The purpose of the Huntavore scoring system is to focus on the hunt rather on just the antlers. 

<p>
Was the deer recovered? <input type="RADIO" name="recovered" value="50" checked>Yes 
                        <input type="RADIO" name="recovered" value="0">No
</p>

<p>
Was the deer recovered on public land? <input type="RADIO" name="public" value="15" checked>Yes 
                                       <input type="RADIO" name="public" value="0">No
</p>

<p>
If it was a buck, how many points did it have? To count the point has to hold  a ring. 
<input type="number" id="points" value="0" required>
</p>

<p>
How many stickers or drop tines did the buck have? Get some bonus points for character!
<input type="number" id="stickers" value="0" required>
</p>

<p>
How many organs did you recover for consumption?
<input type="number" id="organs" value="0" required>
</p>

<p>
How much did your deer weigh field dressed? Hanging carcass weight.
<input type="number" id="weight" value="0" required>
</p>

<p>
How many pounds of butchered meat did you end up with after butchering?
<input type="number" id="meat" value="0" required>
</p>

<p>
How far was the drag out? Only count non-motorized recovery distance and be accurate down to the quarter mile. 
<input type="number" id="distance" step="0.01" value="0" required>
</p>
<button type="button" onclick="myFunction()">What's my score?</button>

<p id="score">
Total Score: 0 
</p>

</form>
</body></html>
