# hello-login
## Task
1. create a component `Login` which contains two inputs:
    1. username
    1. password
    and a button to login.
1. render the Login component in the App component.
1. Use useState to control the inputs of the Login component. (This means storing the values of the inputs in a state and changing them by passing a function to the onChange prop of the inputs.)
1. Add a prop called `onLogin` to the Login component.
1. The onLogin prop takes a function which is called by the Login component with a token if the login was successful.
1. Create a function called `handleLogin` in the App component and pass it to the Login component via the `onLogin` prop we created. The handleLogin function takes a token as an argument when it is called by the Login component.
1. Print the token that is returned.
## Task 2
1. Whenever the login button is clicked, take the input data for username and password and send it to the `/login` endpoint of our api at https://demo-api-react-2020.herokuapp.com/login.  
  The api expects a body which contains username and password as a json object. The HTTP method has to be `POST`. You can use fetch or axios.  
  Example for doing a POST request with axios:
```ecmascript 6
axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
``` 
1. If the login request was correct (it is for username `admin` and password `demo`), a `token` is returned in the response.data object. Return this token to the App component via the callback function `onLogin`.
1. Store the token in the state of the App component using `useState`.
## Task 3
1. Create a new component called UserProfile
1. UserProfile takes the token as a prop.
1. If the token is not empty, UserProfile makes a GET request to `/user/me`. To be allowed to access that endpoint, you must set an HTTP Authorization header with the value `Bearer <token>` with `<token>` being the Jsonwebtoken you got from Login and which should already be saved in the state of App. See below for an example for the axios request.  
```ecmascript 6
axios.get('/your-endpoint', {
    headers: {'X-YourHeader': 'Your header value'},
  })
```
1. Render the username that is returned by the GET request in the UserProfile component.
## Task 4 (Optional)
1. Add a logout button which clears the token and make sure that the UserProfile does not show the Username anymore when the user is logged out.
## Task 5 (Optional)
1. Use the React Context API to pass the token to the UserProfile component. You can have a look at `session-6/hello-react-context` for an example. 


# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
