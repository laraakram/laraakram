
$(document).ready(function() {
  //Variables
  var selectedStarter = {
    dish: "(None)",
    price: 0
  };
  var selectedMain = {
    dish: "(None)",
    price: 0
  };
  var selectedDessert = {
    dish: "(None)",
    price: 0
  };
  var starter = {
    firstDish: "Salad",
    firstDishPrice: 15,
    secondDish: "Soup",
    secondDishPrice: 7,
    thirdDish: "Fish rolls",
    thirdDishPrice: 12
  };

  var main = {
    firstDish: "Steak",
    firstDishPrice: 17,
    secondDish: "Salmon",
    secondDishPrice: 12,
    thirdDish: "Rissotto",
    thirdDishPrice: 9
  };

  var dessert = {
    firstDish: "Sorbet",
    firstDishPrice: 4,
    secondDish: "Fruit salad",
    secondDishPrice: 6,
    thirdDish: "Apple pie",
    thirdDishPrice: 5
  };

  function total() {
    return selectedStarter.price + selectedMain.price + selectedDessert.price;
  }

  function selectedStarterFnc(dish, price) {
    selectedStarter.price = price;
    selectedStarter.dish = dish;
    $("#total").html(total());
    return dish + "(" + price + ")";
  }

  function selectedMainFnc(dish, price) {
    selectedMain.price = price;
    selectedMain.dish = dish;
    $("#total").html(total());
    return dish + "(" + price + ")";
  }

  function selectedDessertFnc(dish, price) {
    selectedDessert.price = price;
    selectedDessert.dish = dish;
    $("#total").html(total());
    return dish + "(" + price + ")";
  }

  // Instantiating HTML Button Elements
  // Starter Elements
  document.getElementById("btStarter1").value =
    starter.firstDish + ": " + starter.firstDishPrice;

  document.getElementById("btStarter2").value =
    starter.secondDish + ": " + starter.secondDishPrice;

  document.getElementById("btStarter3").value =
    starter.thirdDish + ": " + starter.thirdDishPrice;

  // Main Elements
  document.getElementById("btMain1").value =
    main.firstDish + ": " + main.firstDishPrice;

  document.getElementById("btMain2").value =
    main.secondDish + ": " + main.secondDishPrice;

  document.getElementById("btMain3").value =
    main.thirdDish + ": " + main.thirdDishPrice;

  // Dessert Elements
  document.getElementById("btDessert1").value =
    dessert.firstDish + ": " + dessert.firstDishPrice;

  document.getElementById("btDessert2").value =
    dessert.secondDish + ": " + dessert.secondDishPrice;

  document.getElementById("btDessert3").value =
    dessert.thirdDish + ": " + dessert.thirdDishPrice;

  // Your Order: Elements
  document.getElementById("selectedStarter").innerHTML =
    selectedStarter.dish + " (" + selectedStarter.price + ")";

  document.getElementById("selectedMain").innerHTML =
    selectedMain.dish + " (" + selectedMain.price + ")";

  document.getElementById("selectedDessert").innerHTML =
    selectedDessert.dish + " (" + selectedDessert.price + ")";

  // Functions (JQuery)
  // Main menu onClicks handler
  $("#btMenu").click(function() {
    $("#liMainMenu").toggle("slow");
  });

  $("#btStarter").click(function() {
    $("#liStarter").toggle("slow", function() {
      if ($(this).css("display") == "none") {
        $("#btStarter").css("background-color", "black");
      } else {
        $("#btStarter").css("background-color", "blue");
      }
    });
  });

  $("#btMain").click(function() {
    $("#liMain").toggle("slow", function() {
      if ($(this).css("display") == "none") {
        $("#btMain").css("background-color", "black");
      } else {
        $("#btMain").css("background-color", "blue");
      }
    });
  });

  $("#btDessert").click(function() {
    $("#liDessert").toggle("slow", function() {
      if ($(this).css("display") == "none") {
        $("#btDessert").css("background-color", "black");
      } else {
        $("#btDessert").css("background-color", "blue");
      }
    });
  });

  // Starter onClicks
  $("#btStarter1").click(function() {
    $("#liStarter").children("li").children("input").css("background-color", "red");
    $(this).css("background-color", "green");
    $("#selectedStarter").html(selectedStarterFnc(starter.firstDish, starter.firstDishPrice));
  });

  $("#btStarter2").click(function() {
    $("#liStarter").children("li").children("input").css("background-color", "red");
    $(this).css("background-color", "green");
    $("#selectedStarter").html(selectedStarterFnc(starter.secondDish, starter.secondDishPrice));
  });

  $("#btStarter3").click(function() {
    $("#liStarter").children("li").children("input").css("background-color", "red");
    $(this).css("background-color", "green");
    $("#selectedStarter").html(selectedStarterFnc(starter.thirdDish, starter.thirdDishPrice));
  });

  // Main onClicks
  $("#btMain1").click(function() {
    $("#liMain").children("li").children("input").css("background-color", "red");
    $(this).css("background-color", "green");
    $("#selectedMain").html(selectedMainFnc(main.firstDish, main.firstDishPrice));
  });

  $("#btMain2").click(function() {
    $("#liMain").children("li").children("input").css("background-color", "red");
    $(this).css("background-color", "green");
    $("#selectedMain").html(selectedMainFnc(main.secondDish, main.secondDishPrice));
  });

  $("#btMain3").click(function() {
    $("#liMain").children("li").children("input").css("background-color", "red");
    $(this).css("background-color", "green");
    $("#selectedMain").html(selectedMainFnc(main.thirdDish, main.thirdDishPrice));
  });

  // Dessert onClicks
  $("#btDessert1").click(function() {
    $("#liDessert").children("li").children("input").css("background-color", "red");
    $(this).css("background-color", "green");
    $("#selectedDessert").html(selectedDessertFnc(dessert.firstDish, dessert.firstDishPrice));
  });

  $("#btDessert2").click(function() {
    $("#liDessert").children("li").children("input").css("background-color", "red");
    $(this).css("background-color", "green");
    $("#selectedDessert").html(selectedDessertFnc(dessert.secondDish, dessert.secondDishPrice));
  });

  $("#btDessert3").click(function() {
    $("#liDessert").children("li").children("input").css("background-color", "red");
    $(this).css("background-color", "green");
    $("#selectedDessert").html(selectedDessertFnc(dessert.thirdDish, dessert.thirdDishPrice));
  });
});
.button {
  background: #353535;
  outline: solid 2px #353535;
  border: solid 2px white;
  color: white;
  padding: 10px 15px;
  text-decoration: none;
  width: 200px;
  margin-top: 50px;
}
.ul li {
  display: inline;
  margin-right: 8px;
}
.ul {
  display: none;
}
.table {
  margin-top: 50px;
  border: 10px solid blue;
  width: 33%;
}
.table th {
  padding-top: 20px;
  text-align: left;
  font-size: 24px;
  margin: 30px;
}
.table tr,
td {
  text-align: left;
  padding-left: 50px;
  padding-right: 20px;
  padding-top: 20px;
  padding-bottom: 20px
}
<!doctype html>
<html lang="en">

<head>
  <meta charset="utf-8">
  <title>Restaurant Menu With JQuery</title>
  <link rel="stylesheet" type="text/css" href="style.css">
  <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
</head>

<body>
  <input type="button" class="button" id="btMenu" value="Menu">
  <ul id="liMainMenu" class="ul">
    <li>
      <input type="button" class="button" id="btStarter" value="Starter">
    </li>
    <li>
      <input type="button" class="button" id="btMain" value="Main">
    </li>
    <li>
      <input type="button" class="button" id="btDessert" value="Dessert">
    </li>
  </ul>
  <ul id="liStarter" class="ul">
    <li>
      <input type="button" class="button" id="btStarter1" value="">
    </li>
    <li>
      <input type="button" class="button" id="btStarter2" value="">
    </li>
    <li>
      <input type="button" class="button" id="btStarter3" value="">
    </li>
  </ul>
  <ul id="liMain" class="ul">
    <li>
      <input type="button" class="button" id="btMain1" value="">
    </li>
    <li>
      <input type="button" class="button" id="btMain2" value="">
    </li>
    <li>
      <input type="button" class="button" id="btMain3" value="">
    </li>
  </ul>
  <ul id="liDessert" class="ul">
    <li>
      <input type="button" class="button" id="btDessert1" value="">
    </li>
    <li>
      <input type="button" class="button" id="btDessert2" value="">
    </li>
    <li>
      <input type="button" class="button" id="btDessert3" value="">
    </li>
  </ul>
  <table class="table">
    <th>Your Order:</th>
    <tr>
      <td>Starter :</td>
      <td id="selectedStarter"></td>
    </tr>
    <tr>
      <td>Main :</td>
      <td id="selectedMain"></td>
    </tr>
    <tr>
      <td>Dessert :</td>
      <td id="selectedDessert"></td>
    </tr>
    <tr>
      <td>Total :</td>
      <td id="total"></td>
    </tr>
  </table>
</body>
<script src="app.js" type="text/javascript"></script>

</html>
Full page
javascriptbeginnerjqueryhtmlcss
Share
Improve this question
Follow
edited Jun 13, 2016 at 18:08
asked Jun 13, 2016 at 15:50
Daniel Netzer's user avatar
Daniel Netzer
29922 gold badges44 silver badges1111 bronze badges
1
Now this question could use a better description of what the code does, and possibly be inserted into a StackSnippet. Do that and you've earned my upvote! – 
syb0rg
 Jun 13, 2016 at 16:02 
will do, and the StackSnippet is amazin
<!---
laraakram/laraakram is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
