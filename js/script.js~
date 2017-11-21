/*
 * Copyright (C) 2017 Neeraj Mourya
 * Licensed under the GPL V3 or Later, License (https://www.gnu.org/licenses/gpl-3.0.en.html)
 */
$(document).ready(function(){
    $('.sticky-nav').each(function(){
        var stickyel = $(this);
        var width = $(this).width();
        var elementPosition = stickyel.offset();
        $(window).scroll(function(){
            if($(window).scrollTop() > elementPosition.top){
                stickyel.css({'width': width + 'px'});
                stickyel.removeClass('static').addClass('fixed');
            } else {
                stickyel.removeClass('fixed').addClass('static');
            }
        });
    });
    
    var scrollTimer = setTimeout(function(){ console.log("ScrollTimeout") }, 100);
    var scrollTimeout = 500;
    //scroll selection    
    $(window).scroll(function() {
        var wind = $(this);
        $('.id-block').each(function(){
            var idblock = $(this);
            var top_of_element = idblock.offset().top;
            var bottom_of_element = idblock.offset().top + idblock.outerHeight();
            var bottom_of_screen = $(window).scrollTop() + window.innerHeight;
            var top_of_screen = $(window).scrollTop();

            if((bottom_of_screen > (top_of_element + 350)) && (top_of_screen < bottom_of_element)){
                // The element is visible, do something
                clearTimeout(scrollTimer);
                scrollTimer = setTimeout(function(){
                    var blockid = idblock.attr("id");
                    $('.id-block.active').removeClass('active');
                    $('.side-nav li a.active').removeClass('active');
                    idblock.addClass('active');
                    $('a[href="#'+blockid+'"]').addClass('active');
                },scrollTimeout);
            }
            else {
                // The element is not visible, do something else
            }     
        });       
    });   
    
    // handle links with @href started with '#' only
    $(document).on('click', 'a[href^="#"]', function(e) {
        // target element id
        var id = $(this).attr('href');

        // target element
        var $id = $(id);
        if ($id.length === 0) {
            return;
        }

        // prevent standard hash navigation (avoid blinking in IE)
        e.preventDefault();

        // top position relative to the document
        var pos = $id.offset().top;

        // animated top scrolling
        $('body, html').animate({scrollTop: pos});
    }); 
});
