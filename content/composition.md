# Composition

```javascript

// Simple Example, only generate the tag
var tag = t => contents => `<${t}>${contents}</${t}>`
tag('b')('this is bold!')

var print_tag = function(tagname){
  return function(content){
    return `<${tagname}>${content}</${tagname}>`
  }
}

print_tag('strong')('this is strong');

// Example generating the tags with attributes

// Cleaning the attribute
var encodeAttribute = (attr = '') => attr.replace(/""/g, '&quot;');

// Transform the object to string
var toAttributeString = (x = {}) =>
    Object.keys(x)
    .map(attr => `${encodeAttribute(attr)}="${encodeAttribute(x[attr])}"`)
    .join(' ');

// Create the string of the tag with the attributes
var tagAttributes = x => (c = '') =>
`<${x.tag}${x.attr?' ':''}${toAttributeString(x.attr)}>${c}</${x.tag}>`

// constructor, it will accept if the parameter is string or object
var tag = x => typeof x === 'string' ? tagAttributes({ tag: x }) : tagAttributes(x);

// Simplified version
var bold = tag('b');
bold('this is bold');

// Currying
tag('b')('this is bold');

// Tag with attributes
tag({ tag: 'div', attr: { 'class': 'title'}})('this is a title');


const listGroup = tag({ tag: 'ul', attr: { class: 'list-group' }});
const listGroupItem = tag({ tag: 'li', attr: { class: 'list-group-item' }});
const listGroupItems = items =>  items.map(listGroupItem).join('');

listGroup()
// <ul class="list-group"></ul>

listGroupItem('Cras justo')
// <li class="list-group-item">Cras justo</li>

listGroupItems(['Cras justo', 'Dapibus ac'])
// <li class='list-group-item'>Cras justo</li>
// <li class='list-group-item'>Dapibus ac</li>

listGroup(listGroupItems(['Cras justo', 'Dapibus ac']))
// <ul class='list-group'>
//   <li class='list-group-item'>Cras justo</li>
//   <li class='list-group-item'>Dapibus ac</li>
// </ul>


```
