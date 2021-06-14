State and Props
Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?
render first then componentDidMount
What is the very first thing to happen in the lifecycle of React?
The constructor for a React component is called before it is mounted.
Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Updates
constructor
render
componentDidMount
React Updates
componentWillUnmount
What does componentDidMount do?
Used for DOM mainupolation and network requests.
It is invoked after a component is mounted.
It is a good place to set up any subscriptions.
setState() can be called here, but it should be used sparingly.
how to include React Bootstrap in the project
Installation: npm install react-bootstrap bootstrap@4.6.0
Importing Components:` import Button from ‘react-bootstrap/Button’;
// or less ideally import { Button } from ‘react-bootstra`
Browser globals:`
`
CSS: `{/* The following line can be included in your src/index.js or App.js file*/}
import ‘bootstrap/dist/css/bootstrap.min.css’;`
React State Vs Props
What types of things can you pass in the props? props used to display things, like argument to function
What is the big difference between props and state? props: pass it to the component—-> updated outside the component state: it’s inside the component—->updated inside the component
When do we re-render our application? when we change the state inside of our application
What are some examples of things that we could store in state? use state to store date that are inside of a form like checkbox, textbox, or an input element that are being updated by the user.