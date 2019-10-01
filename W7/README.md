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

#### React to return list
When we use map to return items, compare
```
const listItems = props.days.map(day => 
    <DayListItem
      name={day.name}
      spots={day.spots}
      selected={day.name === props.day}
      setDay={props.setDay} />
  );
```
```
const listItems = props.days.map(day => {
return
    <DayListItem
      name={day.name}
      spots={day.spots}
      selected={day.name === props.day}
      setDay={props.setDay} />
  });
```
if use curly bracket for the arrow function, you need to return otherwise it is going to be undefined.<br>

#### Example of encapsulating and reusing Components
Before
```
function Clock(props) {
  return (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {props.date.toLocaleTimeString()}.</h2>
    </div>
  );
}
function tick() {
  ReactDOM.render(
    <Clock date={new Date()} />,
    document.getElementById('root')
  );
}

setInterval(tick, 1000);
```
After:
```
function tick(){
  ReactDOM.render(
  <Clock date={new Date()} />,
    document.getElementById('root'))
}
setInterval(tick, 1000);
class Clock extends React.Component {
  render() {
     return (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {this.props.date.toLocaleTimeString()}.</h2>
    </div>
  );
  }
}
```
Five steps to do that:
<ul>
 <li>Create an ES6 class, with the same name, that extends React.Component. </li>

 <li>Add a single empty method to it called render().</li>

 <li>Move the body of the function into the render() method.</li>

 <li>Replace props with this.props in the render() body.</li>

 <li>Delete the remaining empty function declaration.</li>
</ul>
#### useEffect
useEffect is also hooks, if we don't pass into dependencies, it will re-render every single time the components get changed, which means our website would be reloading basicailly all the time. Because we have the side effect from fetch.
dependency array: nothing means everytime, empty means once, data means only when this data change.
