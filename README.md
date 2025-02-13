**Project Description**

For my Meet App, I will be using serverless functions, progressive web application (PWA) with React using a test-driven development (TDD) technique. This application uses the Google Calendar API to fetch upcoming events.

The Meet app is a progressive web application with a serverless backend, offering offline access to upcoming events in specific cities. Its responsive design ensures seamless display across devices, delivering a superior user experience. Powered by Test-Driven Development, it prioritizes code quality and test coverage for optimal performance.
This project is developed using REACT.

**User Stories**
As a user, I should be able to filter events by city so that I can see a list of events taking place in that city.

As a user, I should be able to show and hide event details in order to have control over the amount of information displayed.

As a user, I should be able to see a specific number of events, so can I can quickly find and browse through a list of events without being overwhelmed by too much information.

As a user, I should be able to use the App when offline, so that I have the Events list and info related to them at all times.

As a user, I should be able to add a shortcut to the home screen, so that I have easy access to the app.

As a user, I should be able to see charts visualizing event details, so that I would better understand the data associated with events and make a choise.

**Scenarios**
**SCENARIO 1**
When user hasn’t searched for a specific city, show upcoming events from all cities.

Given user hasn’t searched for any city;

When the user opens the app;

Then the user should see a list of upcoming events.

**SCENARIO 2**
User should see a list of suggestions when they search for a city.

Given the main page is open;

When user starts typing in the city textbox;

Then the user should receive a list of cities (suggestions) that match what they’ve typed.

**SCENARIO 3**
User can select a city from the suggested list.

Given user was typing “Berlin” in the city textbox AND the list of suggested cities is showing;

When the user selects a city (e.g., “Berlin, Germany”) from the list;

Then their city should be changed to that city (i.e., “Berlin, Germany”) AND the user should receive a list of upcoming events in that city.

**SCENARIO 4**
User has clicked to expand show more details of the event

Given user has decided to click on an event to see more details;

When user clicks on a button or card;

Then the user should see more details of the event.

**SCENARIO 5**
User has displayed on the page a specific number of events;

Given user selected a city for ex. "Berlin" from the list.

When user clicks on the city;

Then the user should see a specific number of events, 32 at a time.

**SCENARIO 6**
User has the app installed or shortcut on home screen but no internet connection.

Given user clicked on the shortcut;

When user clicks on the shortcut;

Then user should be able to use the app offline and see the events of a chosen city (e.g., “Berlin, Germany”).

**SCENARIO 7**
User has the app open and decides to create a shortcut for home creen.

Given user clicked on the button "Create home shortcut";

When user clicks on the button "Create home shortcut";

Thenuser should be able to find the shortcut on the home screen.

**SCENARIO 8**
User is planning a weekend and browses through a list of upcoming events based on city(e.g., “Berlin, Germany”).

Given user chooses an event of interest but unsure about the details and attendance trends. Navigates to the event page and notices a chart visualization option available;

When user taps on chart visualisation icon;

Then user should see a graphical representation of attendance trends, ticket prices, or event popularity over time is displayed.




In this project, created serverless functions using both AWS Lambda and the Serverless Toolkit to get the authorization server up and running. Once the authorization server for the Meet app is in existence, users of the app will be able to connect to the Google Calendar API by way of an access token.

In Exercise 4.3, created the following serverless functions - > getAuthURL() and getAccessToken() & getCalendarEvents().

Steps in the workflow -- 
1. When users first visit the app, a check occurs to see if they’re authorized.
2. If they’re not authorized, users are redirected to the Google authorization screen (i.e., getAuthURL).
3. At the Google authorization screen, users can sign in with their Google credentials, which authorizes their access to the app.
4. Once authorized, users will be redirected to your app with a code parameter in the URI.
5. The code parameter is then exchanged for an access token—this is done by sending it to the getAccessToken serverless function.
6. The function then checks the validity of the code with Google. If valid, the function returns the access token.
7. Once the token is received, it’s saved in a cookie in local storage, which is sent to the getCalendarEvents serverless function. This function then uses the token to get the events from the Google Calendar API.


Note:There are two steps to creating a new function to be deployed to AWS Lambda (listed in the order that you followed for your first function):

Step 1. Update the serverless.yml file to tell Serverless what the function is and how to deploy it.
Step 2. In your handler.js file, create the function and export it using Node.js module exports.


Additional notes : 
After making any changes to the serverless code, it needs to be deployed to AWS Lambda using the command 'serverless deploy'. 
This needs to be run from the directory 'meet\auth-server'.

The command to run this application locally on the machine is 'http-server'. 
This needs to be run from the directory 'meet\static-site-test'.


In Exercise 4.5 - 
 Used React Testing Library to create unit and integration tests. You also dove into the world of serverless functions, using Lambda to write functions for retrieving and managing access and refresh tokens for the Google Calendar API, which you then integrated into your app.

 In Exercise 4.9 - 
 Progressive web apps are discussed. This enables achievement of Scenario 6 & 7 described above.

 Note: To run the code locally on the box, use the command -> npm run start
 It can also be run from online Github if the code is synced there.