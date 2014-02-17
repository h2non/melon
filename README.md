# oml

> **SPOILER! Work in progress**

## About

**oml** (Oli Markup Language) is a template engine build on top of the [Oli][oli] language for node and the browser
It's powered by the Oli [JavaScript][oli-js] parser and compiler

## Features

- Pretty and minimalist syntax
- Built-in support for data references
- Support mixins and includes (upcoming)
- Runs over node and browers
- No third party dependencies

## Installation

#### Node.js

```
$ npm install omljs
```
For CLI usage only, it's recommented you install it as global package
```
$ npm install -g omljs
```

#### Browser (via Bower)

```
$ bower install oml --save
```

Or load the script remotely (just for testing or development)
```html
<script src="//rawgithub.com/h2non/oml/master/oml.js"></script>
```
Then you can create script tags with `text/oli` MIME type
```html
<script type="text/oli" src="path/to/template.oli"></script>
```
It will automatically fetch and parse the oli sources and make it available from `oli.scripts`.
To disable the automatic parsing, just add `data-ignore` attribute in the script tag

## Environments

- Node.js >= 0.8.0
- Chrome
- Firefox
- Safari 5
- Opera >= 11.6
- IE >= 9

## Upcoming features

- Mixins
- Includes

## Syntax Reference

### Doctype

The document can be defined define the following doctypes:

```html
xml <?xml version="1.0" encoding="utf-8" ?>
transitional <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
strict <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
frameset <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">
1.1 <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
basic <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML Basic 1.1//EN" "http://www.w3.org/TR/xhtml-basic/xhtml-basic11.dtd">
mobile <!DOCTYPE html PUBLIC "-//WAPFORUM//DTD XHTML Mobile 1.2//EN" "http://www.openmobilealliance.org/tech/DTD/xhtml-mobile12.dtd">
```

Example
```ruby
doctype html
```

### Tags

```ruby
ul:
  li: Apple
  li: Banana
  li: Coco
end
```
Self-closing tags
```ruby
!img
```

#### Literal shortcuts

##### Class
```jade
a.button 
```
```html
<a class="button"></a>
```
```jade
.content 
```
```html
<div class="content"></div>
```

##### ID
```jade
a#button 
```
```html
<a id="button"></a>
```
```jade
#content
```
```html
<div id="content"></div>
```

### Attributes

```ruby
a(href:'google.com'): Google
a(class: 'button', href: 'me.com'):> My Web Site
```


[oli-js]: https://github.com/oli-lang/oli-js
[oli]: https://oli-lang.org
