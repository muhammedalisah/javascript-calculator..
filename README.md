# javascript-calculator..
b
# JavaScript Calculator
HTML, CSS ve Vanilla JavaScript ile yapılmış basit hesap makinesi.
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Calculator</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="calculator">
    <input type="text" id="result" readonly>
    <div class="row">
      <button onclick="clearResult()">C</button>
      <button onclick="append('/')">/</button>
      <button onclick="append('*')">*</button>
      <button onclick="append('-')">-</button>
    </div>
    <div class="row">
      <button onclick="append('7')">7</button>
      <button onclick="append('8')">8</button>
      <button onclick="append('9')">9</button>
      <button onclick="append('+')">+</button>
    </div>
    <div class="row">
      <button onclick="append('4')">4</button>
      <button onclick="append('5')">5</button>
      <button onclick="append('6')">6</button>
      <button onclick="calculate()">=</button>
    </div>
    <div class="row">
      <button onclick="append('1')">1</button>
      <button onclick="append('2')">2</button>
      <button onclick="append('3')">3</button>
      <button onclick="append('0')">0</button>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>
body{display:flex;justify-content:center;align-items:center;height:100vh;background:#f2f2f2;margin:0}
.calculator{background:#fff;padding:20px;border-radius:10px;box-shadow:0 2px 8px rgba(0,0,0,0.1)}
#result{width:100%;padding:10px;margin-bottom:10px;font-size:18px}
.row{display:flex;justify-content:space-between}
button{flex:1;margin:4px;padding:12px;font-size:16px;border:none;border-radius:6px;cursor:pointer}
function append(v){
  document.getElementById("result").value += v;
}
function clearResult(){
  document.getElementById("result").value = "";
}
function calculate(){
  try{
    let res = eval(document.getElementById("result").value);
    document.getElementById("result").value = res;
  }catch(e){
    alert("Geçersiz ifade");
  }
}
