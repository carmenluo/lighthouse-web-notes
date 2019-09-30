## React
#### Fragment can be uesed to avoid using `<div>` to wrap a couple of tags
```

 class App extends React.Component {
    render() {
        return (
            <div>
                <p>I would</p>
                <p>really like</p>
                <p>to render</p>
                <p>an array</p>
            </div>
        );
    }
}
```
If we do it without `<div>` we will have error, because JSX is turning all of our `<div>` and `<MyComponent>` into `React.createElement()` calls - when the JSX transpiler sees multiple elements instead of a single element, it doesnt know what tag name to render with.
<br>
```
class App extends React.Component {
    render() {
        return (
            <>
                <p>I would</p>
                <p>really like</p>
                <p>to render</p>
                <p>an array</p>
            </>
        );
    }
}
```
Using framents is basically just like using `<div>`, but it'll behave functionally equivalent to the array-render method.
