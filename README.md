#JavaScript equivalent to jQuery basics

##Intro
jQuery is a great cross-platform JavaScript library for DOM selection, manipulation and other cool things, but usually you load 94kb and use less than 3%. So maybe you want try another cool alternative, use native JavaScript with their methods... Also you can load jQuery using CDN... But again, maybe you want to try native JavaScript...

##Index
* [Selectors](#selectors)
* [Attributes](#attributes)
* [Styles](#styles)
* [Events](#events)
* [Others](#others)

##Selectors

###$() (IE 8+)
    var $ = function(el) {
       return document.querySelectorAll(el);
    };
###$('#foo')
    document.getElementById('foo')
###$('.foo')
IE 8+

    document.querySelectorAll('.foo')
IE 9+

    document.getElementsByClassName('foo')
###$('span')    
    document.getElementsByTagName('span')
###$('#foo span')
    document.getElementById('foo').getElementsByTagName('span')
###$('html')
    document.documentElement
###$('head')
    document.head
###$('body')
    document.body
###$('#foo').parent()
    document.getElementById('foo').parentNode
###$('#foo).children()
    document.getElementById('foo').children
###$('#foo').next()
IE 9+

    document.getElementById('foo').nextElementSibling

##Attributes

###$('#foo').html()
    document.getElementById('foo').innerHTML
###$('#foo').html('Hello world!')
    document.getElementById('foo').innerHTML = 'Hello world!'
###$('#foo').val()
    document.getElementById('foo').value
###$('#foo').addClass('bar')
    document.getElementById('foo').className += ' bar'
IE 10+

    document.getElementById('foo').classList.add('bar')
###$('#foo').removeClass('bar')
IE 10+

     document.getElementById('foo').classList.remove('bar')
###$('#foo').hasClass('bar')
IE 10+

    document.getElementById('foo').classList.contains('bar')
###$('#foo').toggleClass('bar')
IE 10 +

    document.getElementById('foo').classList.toggle('bar')

##Styles

###$('#foo').hide()
    document.getElementById('foo').style.display = 'none'
###$('#foo').css('background-color', red')
    document.getElementById('foo').style['background-color'] = 'red'
    
    document.getElementById('foo').style.backgroundColor = 'red'

##Events

###$(document).ready
IE 9+

    document.addEventListener('DOMContentLoaded', function() { ... })
###$('#foo').on('click', function() { ... })
    document.getElementById('foo').onclick = function() { ... }

IE 9 +

    document.getElementById('foo').addEventListener('click', function() { ... })

##Others

###$('#foo').append('<div id="a">b</div>')
    document.getElementById('foo').insertAdjacentHTML('beforeend', '<div id="a">b</div>')
    
    document.getElementById('foo').innerHTML += '<div id="a">b</div>'
###$('#foo').prepend('<div id="a">b</div>')
    document.getElementById('foo').insertAdjacentHTML('afterbegin', '<div id="a">b</div>')
###$('#foo').before('<div id="a">b</div>')
    document.getElementById('foo').insertAdjacentHTML('beforebegin', '<div id="a">b</div>')
###$('#foo').after('<div id="a">b</div>')
    document.getElementById('foo').insertAdjacentHTML('afterend', '<div id="a">b</div>')
###$('#foo').remove()
    document.getElementById('foo').parentNode.removeChild(document.getElementById('foo'))

##Authors
I take
