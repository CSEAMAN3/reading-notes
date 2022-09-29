# React and Forms

##### Reference Links

https://reactjs.org/docs/forms.html

https://formik.org/



#### Questions

React Docs - Forms

1) What is a ‘Controlled Component’?

A controlled component is a component that renders form elements and controls them by keeping the form data in the component's state. In a controlled component, the form element's data is handled by the React component (not DOM) and kept in the component's state. 


2) Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.

We should update the state with their responses as soon as they happen. This means you can now pass the value to other UI elements too, or reset it from other event handlers.

3) How do we target what the user is entering if we have an event handler on an input field?

We use an onChange handler to listen for changes to input elements and record their values in state. Besides handling just one input, a single onChange handler can be set up to handle many different inputs in the form.


The Conditional (Ternary) Operator Explained

1) Why would we use a ternary operator?



2) Rewrite the following statement using a ternary statement:

```

if(x===y){
  console.log(true);
} else {
  console.log(false);
}

```

re-written

```

x === y ? console.log(true) : console.log(false)

```


