# REACT JS  
## Description  
This repository contains the source code of the course about React Js for beginners.  
## Concepts  
A **React App** is a set of reusable components. It takes input  and produce elements of the user interfaces in the form of react elements. 
**Components:** 
It is compound of:
* States
* Props
In react there are two types of components: Function and class.   
**Function:** The functions are associated to presentational concept. It is the simplest form of react components. It could has props as inputs, and the output will be a DOM. That DOM looks like html but is a special sintax of javascript called JSX. For example:  
```javascript
const MyComponent = (props) => {
    return (
        <elementOrComponent.../>
    );
}
```
**Class:** It is a more featured way to defined a react component. States are private internal states that gives to React its reactive native. When the state of a React component changes, it will automaticly change his re-render that component.  
The difference between state and props is that the first can change, but props are fix or inmutable values. Clases just can change the internal state, not the properties.  

## Playground  
If you want to test some JSX or React code go to: https://jscomplete.com/repl.
There is an example of the code:  

```javascript
class Yesid extends React.Component {
    state = {counter: 0};
    handleClick = () => {
        this.setState( (prevState) => ({
            return({counter: prevState.counter + 1})
        }));
    };
        render() {
        return (
            <button onClick={this.handleClick}>{this.state.counter}</button>
        );
    };	
}

ReactDOM.render(<Yesid />, mountNode);
```
Now we can see how the components can be used in a reusable way: 
```javascript
class YesidComponent extends React.Component {
	handleClick = () => {
  	this.props.onClickFunction(this.props.incrementValue)
  };
  
	render() {
  	return (
    	<button onClick={this.handleClick}>+{this.props.incrementValue}</button>
    );
  };	
}
 
const Result = (props) => {
	return (
  	<div>Probando ando {props.counter}</div>
  );
};

class App extends React.Component {
	state = {counter: 0};

  incrementCounter = (increment) => {
    this.setState( (prevState) => {
        return({counter: prevState.counter + increment})
      });
  }

	render() {
  	return(
    	<div>
    		<YesidComponent incrementValue={1} onClickFunction={this.incrementCounter}/>
        <YesidComponent incrementValue={10} onClickFunction={this.incrementCounter}/>
        <YesidComponent incrementValue={5} onClickFunction={this.incrementCounter}/>
        <YesidComponent incrementValue={6} onClickFunction={this.incrementCounter}/>
        <Result counter={this.state.counter}/>
    	</div>
    );
  };
}

ReactDOM.render(<App />, mountNode);
```