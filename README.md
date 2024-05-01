//establishes original variables 
var distanceList = getColumn("Planets of our Solar System", "Distance from sun");
var dayLengthList = getColumn("Planets of our Solar System", "Length of day");
var planetList = getColumn("Planets of our Solar System", "Planet");
var iconList = getColumn("Planets of our Solar System", "Picture");

//filteres variables
var filteredDistance = [];
var filteredDay = [];
var filteredPlanet = [];
var filteredIcon = [];

//appends items based on distance length
onEvent("getPlanet", "click", function( ) {
  for (var i = 0; i < distanceList.length; i++) {
    if(distanceList[i]>=100) {
    appendItem(filteredDistance, distanceList[i]);
    appendItem(filteredPlanet, planetList[i]);
    appendItem(filteredIcon, iconList[i]);
    }
  }
});

//appends items based on day length
onEvent("getPlanet2", "click", function( ) {
  for (var i = 0; i < dayLengthList.length; i++) {
    if (dayLengthList[i]>=10) {
      appendItem(filteredDay, dayLengthList[i]);
      appendItem(filteredPlanet, planetList[i]);
      appendItem(filteredIcon, iconList[i]);
    }
  }
});


function updateScreen1() {
  var index = randomNumber(0, planetList.length-1);
  setText("planetOutput", filteredPlanet[index]);
  setText("distanceOutput", filteredDistance[index]);
  setProperty("iconOutput", "image", filteredIcon[index]);
}
onEvent("getPlanet", "click", function( ) {
  updateScreen1();
});

function updateScreen2() {
  var index = randomNumber(0, planetList.length-1);
  setText("planetOutput2", filteredPlanet[index]);
  setText("dayLengthOutput", filteredDay[index]);
  setProperty("iconOutput2", "image", filteredIcon[index]);
}
onEvent("getPlanet2", "click", function( ) {
  updateScreen2();
});

onEvent("distanceButton3", "click", function( ) {
  setScreen("distanceScreen");
});
onEvent("hoursButton", "click", function( ) {
  setScreen("daylengthScreen");
});
onEvent("dayLengthButton", "click", function( ) {
  setScreen("daylengthScreen");
});
onEvent("distanceButton", "click", function( ) {
  setScreen("distanceScreen");
});
onEvent("homeButton", "click", function( ) {
  setScreen("screen1");
});
onEvent("homeButton2", "click", function( ) {
  setScreen("screen1");
});
