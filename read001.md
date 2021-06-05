# Things I want to know more about


**Component Based Architecture**

**What is a component?**

A component it is a higher-level interface and is a modular, portable, replaceable, and reusable set of well-defined functionality. And it have three different views: 
 * object-oriented view
 * conventional view
 * process-related view

**What are the charactistics of a component?**

* *Reusability*: the component are desgied to be reused in different situations.

* *Replaceable:* it is freely substituted with other similar component.

* *Not context specific:* designed to operate in different environments and contexts.

* *Extensible:* extended from existing components to provide new behavior.

* *Encapsulated:* it allows the caller to use its functionality.

* *Independent:* designed to have minimal dependencies on other components. 

**What are the advantages of using component based architecture?**

Component have a lot of advantages:

* Ease of deployment

* Reduced cost 

* Ease of development

* Reusable  
* Modification of technical complexity 
* Reliability 
* System maintenance and evolution
* Independent



 **Props and How to Use it in React**

**What is props short for?**

Its stands for properties used for passing data from one component to another. And data with props are being passed in a uni-directional flow also props data is read-only

>Props are arguments passed into React components. — w3schools.com


**How are props used in React?**

1. define an attribute and assign it a value.
2. then we pass it to child component by **props**.
3. reder the props data.



What is the flow of props?
* 1st: Defining Attribute & Data: we define our own attributes & assign values with interpolation { }

Example: `<ChildComponent someAttribute={value} anotherAttribute={value}/>`

* 2nd: Passing Data using Props: we can Passing props Like we pass arguments to a function.

Example: `const addition = (firstNum, secondNum) => {  
  return firstNum + secondNum; 
};`

* Final Step: Rendering Props Data: we reneder the property that we passed into the props by interpolation.

Example: `const ChildComponent = (props) => {  
  return <p>{props.text}</p>; 
};`


>React is a JavaScript library, objects are called “React elements” 

>JSX( stands for JavaScript XML):  It allows React to show more useful error and warning messages.And JSX allows us to write HTML in React. You can put any valid JavaScript expression inside the curly braces in JSX. 

>React DOM takes care of updating the DOM to match the React elements. To render a React element into a root DOM node, pass both to ReactDOM.render().

>Components and Props: components are like JavaScript functions. Props return React elements describing what should appear on the screen and its read-only.