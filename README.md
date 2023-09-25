# context API

![Alt text](src/screenshots/ksnip_20230925-122014.png)

![Alt text](src/screenshots/ksnip_20230925-122410.png)

**Context API** is a solution provided by React for managing and sharing state or data across multiple components in a more efficient way, especially when dealing with prop drilling becomes cumbersome. It allows you to create a central store of data that can be accessed by any component in your application without the need to pass props down the component tree manually.

Here's how you can use the Context API to address prop drilling:

**1. Create a Context**:

First, you need to create a context using the `createContext` function from React.

```jsx
import React, { createContext, useContext, useState } from "react";

// Create a context with an initial value (optional)
const MyContext = createContext();
```

**2. Provide Data**:

Wrap your entire application or the part of your application where you want to share data with a `Provider` component. The `Provider` component will supply the data to all components within its subtree.

```jsx
function App() {
  const [data, setData] = useState("Some data to share");

  return (
    <MyContext.Provider value={data}>
      {/* Rest of your application */}
    </MyContext.Provider>
  );
}
```

**3. Consume Data**:

In any component where you want to access the shared data, use the `useContext` hook to consume the context.

```jsx
function MyComponent() {
  const sharedData = useContext(MyContext);

  return <div>{sharedData}</div>;
}
```

By using the Context API, you can avoid prop drilling and directly access the shared data from any component within the context's provider. This makes it easier to manage global or shared state without passing props through intermediary components.

**Advanced Usage**:

- You can create multiple contexts for different parts of your application if needed.
- Context can also hold functions or objects, not just simple values.
- To update the context data, you can pass callback functions as part of the context value.

However, it's important to use context judiciously and not overuse it for every piece of shared data in your application, as it may make your code less predictable and harder to maintain in some cases. Consider using context for global state or shared data that genuinely needs to be accessible from multiple parts of your application.

# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

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

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

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
