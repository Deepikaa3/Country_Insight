# Country_Insight
Project Description:
The "Country Insight" web application is designed to provide information about a specific country. Users can enter a country name, and the application will fetch and display various details about that country, including its flag, capital, continent, population, currency, and common languages. The application is designed with a user-friendly interface and responsive design, making it accessible on various devices.

API Used:
The application utilizes the Restcountries API to retrieve data about countries. It specifically uses the following endpoint to fetch information about a given country:
- Endpoint: https://restcountries.com/v3.1/name/{countryName}?fullText=true

Event Handling Functions:
1. *Search Button Click Event:*
   - When the "Search" button is clicked, the searchBtn event listener is triggered.
   - It retrieves the value entered in the input field (country name).
   - Constructs the API URL with the country name.
   - Performs a fetch request to the API endpoint using fetch.
   - Parses the response data as JSON and processes it.
   - Dynamically updates the HTML content in the result element to display information about the selected country.

Here is the event handling function for the "Search" button:

javascript
searchBtn.addEventListener("click", () => {
  let countryName = countryInp.value;
  let finalURL = `https://restcountries.com/v3.1/name/${countryName}?fullText=true`;

  fetch(finalURL)
    .then((response) => response.json())
    .then((data) => {
      // Update HTML content to display country information
      result.innerHTML = `
        <!-- Display country information using fetched data -->
      `;
    })
    .catch(() => {
      // Handle errors or invalid input
      if (countryName.length == 0) {
        result.innerHTML = `<h3>The input field cannot be empty</h3>`;
      } else {
        result.innerHTML = `<h3>Please enter a valid country name.</h3>`;
      }
    });
});


The event handling function constructs the API URL, fetches data, and updates the content dynamically to provide insights about the selected country. It also includes error handling for empty input or invalid country names.
