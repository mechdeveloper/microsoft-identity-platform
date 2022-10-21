# Sign In Users - JavaScript

<https://learn.microsoft.com/en-us/azure/active-directory/develop/tutorial-v2-javascript-auth-code>

- Install Node JS
- Next, implement a small Express web server to serve your index.html file.

    ```
    npm init -y
    npm install @azure/msal-browser
    npm install express
    npm install morgan
    npm install yargs
    ```

- create file named `server.js`
- Create SPA UI
  - Create an `app` folder in your project directory, and in it create an `index.html` file for your JavaScript SPA. 
    - This file implements a UI built with the Bootstrap 4 Framework and imports script files for configuration, authentication, and API calls.
  - Also in the `app` folder, create a file named `ui.js`
    - This file will access and update DOM elements.

# Register your application

| | |
|-|-|
| Display Name | Demo Client Javascript SPA | 
| Application (client) ID | `26df9b5c-17d2-412c-bb3f-243ad21fbddd` |
| Directory Tenant ID | `2a8d6e38-f847-47c9-bf7d-71334a7a948d` | 

## Configure app registration with a Redirect URI using MSAL.js 2.0 with auth code flow (recommended)
<https://learn.microsoft.com/en-us/azure/active-directory/develop/scenario-spa-app-registration#redirect-uri-msaljs-20-with-auth-code-flow>

- Select __Authentication__ > __Add a platform__
- Select the __Single-page application__ tile.
- Under Redirect URIs, enter a redirect URI (`http://localhost:3000`). Do NOT select either checkbox under Implicit grant and hybrid flows.

  By configuring your redirect URI using the __Single-page application__ tile in the __Add a platform pane__, your application registration is configured to support the authorization code flow with PKCE and CORS.

- Configure  JavaScript SPA
- Create a file named `authConfig.js` in the `app` folder to contain your configuration parameters for authentication

- Create a file named `graphConfig.js` in the `app` folder to provide your application the configuration parameters for calling the Microsoft Graph API

  - `Enter_the_Graph_Endpoint_Here` is the instance of the Microsoft Graph API the application should communicate with.
    - For the global Microsoft Graph API endpoint, replace both instances of this string with https://graph.microsoft.com.

    values should look similar to following: 
    ```
    graphMeEndpoint: "https://graph.microsoft.com/v1.0/me",
    graphMailEndpoint: "https://graph.microsoft.com/v1.0/me/messages"
    ```

## Use the Microsoft Authentication Library (MSAL) to sign in user

- In the `app` folder, create a file named `authPopup.js`, this file contians authentication and token acquisition code for the __login pop-up__

- Create a file named `authRedirect.js` in the `app` folder, this file contains authentication and token acquisition code for __login redirect__

## Call Microsoft Graph API

- Create file named `graph.js` in the `app` folder, this file contains code for making REST calls to the Microsoft Graph API

## Test Application

- Start Node.js web server
```
npm start
```

- navigate to `http://localhost:3000` You should see the contents of your index.html file and the Sign In button.


