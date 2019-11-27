# JavaScript equivalent to jQuery basics

## Intro
jQuery is a great cross-platform JavaScript library for DOM selection, manipulation and other cool things, but usually you load 84kb and use less than 3%. So maybe you want try another cool alternative, use native JavaScript with their methods... Also you can load jQuery using CDN... But again, maybe you want to try native JavaScript...

## Index
* [Selectors](#selectors)
* [Attributes](#attributes)
* [Styles](#styles)
* [Effects](#effects)
* [Events](#events)
* [Others](#others)

## Selectors

### $() 
(IE 8+)
```javascript
var $ = function(el) {
    return document.querySelectorAll(el);
};
```
### $('#foo')
```javascript
document.getElementById('foo')
```
### $('.foo')
IE 8+
```javascript
document.querySelectorAll('.foo')
```
IE 9+
```javascript
document.getElementsByClassName('foo')
```
### $('span')
```javascript
document.getElementsByTagName('span')
```
### $('#foo span')
```javascript
document.getElementById('foo').getElementsByTagName('span')
```
### $('html')
```javascript
document.documentElement
```
### $('head')
```javascript
document.head
```
### $('body')
```javascript
document.body
```
### $('#foo').parent()
```javascript
document.getElementById('foo').parentNode
```
### $('#foo).children()
```javascript
document.getElementById('foo').children
```
### $('#foo').next()
IE 9+
```javascript
document.getElementById('foo').nextElementSibling
```

## Attributes

### $('#foo').html()
```javascript
document.getElementById('foo').innerHTML
```
### $('#foo').html('Hello world!')
```javascript
document.getElementById('foo').innerHTML = 'Hello world!'
```
### $('#foo').val()
```javascript
document.getElementById('foo').value
```
### $('#foo').addClass('bar')
```javascript
document.getElementById('foo').className += ' bar'
```
IE 10+
```javascript
document.getElementById('foo').classList.add('bar')
```
### $('#foo').removeClass('bar')
IE 10+
```javascript
document.getElementById('foo').classList.remove('bar')
```

```javascript
function removeClass(elem, className) {
    var newClass = ' ' + elem.className.replace( /[\t\r\n]/g, ' ') + ' ';
    if (hasClass(elem, className)) {
        while (newClass.indexOf(' ' + className + ' ') >= 0 ) {
            newClass = newClass.replace(' ' + className + ' ', ' ');
        }
        elem.className = newClass.replace(/^\s+|\s+$/g, '');
    }
}

removeClass(document.getElementById('foo'), 'bar')
```

### $('#foo').hasClass('bar')
IE 10+
```javascript
document.getElementById('foo').classList.contains('bar')
```

```javascript
function hasClass(elem, className) {
    return new RegExp(' ' + className + ' ').test(' ' + elem.className + ' ');
}

hasClass(document.getElementById('foo'), 'bar')
```

### $('#foo').toggleClass('bar')
IE 10 +
```javascript
document.getElementById('foo').classList.toggle('bar')
```

```javascript
function toggleClass(elem, className) {
    var newClass = ' ' + elem.className.replace( /[\t\r\n]/g, ' ' ) + ' ';
    if (hasClass(elem, className)) {
        while (newClass.indexOf(' ' + className + ' ') >= 0 ) {
            newClass = newClass.replace( ' ' + className + ' ' , ' ' );
        }
        elem.className = newClass.replace(/^\s+|\s+$/g, '');
    } else {
        elem.className += ' ' + className;
    }
}

toggleClass(document.getElementById('foo'), 'bar')
```

## Styles

### $('#foo').hide()
```javascript
document.getElementById('foo').style.display = 'none'
```
### $('#foo').css('background-color', red')
```javascript
document.getElementById('foo').style['background-color'] = 'red'
    
document.getElementById('foo').style.backgroundColor = 'red'
```

## Effects

### $('#foo').fadeOut(750)
```javascript
function fadeOut(ms, el) {
    var opacity = 1,
        interval = 50,
        gap = interval / ms;

    function func() { 
        opacity -= gap;
        el.style.opacity = opacity;

        if(opacity <= 0) {
            window.clearInterval(fading); 
            el.style.display = 'none';
        }
    }

    var fading = window.setInterval(func, interval);

}

fadeOut(750, document.getElementById('foo'))
```

### $('#foo').fadeIn(750)
```javascript
function fadeIn(ms, el) {
    var opacity = 0,
        interval = 50,
        gap = interval / ms;

    el.style.display = 'block';
    el.style.opacity = opacity;
    
    function func() { 
        opacity += gap;
        el.style.opacity = opacity;
        if(opacity >= 1) {
            window.clearInterval(fading);
        }
    }
    
    var fading = window.setInterval(func, interval);
}

fadeIn(750, document.getElementById('foo'))
```

## Events

### $(document).ready
IE 9+
```javascript
document.addEventListener('DOMContentLoaded', function() { ... })
```
### $('#foo').on('click', function() { ... })
```javascript
document.getElementById('foo').onclick = function() { ... }
```
IE 9 +
```javascript
document.getElementById('foo').addEventListener('click', function() { ... })
```

## Others

### $('#foo').after('&lt;div id="a"&gt;b&lt;/div&gt;')
```javascript
document.getElementById('foo').insertAdjacentHTML('beforeend', '<div id="a">b</div>')
    
document.getElementById('foo').innerHTML += '<div id="a">b</div>'
```
### $('#foo').prepend('&lt;div id="a"&gt;b&lt;/div&gt;')
```javascript
document.getElementById('foo').insertAdjacentHTML('afterbegin', '<div id="a">b</div>')
```
### $('#foo').before('&lt;div id="a"&gt;b&lt;/div&gt;')
```javascript
document.getElementById('foo').insertAdjacentHTML('beforebegin', '<div id="a">b</div>')
```
### $('#foo').after('&lt;div id="a"&gt;b&lt;/div&gt;')
```javascript
document.getElementById('foo').insertAdjacentHTML('afterend', '<div id="a">b</div>')
```
### $('#foo').remove()
```javascript
document.getElementById('foo').parentNode.removeChild(document.getElementById('foo'))
```

## Authors
Taking from:
- [JavaScript equivalent to jQuery basics](http://codepen.io/danielcure/full/omDwv/)

Inspired by:
- [Doing without jQuery](http://evanhahn.com/doing-without-jquery/)
- [From jQuery to JavaScript: A Reference](http://code.tutsplus.com/tutorials/from-jquery-to-javascript-a-reference--net-23703)

## More resources
A great article was published here: [Cheat sheet for moving from jQuery to vanilla JavaScript](https://tobiasahlin.com/blog/move-from-jquery-to-vanilla-javascript/)
