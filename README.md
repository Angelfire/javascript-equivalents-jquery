#JavaScript equivalent to jQuery basics

##Intro
jQuery is a great cross-platform JavaScript library for DOM selection, manipulation and other cool things, but usually you load 94kb and use less than 3%. So maybe you want try another cool alternative, use native JavaScript with their methods... Also you can load jQuery using CDN... But again, maybe you want to try native JavaScript...

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


    
##Authors
I take
