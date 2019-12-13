# SmartBlock

SmartBlock.js is a JavaScript which enables you to write contents easily on websites even with <span style="font-weight:bold">SmartPhone</span>.

## Features

*   Easy to use with SmartPhone
*   Fully customizable
*   Block based
*   Keep clean HTML and wipe out unnecessary tags
*   Get the result as <span style="font-weight:bold">HTML</span> or <span style="font-weight:bold">JSON</span>
*   copy and paste contents

## Install

    $ npm install smart-block --save

## Usage

```js
import * as React from 'react';
import { render } from 'react-dom';
import { SmartBlock, GlobalStyle } from 'smart-block';

render(<>
  <GlobalStyle />
  <SmartBlock 
    html={'<h2>Hello World</h2><p>hello</p>'}
    onChange={({ json, html }) => { console.log(json, html);}}  
  />
</>, document.getElementById("app"));
```

## Extensions



## Customize

You can add custom block like this

```js
import { Extensions, CustomBlock, CustomMark } from 'smart-block';
Extensions.push(new CustomBlock({  tagName: 'div',  className: '.alert',  icon: <SomeIconComponent />});

render(<>
  <GlobalStyle />
  <SmartBlock 
    extensions={Extensions}
    html={'<h2>Hello World</h2><p>hello</p>'}
    onChange={({ json, html }) => { console.log(json, html);}}  
  />
</>, document.getElementById("app"));
```

You can also add custom inline element like this

```js
import { Extension, CustomBlock, CustomMark } from 'smart-block';
Extension.push(new CustomMark({  tagName: 'span',  className: '.small',  icon: <SomeIconComponent />});

render(<>
  <GlobalStyle />
  <SmartBlock 
    extensions={Extensions}
    html={'<h2>Hello World</h2><p>hello</p>'}
    onChange={({ json, html }) => { console.log(json, html);}}  
  />
</>, document.getElementById("app"));
```

## Options

| Props        | description                                                                                                 | type               | default                                                                                                                                                                                                                                                                                                                                                                 |
| ------------ | ----------------------------------------------------------------------------------------------------------- | ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| extensions   | Array of extensions which extend the feature of SmartBlock                                                  | Array\<Extension\> | \[   new Paragraph(),   new Heading2(),   new Heading3(),   new ListItem(),   new BulletList(),   new OrderedList(),   new Embed(),   new Code(),   new Table(),   new BlockQuote(),   new Strong(),   new Emphasis(),   new Underline(),   new Strike(),   new Link(),   new MoveDown(),   new MoveUp(),   new Trash(),   new DefaultKeys(),   new DefaultPlugins() \] |
| onChange     | Callback function which is called when the content of the editor is changed. You can get both html and json | Function           |                                                                                                                                                                                                                                                                                                                                                                         |
| onInit       | Callback function which is called when the editor is initialized                                            | Function           |                                                                                                                                                                                                                                                                                                                                                                         |
| json         | The editor contents will be initialized with the json data                                                  | Object             | {}                                                                                                                                                                                                                                                                                                                                                                      |
| HTML         | The editor contents will be initialized with the HTML                                                       | String             | ''                                                                                                                                                                                                                                                                                                                                                                      |
| showTitle    | Title will be shown                                                                                         | Boolean            | false                                                                                                                                                                                                                                                                                                                                                                   |
| showBackBtn  | Btn to support history back will be shown                                                                   | Boolean            | false                                                                                                                                                                                                                                                                                                                                                                   |
| autoSave     | The HTML will be stored to the localstorage every time the content is changed                               | Boolean            | false                                                                                                                                                                                                                                                                                                                                                                   |
| getEditorRef | Get the editor ref object                                                                                   | Function           |                                                                                                                                                                                                                                                                                                                                                                         |
