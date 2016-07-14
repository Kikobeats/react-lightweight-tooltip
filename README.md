# A lightweight but powerful React.js tooltip component

## Work in progress - do not use it!
### TODO
- [ ] Test mobile events
- [ ] Test / fix mobile styles
- [ ] Fix styles: tooltip width based on content not wrapper
- [ ] Write specialized component examples
- [ ] Improve demo list of transactions (10, 100, 500, 1000, 2000, 3000, 5000 trns)
- [ ] Improve docs: custom content and styling and style/dom explatnation
- [ ] Npm + travis + bithound
- [ ] Consider adding hidearrow prop

## Demo
[Check it out](https://mcumpl.github.io/react-lightweight-tooltip/)

## Motivation
I recently needed a lightweight React.js tooltip component that:

* Is small (~100 lines) and ideally has no external dependencies
* Won't break with the next version of React
* Uses inline-styles (for easy composing of specialized components)
* Correctly uses React Event System
* Is applicable on a long lists (eg. financial transactions)
* Its content can be composed of elements (links, images etc.)
* Works well on mobile devices by default (is responsive)

And I couldn't find any, so I decided to write one.

## Basic Usage

```js
import React from 'react';
import {Tooltip} from 'react-lightweight-tooltip';

export default class Demo extends React.Component {
  render() {
    return <Tooltip content="Yes, the default one">Simple tooltip</Tooltip>;
  }
}
```

## Props
The props...

### children
```js

```

### content
```js

```

### styles
```js

```

## Custom content and styling 
Thanks to the inline-styling, the customization is extremely easy...
```js
import React from 'react';
import {Tooltip} from 'react-lightweight-tooltip';

const wrapperStyle = {
  wrapper: {
    background: '#ececec',
    color: '#555',
    margin: '30px 10px 10px 10px',
    padding: '15px 20px',
    textAlign: 'center',
    width: '195px',
    display: 'inline-block',
  },
};

const greenStyle = {
  wrapper: wrapperStyle.wrapper,
  content: {
    backgroundColor: 'green',
    color: '#000',

  },
  tooltip: {
    backgroundColor: 'green',
  },
  arrow: {
    borderTop: 'solid green 5px',
  },
};

const greyStyle = {
  wrapper: wrapperStyle.wrapper,
  content: {
    backgroundColor: 'grey',
    color: '#000',

  },
  tooltip: {
    backgroundColor: 'grey',
  },
  arrow: {
    borderTop: 'solid grey 5px',
  },
};

export default class Demo extends React.Component {
  render() {
    return (
      <div>
        <Tooltip content="Yes, the default one" styles={wrapperStyle}>Simple tooltip</Tooltip>

        <Tooltip
          content={
            [
              'This repo is hosted on ',
              <a href="https://github.com" target="_blank">Github</a>,
            ]
          }
          styles={greenStyle}>
          Tooltip with a link
        </Tooltip>

        <Tooltip
          content={
            [
              <img src="https://avatars0.githubusercontent.com/u/9491005" style={{ width: '100px', borderRadius: '50%' }} />,
              <div style={{ textAlign: 'center', padding: '10px 20px' }}>
                Hi there, I am <a href="https://github.com/mcumpl" target="_blank">Michal</a> and I love corrida de toros! <em>Not...</em>
              </div>,
            ]
          }
          styles={greyStyle}>
          Tooltip with a rich content
        </Tooltip>
      </div>
    );
  }
}
```

## Installation
```js
npm install react-lightweight-tooltip
```


## Run the demo
```js
npm start
```

## Acknowledgements

This project uses the [react-component-boilerplate](https://github.com/survivejs/react-component-boilerplate).

## License

*react-lightweight-tooltip* is available under MIT license. See LICENSE for more details.
