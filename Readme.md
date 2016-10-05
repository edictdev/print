#Print Theme
###A simple theme with print button and print style sheet.

This theme is designed as example of how to add the ability to print a fairly clean page from a Mahara user page or 
collection. It adds a print button on the display view of a page, printing from the browser also works.

#####Tested against Mahara 16.04.3.

Disclaimer: This is something fro people to play with rather than a full solution. I'm not a css expert, so there may be better ways to do this. 
My aim was to change as few files as possible, which is why I've used the Bootstrap "hidden-print" only once as I would have had to change a number of template files.
I only used it in that case as nothing else seemed to work.

 Kevin Rickis, EdICT Training LTD. 04/10/2016
 
 (rdx565 on mahara.org)

## Theme structure
* print
    * style
        * print.css(#print.css)
    * templates
        * header
            * head.tpl(#head.tpl)
        * view
            * view.tpl(#view.tpl)
    * collectionnav.tpl(#collectionnav.tpl)
    * Readme.md
    * themeconfig.php
    
 ##print.css   
 
 This file contains the css to print a fairly clean page from Mahara. 
 See the comments in the file.
 
 ##head.tpl
 
 Line 38 added to include print.css.
 
    <link media="print"  rel="stylesheet" type="text/css" href="{theme_url filename='style/print.css'}?v={$CACHEVERSION}"/>
    
 ##view.tpl
 
 Added the following code at line 30 to provide a print button.
 
                 <a title="{str tag=print section=view}" id="print_link" class="btn btn-default" href=""
                    onclick="window.print(); return false;">
                     <span class="icon icon-print icon-lg left" role="presentation" aria-hidden="true"></span>
                     {str tag=print section=view}
                 </a>
 ##collectionnav.tpl
 
 Added the Bootstrap class "hidden-print" to hide the Collection navigation.
 
     <div id="collectionnavwrap" class="collection-nav hidden-print">
     