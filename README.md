# Weather-App-
Weather App 
function getWeatherData(latitude, longitude) {
  const url = `${apiUrl}&lat=${latitude}&lon=${longitude}`;
  fetch(url)
    .then(response => response.json())
    .then(data => {
      // extract required data from the response and update UI
    })
    .catch(error => {
      console.log(error);
      // display error message to user
    });
}

function getLocation() {
  if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(position => {
      const { latitude, longitude } = position.coords;
      getWeatherData(latitude, longitude);
    }, error => {
      console.log(error);
      // display error message to user
    });
  } else {
    // geolocation not supported by browser
  }
}

// call getLocation to get weather data for user's location
getLocation();
