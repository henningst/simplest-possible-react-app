# simplest-possible-react-app
This repo contains the simplest possible React app.
It's just an index.html file with a single React component loading the required dependencies from CDN.

## Documentation

### Script includes

The required libraries are loaded directly from a CDN.
First we load the main `react` library, then we include `react-dom` library which provides DOM-specific
methods.

Since we are using ECMAscript 6 and JSX we also need the Babel compiler which is the third script tag.

```html
<script src="https://fb.me/react-15.0.0.js"></script>
<script src="https://fb.me/react-dom-15.0.0.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/babel-core/5.8.34/browser.min.js"></script>
```

### Add a container for the React app

To "connect" the React app with our html document, we create a div with an id.

```html
<div id="app-content"></div>
```

### Write a React component

The next thing we do is writing our first React *component*. The component is created as 
a class and has just one function called `render`. The `render`-function returns a simple text.

```javascript
var Greeting = React.createClass({
    render: function() {
        return (
        <p>Hello World, from React!</p>
        )
    }
});
```

### Initialize the React app

The last thing we do is to actually hook the React component up with out container div.
We use the `<Greeting />` component and say that it should be rendered in the element with id `app-content`. 

```javascript
ReactDOM.render(
    <Greeting/>,
    document.getElementById('app-content')
);
```

### Run the app

If you open `index.html` in your browser, you should see the text `Hello World, from React!`.