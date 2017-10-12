# react-sane-contenteditable
React component with sane defaults to make any element contentEditable

## Why?
ContentEditable has some known issues, the purpose of this component is to avoid some of its problems:

* Allow plaintext-only mode;
* Prevent cursor jumping to the beginning of the field.

## Example
```jsx
import React, { Component } from 'react';
import ContentEditable from 'react-sane-contenteditable';

class App extends Component {
  constructor (props) {
    super(props);

    this.state = {
      title: "Title here"
    }
  }

  handleChange = (ev, value) => {
    this.setState({ title: value });
  }

  render() {
    return (
      <div className="App">
        <ContentEditable
          className="my-class"
          tagName="h1"
          mode="plaintext"
          content={this.state.title}
          editable={true}
          maxLength={140}
          onChange={ this.handleChange }
        />
      </div>
    );
  }
}

```
