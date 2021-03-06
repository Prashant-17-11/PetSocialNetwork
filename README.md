# Social Network for Pets

This project is built under react101 course from codecademey.
The objective is to learn about lifecycle events.

In this project, we will build a simple social network for pets. We will be able to view a pet's profile and navigate to other profiles. There will also be a profile directory where we can see all of the profiles.
There have been three profiles set before hand.

## Task 1

The first thing we'll want to do is load user data into the componet's state. In order to do that, however, we'll need a place to store that data.
Look into Profile.js.

Create a consturctor for this component. Inside, set this.state to {usedData: null}, which will represent a profile with no user data loaded. Don't forget to call super.

## Task 2

Now we have a place to store our data, let's start loading it.

Create a new method called loadUserData() that does two things:

 <ol>
    <li>Set the userData state to null while the data is loading. Once it's loaded, we'll update it.</li>
    <li>Fetches the user data with fetchUserData</li>
 </ol>

(Note: fetchUserData simulates real user data)

## Task 3

Now that we have a method for loading user data, let's call it when the component mounts.

Add a lifecycle method for when the component mounts, and call this.loadUserData() inside.

## Task 4

We're now loading user data, but we aren't displaying it anywhere because we haven't updated the render() method. Let's fix that!

The firs thing we'll need to change is isLoading. It shouldn't always be true - it should only be true when this.state.userData === null. Updata isLoading to reflect that.

## Task 5

Let's start by displaying the user's name.

Inside of render(), create a new variable called name.

If isLoading is true, set name to a sample value, such as 'Loading...'. Otherwise, set name to this.state.userData.name.

Finally, replace "Name goes here" with {name}.

## Task 6

Time to do the same exact thing, but for user's bio.

## Task 7

Let's update the user's friend list.

Create a new variable called friends inside render(). When the component is loading, friends should be the empty array([]). Otherwise, it should be this.state.useData.friends.

Next, update the usernames prop of the Userlist component. Change it from empty array to {friends}.

## Task 8

Let's update the users profile picture.

Find the div with the class name of profile-picture.
For ifLoading == false put an image tag with src={this.state.userData.profilePictureUrl} and alt=""

## Task 9

Cleaning Up

There are two problems left to fix!

<ol>
<li>If you open a profile, then quickly return to the directory, then go to a differnt pet's profile, there will be some jitter</li>
<li>If you click on a pet's friends, only the username updates.</li>
</ol>

Let's start with the first problem:

We'll slove this by canceling the fetch when Profile unmouns.
Add a lifecycle method for when the component unmounts, and call cancelFetch(this.fetchID) inside.

## Task 10

Let's solve the final problem.
Add a lifecycle method for when the component updates. If the usrname has changed (in other words, if this.props.username !== prevProps.username), we should do two things:

<ol>
<li>Cancel the fetch currently in progress with cancelFetch(this.fetchID)</li>
<li>Call this.loadUserData() again.</li>
</ol>

Once that's done we will be able to navigate through profiles with ease.

Voila!! Project finished successfully!!!

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

**Note: this is a one-way operation. Once you `eject`, you can???t go back!**

If you aren???t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you???re on your own.

You don???t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn???t feel obligated to use this feature. However we understand that this tool wouldn???t be useful if you couldn???t customize it when you are ready for it.

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
