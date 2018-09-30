<!DOCTYPE html>
<html>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js"></script>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">

<style>
*{
    box-sizing: border-box;
}

/* Create two equal columns that floats next to each other */
.column1 {
    float: left;
    width: 30%;
    padding: 10px;
    /*height: 300px;  Should be removed. Only for demonstration */
}

.column4 {
    float: left;
    width: 80%;
    padding: 10px;
    /*height: 300px;  Should be removed. Only for demonstration */
}

.label1{
  text-align: right;
}

.column5 {
    float: right;
    width: 20%;
    padding: 10px;
    /*height: 300px;  Should be removed. Only for demonstration */
}

.column2 {
    float: left;
    width: 70%;
    padding: 10px;
    /*height: 300px;  Should be removed. Only for demonstration */
}

/* Clear floats after the columns 1E90FF */
.row:after {
    content: "";
    display: table;
    clear: both;
}

.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
  text-align: right;
  float: right;
}

.switchLabel{
	float: right;
	margin: 5px;
}

.switch input {display:none;}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: .4s;
  transition: .4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: .4s;
  transition: .4s;
}

input:checked + .slider {
  background-color: #2196F3;
}

input:focus + .slider {
  box-shadow: 0 0 1px #2196F3;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}

#myInput {
  background-image: url('/css/searchicon.png');
  background-position: 10px 12px;
  background-repeat: no-repeat;
  width: 100%;
  font-size: 16px;
  padding: 12px 20px 12px 40px;
  border: 1px solid #ddd;
  margin-bottom: 12px;
}

#myUL {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

#myUL li a {
  border: 1px solid #ddd;
  margin-top: -1px; /* Prevent double borders */
  background-color: #f6f6f6;
  padding: 12px;
  text-decoration: none;
  font-size: 18px;
  color: black;
  display: block
}

#myUL li a:hover:not(.header) {
  background-color: #eee;
}


#myInput {
  background-image: url('/css/searchicon.png');
  background-position: 10px 10px;
  background-repeat: no-repeat;
  width: 100%;
  font-size: 16px;
  padding: 12px 20px 12px 40px;
  border: 1px solid #ddd;
  margin-bottom: 12px;
}

#myInput2 {
  background-image: url('/css/searchicon.png');
  background-position: 10px 10px;
  background-repeat: no-repeat;
  width: 100%;
  font-size: 16px;
  padding: 12px 20px 12px 40px;
  border: 1px solid #ddd;
  margin-bottom: 12px;
}

#myTable {
  border-collapse: collapse;
  width: 100%;
  border: 1px solid #ddd;
  font-size: 18px;
}

#myTable th, #myTable td {
  text-align: left;
  padding: 12px;
}

#myTable tr {
  border-bottom: 1px solid #ddd;
}

#myTable tr.header, #myTable tr:hover {
  background-color: #f1f1f1;
}

#mytext {
    width: 40%;
}

.bckgndColor{
	background-color: lightblue;
}

.top-nav-bar {
    display: block!important;
}

.btn-secondary1 {
    color: #fff;
    background-color: #1274cc;
    border-color: #1a83e0;
}

.ul {  
  overflow: auto;
  margin: 0;
  padding: 0;  
  border: 2px solid #ccc;  
  font-size: 16px;
  font-family: Arial, sans-serif;
  
  // Again, this is where the magic happens
  -webkit-overflow-scrolling: touch;
}

</style>
</head>

<body>
<nav class="navbar navbar-expand-lg navbar-dark bg-primary">
<div class="container-fluid">
	<div class="row" >
		<h2>Data Dictionary</h2>
	</div>
</div>
</nav>
<div class="container-fluid">
	<div class="row">		
		<div class="column4">
		<label class="switchLabel">Table Data</label>
				<form action="">
					<label class="switch">	
					  <input  type="checkbox" checked  onclick="onCheckboxChange()" >
					  <span class="slider round"></span>    
					</label>
				</form>
		<label class="switchLabel">RAML Data</label>			
		</div>
		<div class="column5">
		<form class="form-inline my-2 my-lg-0">
			<button class="btn btn-secondary1 my-2 my-sm-0" type="button" data-toggle="modal" data-target="#loginModal">Refresh</button>
		</form>
		</div>
	</div>
</div>

<div class="container-fluid">
<div class="row">
<div class="column1" style="background-color:#aaa;">
<label class="">API Names</label>
<input type="text" id="myInput" class="mytext" onkeyup="myFunction()" placeholder="Search for names.." title="Type in a name">
<ul id="myUL" class="ul">

  <li class="menu-links__item--nested"><a href="#">odsAPI1</a></li>
  <li onclick="loadTable2()"><a href="#">odsAPI2</a></li>
  <li onclick="loadTable1()"><a href="#">odsAPI3</a></li>
  <li onclick="loadTable2()"><a href="#">odsAPI4</a></li>
  <li onclick="loadTable1()"><a href="#">odsAPI5</a></li>
  <li onclick="loadTable2()"><a href="#">odsAPI6</a></li>
  <li onclick="loadTable1()"><a href="#">odsAPI7</a></li>
  <li onclick="loadTable2()"><a href="#">odsAPI8</a></li>
  <li onclick="loadTable1()"><a href="#">odsAPI9</a></li>
  <li onclick="loadTable2()"><a href="#">odsAPI10</a></li>
</ul>

</div>
<div class="column2" style="background-color:#bbb;">   
	<label class="">End to End Data Mapping</label>
<input type="text" id="myInput2" class="mytext" onkeyup="myFunction2()" placeholder="Search for names.." title="Type in a name">
<table id="myTable">
  <tr class="header">
    <th style="width:33.33%;">Column1</th>
    <th style="width:33.33%;">Column2</th>
	<th style="width:33.33%;">Column3</th>
  </tr>
  <tr>
    <td>column1a</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1b</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1c</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1d</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
  
</table>
<table id="myTable2"  style="display:none"; >
  <tr class="header">
    <th style="width:33.33%;">Column1</th>
    <th style="width:33.33%;">Column2</th>
	<th style="width:33.33%;">Column3</th>
  </tr>
  <tr>
    <td>column1z</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1x</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1v</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1nn</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
<tr>
    <td>column1</td>
    <td>column2</td>
	<td>column3</td>
</tr>
  
</table>
<textarea id="textArea" name="hide" style="display:none;" disabled rows="30" cols="120" text="dsfsdgfsgsfgfgsd"> 

/songs:
  ...
  /{songId}:
    type: collection-item
    get:
      responses:
        200:
          body:
            application/json:
              example: |
                {
                  "songId": "550e8400-e29b-41d4-a716-446655440000",
                  "songTitle": "Get Lucky",
                  "duration": "6:07",
                  "artist": {
                    "artistId": "110e8300-e32b-41d4-a716-664400445500"
                    "artistName": "Daft Punk",
                    "imageURL": "http://travelhymns.com/wp-content/uploads/2013/06/random-access-memories1.jpg"
                  },
                  "album": {
                    "albumId": "183100e3-0e2b-4404-a716-66104d440550",
                    "albumName": "Random Access Memories",
                    "imageURL": "http://upload.wikimedia.org/wikipedia/en/a/a7/Random_Access_Memories.jpg"
                  }
                }




 </textarea>
<div  id="textArea1" class="container" style="display:none;"  >
	<div class="row">
	<code class="lang-yaml">	
	
	dddd
	</code>
	</div>
</div>
  </div>
</div>
</div>
<script>

function loadTable1(){
	if($("#myTable").is(":visible") == true ){
		$("#myTable").hide();
		$("#myTable2").show();	
		
	}else{
		$("#myTable").show();
		$("#myInput2").show();
	}

};


function onCheckboxChange(){
	if($("#myTable").is(":visible") == true && $("#myInput2").is(":visible") == true){
		$("#myTable").hide();
		$("#myInput2").hide();
		 document.getElementById("textArea").style.display = "block";		
	}else{
		$("#myTable").show();
		$("#myTable2").hide();
		$("#myInput2").show();
		document.getElementById("textArea").style.display = "none";
	}	
};
function myFunction() {
    var input, filter, ul, li, a, i;
    input = document.getElementById("myInput");
    filter = input.value.toUpperCase();
    ul = document.getElementById("myUL");
    li = ul.getElementsByTagName("li");
    for (i = 0; i < li.length; i++) {
        a = li[i].getElementsByTagName("a")[0];
        if (a.innerHTML.toUpperCase().indexOf(filter) > -1) {
            li[i].style.display = "";
        } else {
            li[i].style.display = "none";
        }
    }
}

function myFunction2() {
  var input, filter, table, tr, td, i;
  input = document.getElementById("myInput2");
  filter = input.value.toUpperCase();
  table = document.getElementById("myTable");
  tr = table.getElementsByTagName("tr");
  for (i = 0; i < tr.length; i++) {
    td = tr[i].getElementsByTagName("td")[0];
    if (td) {
      if (td.innerHTML.toUpperCase().indexOf(filter) > -1) {
        tr[i].style.display = "";
      } else {
        tr[i].style.display = "none";
      }
    }       
  }
}

</script>
</body>
</html>
