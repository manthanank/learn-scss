# Learn SCSS

This repository contains the code for learning SCSS. SCSS is a preprocessor scripting language that is interpreted or compiled into CSS. SCSS is a superset of CSS, which means that it contains all of the features of CSS and is built on top of CSS. SCSS files are processed by the server before being served to the client as a CSS file.

![npm](https://img.shields.io/npm/dw/learn-scss)
![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/manthanank/learn-scss)
![GitHub repo size](https://img.shields.io/github/repo-size/manthanank/learn-scss)
![GitHub](https://img.shields.io/github/license/manthanank/learn-scss)
![GitHub last commit](https://img.shields.io/github/last-commit/manthanank/learn-scss)

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Variables](#variables)
- [Nesting](#nesting)
- [Partials & Imports](#partials--imports)
- [Mixins](#mixins)
- [Extends](#extends)
- [Operators](#operators)
- [Functions](#functions)
- [Inbuild Functions](#inbuild-functions)
- [Number Functions](#number-functions)
- [String Functions](#string-functions)
- [Colors Functions](#colors-functions)
- [Lists](#lists)
- [Selectors](#selectors)
- [Map](#map)
- [Introspection](#introspection)
- [Conditional Directives](#conditional-directives)
- [Loops](#loops)

## Installation

```bash
npm install scss
```

## Usage

```bash
sass input.scss output.css
```

## Features

- Variables
- Nesting
- Partials & Imports
- Mixins
- Extends
- Operators
- Functions
- Inbuild Functions
- Number Functions
- String Functions
- Colors Functions
- Lists
- Selectors
- Map
- Introspection
- Conditional Directives
- Loops

## Variables

```scss
$variable-name : value;
```

## Nesting

```scss
nav{
    ul{
        li{
            a{
                &:hover
                {
                
                }
            }
        }
    }
}
```

## Partials & Imports

Create file with _filename.scss

```scss
@import "filename";

```

## Mixins

```scss
@mixin align($value){
    text-align = $value;
}

.classname1{
    @include align(center);
}
.classname2{
    @include align(left);
}
```

## Extends

```scss
.clasname{
    height: 10px;
    width: 10px;
    text-align: center;
}
.classname1{
    height: 12px;
    @extend .classname;
}
```

```scss
%clasname{
    height: 10px;
    width: 10px;
    text-align: center;
}
.classname1{
    height: 12px;
    @extend %classname;
}
```

## Operators

```scss
.clasname{
    height: 10px;
    width: 10px;
    text-align: center;
}
.classname1{
    height: 12px;
    @extend .classname;
}
```

```scss
%clasname{
    height: 10px;
    width: 10px;
    text-align: center;
}
.classname1{
    height: 12px;
    @extend %classname;
}
```

## Functions

```scss
@function function-name($value){
    @return($value/2)+px;
}

.half-column{
    width: function-name(1000);
}
```

```scss
@container-width: 1000;

@function half($width){
    @return $width/2 + px;
}

.half-width{
    width: half($container-width);
}
```

## Inbuild Functions

1. Numbers
2. Strings
3. Colors
4. Lists
5. Selectors
6. Introspection

## Number Functions

- abs()
- ceil()
- floor()
- round()
- round()
- max()
- min()
- comparable()
- percentage()
- random()
- unit()
- unitless()

```scss
.test{
    margin: abs(10);
    margin: ceil(10);
    margin: floor(10);
    margin: round(10);
    margin: max(10px, 20px, 30px);
    margin: min(10px, 20px, 30px);
    margin: comparable(1rem, 2px);
    margin: percentage(0.5);
    margin: random();
    margin: unit(10);
    margin: unitless(10);
}
```

## String Functions

- quote()
- str-index()
- str-insert()
- str-length()
- str-slice()
- to-upper-case()
- to-lower-case()
- unique-id()
- unquote()

```scss
.test{
    font-family: quote(Arial);
    font-family: unquote("Arial");
    font-family: to-upper-case(Arial);
    font-family: to-lower-case(Arial);
    font-family: str-length("Helvetica");
    font-family: str-index("Helvetica Neue","Neue");
    font-family: str-insert("Helvetia Neue","Mono",2);
    font-family: str-slice("Mono",1);
    font-family: unique-id();
}
```

## Colors Functions

- lighten()
- darken()
- adjust-hue()
- saturate()
- desaturate()
- mix()
- transparentize()

```scss
$base-color: pink;
.test{
    background-color: darken($base-color, 30);
    background-color: lighten($base-color, 30);
    background: adjust-hue($base-color, 30);
    background: saturate($base-color, 30);
    background: desaturate($base-color, 30);
    background: mix($base-color, yellow, 30);
    background: transparentize($base-color, 0.2);
    background: red($base-color);
    background: green($base-color);
    background: blue($base-color);
    background: hue($base-color);
    background: saturation($base-color);
    background: lightness($base-color);
    background: alpha($base-color);
}
```

## Lists

- length()
- nth()
- set-nth()
- join()
- append()
- zip()
- index()
- list-separator()
- is-bracketed()

```scss
$list : 10px 20px 30px;
$list1 : 10px 20px 30px;
$list2 : 10px 20px 30px;

.test{
    padding: length($list);
    padding: nth($list,1);
    padding: set-nth((Helventica, Arial, Verdana),1, Roboto);
    padding: join($list1, $list2);
    padding: append($list, 70px);
    padding: zip($list1, $list2);
    padding: index($list, 20);
    padding: list-separator($list);
    padding: is-bracketed($list);   
}
```

## Selectors

- selector-nest
- selector-append
- selector-replace
- is-superselector
- simple-selectors
- selector-unify
- selector-extend

```scss
$selector : selector-nest("ul","li");
$selector : selector-append("a",".active");
$selector : selector-replace("a.ab",".ab");
$selector : is-superselector("a","a.active");
$selector : simple-selector("a.ab");
$selector : selector-unify("a",".active");
$selector : selector-extend("a.active","a",".link");

#{$selector}{
    width: 10px;
}
```

## Map

- map-get()
- map-merge()
- map-remove()
- map-keys()
- map-values()
- map-has-keys()

```scss
$font-weights : ("regular" : 400, "medium": 500, "bold": 700);
$light-weights : ("lightest" : 400, "light": 500);

$merge : map-merge($font-weights, $light-weights);
$remove: map-remove($font-weights, "regular")

.test{
    font-weight: map-get($font-weights, "bold");
    font-weight: map-keys($font-weights);
    font-weight: map-values($font-weights);
    font-weight: map-values($font-weights);
    font-weight: map-values($remove);
    font-weight: map-has-keys($font-weights, "bold");
}
```

### Introspection

- variable-exists()
- global-variable-exists()
- mixin-exists()
- function-exists()
- type-of()
- inspect()

```scss
$char : "Arial"
$list : 10px 20px 30px;
$map : ("regular" : 400, "medium" : 500);

@mixin border-radius{
    border-radius: 5px;
}

@function add($a, $b){
    @return $a + $b;
}
.test{
    $num: 10px;
    padding: variable-exists(list);
    padding: global-variable-exists(list);
    padding: mixin-exists(border-radius);
    padding: function-exists(add);
    padding: type-of($char);
    padding: inspect($add);
}
```

## Conditional Directives

@contect

```scss
@mixin test{
    @content;
}

@include test{
    .block{
    color: green;
    }
}
```

@media

```scss
.container{
    width: 1100px;
    margin: 0px auto;

    @media screen and (max-width: 1150px){
    width: 900px;   
    }
    @media screen and (max-width: 950px){
    width: 700px;   
    }
}
```

@at-root

```scss
.item{
    color: red;

    @at-root{
    .item-wrapper{
    color: green;
    }
    img{
    width: 100%;
    }
    }
}
```

## Loops

@if and @else and @else if

```scss
$test : 2;

p{
    @if $test <= 5 {
    color: blue;
    }@else if $test > 5 and $test < 10{
    color: green;
    }@else {
    color: red;
    }
    font-size: 10px;
}
```

@for

```scss
@for $1 from 1 through 3{
    .list{
    width: 100px;
    }
}
```

@each

```scss
@each $iin (normal, bold, italic){
    .test{
    font-weight: bold;
    }
}
```

@while

```scss
$i : 10;
@while $i <= 50{
    .padding{
    padding-left: 10x;
    }
}
```

## Connect with me

- [Twitter](https://twitter.com/manthan_ank)
- [LinkedIn](https://www.linkedin.com/in/manthanank)
- [Facebook](https://www.facebook.com/manthanank/)
- [Instagram](https://www.instagram.com/manthan_ank/)
- [YouTube](https://www.youtube.com/@manthanank)
- [GitHub](https://github.com/manthanank)

## Support

If you like this learning repository and find it useful, consider buying me a coffee or sponsoring me through the GitHub Sponsor. Your support will help me to continue and bring more exciting projects. Thank you!

[![Buy Me A Coffee](/assets/bmc-button.svg)](https://www.buymeacoffee.com/manthanank)

[![Sponsor Me](https://img.shields.io/badge/Sponsor-GitHub-green)]([https://](https://github.com/sponsors/manthanank))

---

Show your support by 🌟 the repository.

---
