# FLUID MENU

FLUID MENU allows how to have either a responsive horizontal menu or vertical menu. Improvement will come later.

FLUID MENU IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND...

Feel free to propose some modification or improvement suggestion.

# Demo

[Check here](https://fluid-menu.eco-sensors.ch)

## How to start
(jQuery is required)

### Horizontal menu

```
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Menu with Felxbox</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <link rel="stylesheet" type="text/css" href="css/font-awesome-4.7.0/css/font-awesome.min.css">
    <link rel="stylesheet" type="text/css" href="css/f-menu.css">
</head>
<body>
    <header>
        <h1>Demo Flex menu</h1>
    </header>
    <section class="container">
        <div id="f-menu-horizontal">
            <nav class="menu" aria-label="Main navigation">
                <!-- Here come the menu -->
            </nav>
            <nav class="hamburger">
                 <ul>
                    <li>
                        <div>
                            <a href="#" class="dropdown-toggle" aria-expanded="false">
                                <i class="fa fa-navicon"></i>
                            </a>
                        </div>
                    </li>
                </ul>
            </nav>
        </div> <!-- end id="f-menu" -->
    </section> <!-- end class="container" -->
    <footer>
    </footer>
<script src="js/jquery-3.6.0.min.js"></script>
<script src="js/f-menu.js"></script>
</body>
</html>
```

### Vertical menu

```
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    
    <title>Menu with Felxbox</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <link rel="stylesheet" type="text/css" href="css/font-awesome-4.7.0/css/font-awesome.min.css">
    <link rel="stylesheet" type="text/css" href="css/f-menu.css">
</head>
<body>
    <header>
        <h1>Demo Flex menu</h1>
    </header>
    <div class="container container-vertical"> 
        <aside>
            <div id="f-menu-vertical">
                <nav class="vhamburger">
                    <ul>
                        <li>
                            <div>
                                <a href="#" class="dropdown-toggle" aria-expanded="false">
                                    <i class="fa fa-navicon"></i>
                                </a>
                            </div>
                        </li>
                    </ul>
                </nav>
                <nav class="menu hide" aria-label="Main navigation"> <!-- the hide class is mantadory -->
                    <!-- Here come the menu -->
                </nav>
            </div> <!-- end of <div id="f-menu-vertical"> -->
        </aside>
        <main id="content">
        </main>
    </div> <!-- <div class="container container-vertical"> -->
    <footer>
    </footer>
<script src="js/jquery-3.6.0.min.js"></script>
<script src="js/f-menu.js"></script>
</body>
</html>
```

CSS
```
.container-vertical{
    display: flex;
    flex-direction: row;
}


.container-vertical main{
    flex: 1 1 auto;
}
```
Read more the [CSS file](https://github.com/ecosensors/fluid-menu/blob/main/css/f-menu.css) and the media queries section.


### Notes

* All li must have the class .level-1, .level-2 etc. according to their level
* A li with sub-menu(s), must have the class .hasChildren, and then the children ul must have the class .sub-menu with the role="group"
* The container of the links must be in a div (see the example, bellow)
* Be aware of the mandatory HTML tag

## Example


```

<div id="f-menu-horizontal">
    <nav class="menu" aria-label="Main navigation">
        <ul>
            <li>
                <div>
                    <a href="#">Level 1 - with no children</a>
                </div>
            </li>
            <li class="hasChildren level-1">
                <div>
                    <a href="#">Level 2 - with chilren</a>
                    <a href="#" class="dropdown-toggle" aria-expanded="false">
                        <i class="fa fa-angle-down"></i>
                    </a>
                </div>
                <ul class="sub-menu" role="group">
                    <li class="level-2">
                        <div>
                            <a href="#">Nous</a>
                        </div>
                    </li>
                    <li class="hasChildren level-2">
                        <div>
                            <a href="#">Histoire</a>
                            <a href="#" class="dropdown-toggle" aria-expanded="false">
                                <i class="fa fa-angle-down"></i>
                            </a>
                        </div>                        
                        <ul class="sub-menu" role="group">
                            <li class="level-3">
                                <div>
                                    <a href="#">Création</a>
                                </div>
                            </li>
                            <li class="hasChildren level-3">
                                <div>
                                    <a href="#">Nos investisseurs</a>
                                    <a href="#" class="dropdown-toggle" aria-expanded="false">            
                                        <i class="fa fa-angle-down"></i>
                                    </a>
                                </div>
                                <ul class="sub-menu">
                                    <li class="level-4">
                                        <div>
                                            <a href="#">Entreprise SA</a>
                                        </div>
                                    </li>
                                    <li class="level-4">
                                        <div>
                                            <a href="#">Association</a>
                                        </div>
                                    </li class="level-4">
                                    <li>
                                        <div>
                                            <a href="#">Fundation</a>
                                        </div>
                                    </li>
                                </ul>
                            </li>
                        </ul>
                    </li>
                </ul>
            </li>
        </ul>
    </nav>
</div>
```

## Classes

The CSS classes bellow, will help you the change the background colors of the menu

```
/*
Colors of the menu
*/

/* Background */
#f-menu-horizontal .menu,
#f-menu-horizontal .hamburger,
#f-menu-vertical .menu{
    background-color: #111111;
}


/* 2nd level background */
#f-menu-horizontal nav.hamburger.toggled-on,
#f-menu-horizontal nav ul li.hasChildren.active,
#f-menu-horizontal nav .hamburger-item, nav.menu .hamburger-item ul,
#f-menu-horizontal li.level-2,
#f-menu-vertical li.level-2,
#f-menu-vertical nav ul li.level-1.active > div a:nth-of-type(2){
    background-color: #333333;
}

/* 3nd level background */
#f-menu-horizontal li.level-3,
#f-menu-vertical li.level-3,
#f-menu-vertical nav ul li.level-2.active > div a:nth-of-type(2){
    background-color: #555555;
}

/* 4nd level background */
#f-menu-horizontal li.level-4,
#f-menu-vertical li.level-4,
#f-menu-vertical nav ul li.level-3.active > div a:nth-of-type(2){
    background-color: #777777;
}


/* Link color */

#f-menu-horizontal a,
#f-menu-vertical  a{
    color: #ffffff;
    text-decoration: none;
}

/* Hover */
#f-menu-horizontal nav ul li:hover,
#f-menu-vertical nav ul li a:nth-of-type(2):hover,
#f-menu-vertical nav ul li a:nth-of-type(1):hover{
    background-color: #222222;
}
```