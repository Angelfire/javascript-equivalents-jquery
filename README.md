#JavaScript equivalent to jQuery basics

##Intro
jQuery is a great cross-platform JavaScript library for DOM selection, manipulation and other cool things, but usually you load 94kb and use less than 3%. So maybe you want try another cool alternative, use native Javascript with their methods... Also you can load jQuery using CDN... But again, maybe you want to try native Javascript...

##Selectors
###$() (IE8+)
    var $ = function(el) {
       return document.querySelectorAll(el);
    };
###$('#foo')
    document.getElementById('foo')
##Authors
I take

    
