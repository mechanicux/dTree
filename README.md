# dTree
*A library for visualizing data trees with multiple parents built on top of D3.*

[![Dependency Status](https://david-dm.org/ErikGartner/dtree.svg)](https://david-dm.org/ErikGartner/dtree) [![devDependency Status](https://david-dm.org/ErikGartner/dtree/dev-status.svg)](https://david-dm.org/ErikGartner/dtree#info=devDependencies) [![npm](https://img.shields.io/npm/v/d3-dtree.svg)](https://www.npmjs.com/package/d3-dtree)

If you want the latest build use the following CDN:
```
https://cdn.rawgit.com/ErikGartner/dTree/master/dist/dTree.min.js
```

For a specific version use:
```
https://cdn.rawgit.com/ErikGartner/dTree/0.2.4/dist/dTree.min.js
```

## Requirements
To use the library the follow dependencies must be loaded:

 - [D3](https://github.com/mbostock/d3) v3.
 - [lodash](https://github.com/lodash/lodash) v3.10

## Usage
Just include the compiled file ```dTree.js```, it exposes a ```dTree``` variable.

To create a graph from data use the following command:
```javascript
dTree.init(data, options);
```

The data object should have the following structure:
```javascript
[{
  name: "Father",
  class: "overriding-css-class",
  textClass: "overriding-css-class",
  marriage: {
    spouse: {
      name: "Mother",
      class: "overriding-css-class"
    },
    children: [{
      name: "Child",
      class: "child-class"
    }]
  },
  extra: {}
}]
```

The options object has the following default values:
```javascript
{
  target: '#graph',
  width: 600,
  height: 600,
  callbacks: {
    nodeClick: function(name, extra, id) {},
    text: function(name, extra, id) {return name;}
  },
  margin: {
    top: 0,
    right: 0,
    bottom: 0,
    left: 0
  },
  styles: {
    node: 'node',
    linage: 'linage',
    marriage: 'marriage',
    text: 'nodeText'
  }
}
```

The following CSS sets some good defaults:
```css
.linage {
    fill: none;
    stroke: black;
}
.marriage {
    fill: none;
    stroke: black;
}
.node {
    stroke: black;
    fill: lightblue;
}
.nodeText{
    font: 10px sans-serif;
}
```

## Development
To setup and build the library from scratch follow these steps:

1. ```npm install --save-dev```
2. ```npm run-script build```

A demo is available by running:
```
gulp demo
```
It hosts a demo on localhost:3000 by serving ```test/demo```.

## Contributions
To make contributions please follow the contributions document.

## License
The MIT License (MIT)

Copyright (c) 2015 Erik Gärtner
