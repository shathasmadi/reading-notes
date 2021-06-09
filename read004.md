# Read: Class 04
## Readings: React and Forms
### Forms
#### What is a ‘Controlled Component’?
it is an element that when its value will change, it will be updated by setState and passed by props, this changing will be notifyed by the parent component and will control it.
#### Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.
No, beacuase we uesd the controlled component in form, like onChange property, that is means you will get the updated data directly when ever the user change anything in the input field. it will be updated in your states. and when you submit the form you will have the updated value that user has entered.
#### How do we target what the user is entering if we have an event handler on an input field?

by storing this value by setState in the onChange function, the target will be : event.target.name.value.

### The Conditional (Ternary) Operator Explained


#### Why would we use a ternary operator?
beacause it is easy to use, and it is shorter than if & else statements and it do the same functionality.

#### Rewrite the following statement using a ternary statement:
  if(x===y){
 console.log(true);
  } else {
 console.log(false);
  }
  
  Answer: 
  x===y ? console.log(true) : console.log(false)
  
  ## Resources:
  [React Docs - Forms](https://reactjs.org/docs/forms.html)
  
  [The Conditional (Ternary) Operator Explained](https://codeburst.io/javascript-the-conditional-ternary-operator-explained-cac7218beeff)
  