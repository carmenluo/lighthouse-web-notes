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
We would need to clean timer after we fire the effect because we don't want our application always keep track of the timers in the background. Simply by returning a function clearInterval would do the work.

![effect functions sequence](https://github.com/carmenluo/lighthouse-web-notes/blob/master/W7/9eb2f427-ba3d-4cfa-8705-33e2568edad0.png)

#### Props and State [toturial](https://codeburst.io/props-and-state-in-react-native-explained-in-simple-english-8ea73b1d224e)
<ol>
 <li>Props and state are two types of data that controls a component: <b>Props</b> is immutable because props are from their parent. In React, data flows in one direction: Parent to children. It can help us to create reusable code . See tutorial</li>
 <li><b>State</b>: State is internal to a componnet so that we can use it to keep track of data. Always use setState to update the state objects</li>
</ol>
