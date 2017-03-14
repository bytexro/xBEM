# B.E.M FRAMEWORK

[![Bytex](http://i.imgur.com/HZ1NEBA.png)](http://bytex.ro/)

### by Prisecaru Bogdan


## Why should we use this?
---
- Easy and intuitive mixins for writing [B.E.M](https://en.bem.info/methodology/) classes
- Optimized output CSS
- No need for more then 1(one) class per element (except +state classes)
- No nesting beyond level 1(one) (except +state classes)


## Installation
---

In your terminal:
```
npm install --save xbem
```
In your webpack project, use 'sass-loader' with the following option:

webpack.config.js
```
{
  loader: 'sass-loader',
  options: {
    includePaths: [
      path.resolve('node_modules/xbem/src/')
    ]
  }
}
```
example.scss (your sass file anywhere in the project)
```
@import 'xbem';
```


## Usage
---
### Blocks

code
```
@include block(menu) { // styles here
  color: red;
}
```
output
```
.menu {
  color: red;
}
```

### Elements

code
```
@include block(menu) { // styles here
  color: red;

  @include element(item) {
    background-color: blue;
  }
}
```
output
```
.menu {
  color: red;
}

.menu__item {
  background-color: blue;
}
```

### Modifiers

code
```
@include block(menu) { // styles here
  color: red;

  @include element(item) {
    background-color: blue;

    @include modifier(big) {
      font-size: 200%;
    }
  }
}
```
output
```
.menu {
  color: red;
}

.menu__item {
  background-color: blue;
}

.menu__item, .menu__item--big {
  background-color: blue;
}

.menu__item--big {
  font-size: 200%;
}
```

### States

code
```
@include block(menu) { // styles here
  color: red;

  @include state(isHidden) {
    display: none;
  }
}
```
output
```
.menu {
  color: red;
}

.menu.\\+isHidden {
  display: none;
}
```

### Mixins
> Not part of the B.E.M methodology
> Just some usefull mixins to use in your SASS projects


| Mixin | Codepen Link |
| ------ | ------ |
| flexgroupof | http://codepen.io/bogdan_bytex/pen/BWKWXa |
