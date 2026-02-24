<div class="section">
<h2>💰 Fare Calculator</h2>

<p>Enter Distance (KM)</p>
<input type="number" id="km" placeholder="Enter KM">

<br><br>

<label>
<input type="radio" name="time" value="day" checked> Day (₹20/km)
</label>

<label>
<input type="radio" name="time" value="night"> Night (₹35/km)
</label>

<br><br>

<button onclick="calculateFare()">Calculate Fare</button>

<div class="result" id="fareResult"></div>
</div>

<script>
function calculateFare() {
  var km = document.getElementById("km").value;
  var time = document.querySelector('input[name="time"]:checked').value;
  
  var rate = 20; // default day rate
  
  if(time === "night"){
    rate = 35;
  }

  if(km > 0){
    var total = km * rate;
    document.getElementById("fareResult").innerHTML = 
    "Estimated Fare: ₹ " + total;
  } else {
    document.getElementById("fareResult").innerHTML = 
    "Please enter valid KM";
  }
}
</script>
