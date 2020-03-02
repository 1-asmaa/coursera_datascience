<!DOCTYPE html>
<html>

<head>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
    integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">

  <style>
    table {
      text-align: center;
    }
  
  </style>
</head>

<body onload='sortTable()' id='myTable'>

  <div id="question"></div>

  <script>
    var Question = [{
      "Item1": "1-",
      "Questions": ["yes ", "No", "May be", "no comment", "no comment"],
      "LeftStatment": "LeftStatment0",
      "RightStatment": "RightStatment"
    }, {
      "Item1": "2-",
      "Questions": ["asd1", "asd2", "asd3", "asd4", "asd5"],
      "LeftStatment": "LeftStatment1",
      "RightStatment": "RightStatment"
    }, {
      "Item1": "3-",
      "Questions": ["asmaa", "asmaa", "asmaa", "asmaa", "asmaa"],
      "LeftStatment": "LeftStatment2",
      "RightStatment": "RightStatment"
    }, {
      "Item1": "4-",
      "Questions": ["Rory", "Rory", "Rory", "Rory", "Rory"],
      "LeftStatment": "LeftStatment3",
      "RightStatment": "RightStatment"
    }, {
      "Item1": "5-",
      "Questions": ["Jekyll", "Jekyll", "Jekyll", "Jekyll", "Jekyll"],
      "LeftStatment": "LeftStatment3",
      "RightStatment": "RightStatment"
    }, {
      "Item1": "6-",
      "Questions": ["verymuch", "verymuch", "verymuch", "verymuch", "verymuch"],
      "LeftStatment": "LeftStatment3",
      "RightStatment": "RightStatment"
    }, {
      "Item1": "7-",
      "Questions": ["asd3", "No", "MAy be", "no comment", "no comment"],
      "LeftStatment": "LeftStatment3",
      "RightStatment": "RightStatment"
    }, {
      "Item1": "8-",
      "Questions": ["asd3", "No", "MAy be", "no comment", "no comment"],
      "LeftStatment": "LeftStatment3",
      "RightStatment": "RightStatment"
    }];


    var str = " ";

 

    for (let i = 0; i < Question.length; i++) {

      str += "<div class='table-responsive' ><table   class='table table-sm table-content table-hover table-striped  table-bordered '>"

      str += "<tr><td></td>"
      for (let j = 0; j < Question[i].Questions.length; j++) {
        /* put style='width:125px;' here */
        str += "<td style='width:125px;'>" + Question[i].Questions[j] + "</td>";

      }
      str += "<td></td></tr>"


    /*Remove this line */--> //str+="<tr><td>"+Question[i].Item1 +"</td>";    
      str += "<td>" + Question[i].LeftStatment + "</td>";


      for (let j = 0; j < Question[i].Questions.length; j++) {
        var name = Question[i].Item1;
        str += "<td>" + "<input type='radio' name=" + name + " /></td>";
      }
      str += "<td >" + Question[i].RightStatment + "</td></tr>";

     
      str += "</table>"

    }

    document.getElementById('question').innerHTML = str;





    function sortTable() {
      //get the parent table for convenience

      let table = document.getElementById("myTable");

      //1. get all rows
      let rowsCollection = table.querySelectorAll("table");

      //2. convert to array
      let rows = Array.from(rowsCollection); //skip the header row

      //3. shuffle
      shuffleArray(rows);

      //4. add back to the DOM
      for (const row of rows) {
        table.appendChild(row);
      }
    }


    /**
     * Randomize array element order in-place.
     * Using Durstenfeld shuffle algorithm.
     * from: https://stackoverflow.com/questions/2450954/how-to-randomize-shuffle-a-javascript-array/12646864#12646864
     */
    function shuffleArray(array) {
      for (var i = array.length - 1; i > 0; i--) {
        var j = Math.floor(Math.random() * (i + 1));
        var temp = array[i];
        array[i] = array[j];
        array[j] = temp;
      }
    }

  </script>
</body>

</html>
