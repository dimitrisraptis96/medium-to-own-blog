---
title: "React: Event handlers on steroids"
description: "TLDR:"
date: "2020-01-29T12:36:17.707Z"
categories: []
published: false
---

  

**TLDR:**

Learn the magic trick to handle React state updates without the hassle of using a separate function for each state variable.

React is the state of the art of web development nowadays. More and more developers are switching their frontend framework to React and get hooked to it. The pros are many and if you’re more interested in them, I highly recommend reading [this article](http://some%20url%20here). Thus, it shouldn’t be surprising to you if you end up writing some React javascript through your frontend development journey.

You go with the flow and …

  

Sooner or later, you are gonna code your first event handler and most possible, it will look like the following example:

```
...

handleClick = (e) => {
  e.preventDefault();
  this.setState({clicked: e.target.value});
}

render() {

return(
    <button onClick={handleClick}>
      Click me now 🔥
    </button>
  );
}
```

[**Handling Events - React**  
_Handling events with React elements is very similar to handling events on DOM elements. There are some syntactic…_reactjs.org](https://reactjs.org/docs/handling-events.html "https://reactjs.org/docs/handling-events.html")[](https://reactjs.org/docs/handling-events.html)

  

  

use gif as preview image!!!!

  

Update state’s value and key

  

Material UI example

```
import React from 'react';
import Switch from '@material-ui/core/Switch';

class Switches extends React.Component {
  state = {
    checkedA: true,
    checkedB: true,
  };

  handleChange = name => event => {
    this.setState({ [name]: event.target.checked });
  };

  render() {
    return (
      <div>
        <Switch
          checked={this.state.checkedA}
          onChange={this.handleChange('checkedA')}
          value="checkedA"
        />
        <Switch
          checked={this.state.checkedB}
          onChange={this.handleChange('checkedB')}
          value="checkedB"
          color="primary"
        />
        <Switch value="checkedC" />
        <Switch disabled value="checkedD" />
        <Switch disabled checked value="checkedE" />
        <Switch defaultChecked value="checkedF" color="default" />
      </div>
    );
  }
}
```

From a previous article. Whom?

```
handleInputChange(event) { 
  const { target } = event; 
  const value = target.checked; 
  this.setState({ [target.name]: value, }); 
}
```
