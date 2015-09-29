# SpidocheTube 3
A simple jQuery youtube gallery plugin

Project website : http://tube.spidoche.com

## DEMO

*   [Minimal theme](http://tube.spidoche.com/demo/minimal/minimal.html)
*   [Darkscroll theme](http://tube.spidoche.com/demo/darkscroll/darkscroll.html)

## INSTALL

### HTML

Add a div with an id of your choice inside the `<body></body>` (we'll use id="youtube" in our example)

    <div id="youtube"></div>

### JAVASCRIPT

1.  If not already inculde, add jQuery inside the head tag
2.  Then add spidochetube.js 
3.  Finally initialize the plugin with at least the 2 required parameter : the youtube api **KEY** and the playlist **ID**

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.9.0/jquery.min.js"></script>
    <script src="js/jquery.spidochetube.js"></script>
    <script>
    jQuery(function($){
        $('#youtube').spidochetube({
            key         : '[MY YOUTUBE API KEY]',
            id          : 'UU_x5XG1OV2P6uZZ5FSM9Ttw',
        });
    })
    </script>

### THEMES

This step is NOT required, you can easily add your own CSS to match your website design

To use the spidocheTube premade skins, follow the instructions below

#### Minimal theme install

##### Add the CSS

    <link rel="stylesheet" href="css/minimal.css" />

Beginner tips: do not forget to change the path of the css file to match your project directory tree

##### Update the js options settings

    <script>
    jQuery(function($){
        $('#youtube').spidochetube({
            key         : '[MY YOUTUBE API KEY]',
            id          : 'UU_x5XG1OV2P6uZZ5FSM9Ttw',
        });
    })
    </script>

#### Darkscroll theme install

##### Add the CSS

    <link rel="stylesheet" href="css/darkscroll.css" />

Beginner tips: do not forget to change the path of the css file to match you project directory tree

##### Add niceScroll library

For this theme you need to include an additional jQuery plugin call niceScroll from [inuyaksa](http://nicescroll.areaaperta.com/)

1.  Download niceScroll from https://github.com/inuyaksa/jquery.nicescroll and add it to your js folder
2.  Then Add inside the head tag `<script src="js/jquery.nicescroll.min.js"></script>`

These script is little heavy but is very simple too install, and it's work on any browser (ie7 include)

##### Update the js options settings

    <script>
    jQuery(function($){
        $('#youtube').spidochetube({
            key         : '[MY YOUTUBE API KEY]',
            id          : 'UU_x5XG1OV2P6uZZ5FSM9Ttw',
            max_results : 8,
            complete: function(){
                // Initialize the scroll plugin after the playlist is ready
                $('#spidochetube_list').niceScroll({cursorcolor:'#666', cursorborder:'0px solid #fff',autohidemode:false});
            }
        });
    });
    </script>

## OPTIONS

<table class="api">

<tbody>

<tr>

<th class="option">Name</th>
<th class="type">Type</th>
<th class="parameter">Default value</th>
<th class="example">Options available</th>
<th class="description">Description</th>

</tr>

<tr>

<td>key</td>
<td>string</td>
<td>'none'</td>
<td></td>
<td>Add your youtube API key , get one on the <a href="https://console.developers.google.com">google dev console</a></td>

</tr>

<tr class="playlist_id">

<td>id</td>
<td>string</td>
<td>'UU_x5XG1OV2P6
uZZ5FSM9Ttw'</td>
<td></td>
<td>
Your playlist id, it's can be a user playist id or a user last entries playlist
if no argument submit spidochetube will display the last google devlopper channel entries
<a href="https://www.youtube.com/watch?v=oRGEOtcZc0o">How to find a playlist id?</a>
</td>
</tr>

<tr>
<td>max_results</td>
<td>integer</td>
<td>10</td>
<td>1 to 50</td>
<td>50 results per page/load maximum (youtube api limitation)</td>
</tr>

<tr>
<td>autoplay</td>
<td>boolean</td>
<td>false</td>
<td>true</td>
<td>Set to true if you want to autoplay the videos</td>
</tr>

<tr>
<td>complete</td>
<td>function</td>
<td></td>
<td></td>
<td>Callback function fire after list is loaded</td>
</tr>

</tbody>

</table>
