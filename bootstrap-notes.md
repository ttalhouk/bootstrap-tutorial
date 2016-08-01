# Bootstrap Notes  
*Codeschool Tutorial*  


## Adding Bootstrap to HTML

Add link tag into head.   
```HTML
<!-- bootstrap CSS -->
<link href="css/bootstrap.min.css" media="all" rel="stylesheet" />
<!-- main CSS -->
<link href="css/main.css" media="all" rel="stylesheet" />
```
Also add Jquery and Bootstrap script tags at the bottom of the body.
```HTML
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
<script src="js/bootstrap.min.js?body=1"></script>
```

**Centering Content**  
To add border around the main html and center the container, we will use the `class="container"`.  Add this attribute to a `<div class='container'>` around the content.

**Stretch Content Across Window**  
To allow containers to stretch across the entire window use `class="container-fluid"`.  Add this attribute to a `<div class='container-fluid'>` around the content you want to have stretch.

## Grids

Bootstrap divides the page into 12 columns.  These can set the width of each row of data by using `class="col-md-*"` where * is the number of columns we want the content to take up.  "md" stands for medium sized screen which has to do with media queries for responsiveness and can be changed to other options.

So if we want 2 containers in the same row, each container would be given `class="col-md-6"` making each take 1/2 the screen.

These should be wrapped in a `<div class="row"` to seperate them.

```html
<div class='container'>

  <div class="row">
    <div class='col-md-12'>...</div>
  </div>

  <div class="row">    
    <div class='col-md-6'>
      <h2>The Fastest Way to Space</h2>  <p>Make your way to space...</p> ...
    </div>
    <div class='col-md-6'>
      <img src='images/blast.png' alt='Blasting Off' />
    </div>
  </div>

</div>
```

You can apply offsets to space out content.

```html
<div class='row'>
  <div class='col-md-8'></div>
  <div class='col-md-3 col-md-offset-1'></div>
  <!-- adds one col of offset before content -->
</div>
```
**Responsive Griding**
```html
 <div class='row'>
  <div class='col-sm-4 col-xs-10 col-xs-offset-1 col-sm-offset-0'>
    <h3>Book Today!</h3> </div>
    <!-- Takes up 10 col offset by 1 on xs screen but only 4 in any larger than s and removes the offset -->
  <div class='col-sm-4 col-xs-6'>  
    <h3>Go Anywhere</h3>
    <!-- Takes up 6 col on xs screen but only 4 in any larger than s -->
  </div>
  <div class='col-sm-4 col-xs-6'>
    <h3>RocketBus&reg;</h3>
    <!-- Takes up 6 col on xs screen but only 4 in any larger than s -->
  </div>
</div>
```

**Hiding Elements based on Screen Size**

```html
<div class='row'>
  <div class='col-md-6'>...</div>
    <div class='col-md-6 hidden-sm hidden-xs'>
      <img src='images/blast.png' alt='Blasting Off' />
      <!-- image hidden on xs and sm screen size -->
  </div>
</div>
```
Alternately you can use `class="visible-(size)"` to only show when at the size given.

## Typography

**`.lead` Class**

Using the lead class increases size and spacing.

**Centering Text**

```html
<div class='row text-center'>  
  <div class='...'>
    <h3>Book Today!</h3>
    <p>Even if you're traveling tomorrow...</p>  
  </div>
...
</div>
```
using `text-center` centers all text elements inside the row.

other options are  
* `text-justify`
* `text-right`
* `text-left`
* `text-nowrap`

**Using Built in Glyphicons**

```html
<div class='...'>
  <i class='glyphicon glyphicon-briefcase'></i>
  <!-- Adds briefcase glyphicon to page -->
  <h3>Book Today!</h3>
  <p>Even if you're traveling...</p>
</div>
```
These are fonts and can be styled like fonts.

**Removing Bullets**

Adding class `list-unstyled` removes bullets and margins from ul's.

Adding `list-inline` makes lists show up horizontally.

## Buttons & Wells

`class="well"` gives an inset to the container (entire row if applyed to that div) to help it stand out.  Give a border and slight grey background.  More padding can be added with `class="well well-lg"` making it larger.

**Button Styling**

Class `btn` allows bootstrap to style the buttons.  To make them bigger add `btn-lg` as well.  `btn-default` applys standard styling to a button.  For custom style apply `btn-primary` will make it stand out. Other styles available...

* `btn-danger` -red
* `btn-info` -light-blue
* `btn-warning` -yellow
* `btn-success` -green

## Navigation

Making a nav bar, start with the content.

```html
<div class='container'>
  <h1>Blasting Off With Bootstrap</h1>
  <ul>
    <li><a href='tickets.html'>Tickets</a></li>  <li><a href='stations.html'>Stations</a></li>  <li><a href='about.html'>About</a></li>
  </ul>
</div>
```
Change the title header to a <a> tag and give it the brand class.

`<a href='index.html' class='navbar-brand'>Blasting Off With Bootstrap</a>`

Apply nav class to <ul>

Then nav modifiers can be added
* `nav-pills` -makes links horz and adds padding around
* `nav-tab` -makes a tab type navigation bar
* `navbar-nav` -horz but no extra padding and borders
* `navbar-right` -pushes list elements to the right side

Apply `navbar` to the container and to apply color scheme add `navbar-default` alternately you can use `navbar-inverse` for dark color schemes.

Pull container class out of navbar div.

To add the navbar to the top apply `navbar-static-top`  Alternately you can use fixed positions to keep navbar on top as screen is scrolled.  if using fixed top need to add padding of 70px to push content below the nav bar.


## Javascript Components

**Collapsible NavBar**

Adding the class `collapse` and `navbar-collapse` to the nav bar `<ul>` then add button before the nav bar that can show when in xs mode.  

```html
 <div class='navbar navbar-default navbar-static-top'>  
  <div class='container'>
    <a href='index.html' class='navbar-brand'>...</a>
    <button type='button'>Toggle navigation</button>
    <ul class='nav navbar-nav navbar-right
      collapse navbar-collapse'>...</ul>
  </div>  
</div>
```

Wrapping the button in a `sr-only` class means the text is for screen readers only making it accessable but not display the text.

```html
<button type='button'>
  <span class='sr-only'>Toggle navigation </span>
</button>
```

Styling the button
```html
<!-- Data toggle collapse switches the collapse state -->
<button type='button' class='navbar-toggle collapsed' data-toggle='collapse' data-target='.navbar-collapse'>
  <span class='sr-only'>Toggle navigation</span>
  <!-- 3 horiz lines in button -->
  <span class='icon-bar'></span>
  <span class='icon-bar'></span>
  <span class='icon-bar'></span>
</button>
```
To seperate the rows between brand and links.

```html
<div class='navbar-header'>
  <a href='index.html' class='navbar-brand'>Blasting Off With Bootstrap</a>

  <button type='button' class='navbar-toggle collapsed' data-toggle='collapse' data-target='.navbar-collapse'>
    <span class='sr-only'>Toggle navigation</span>
    <span class='icon-bar'></span>
    <span class='icon-bar'></span>
    <span class='icon-bar'></span>
  </button>
</div>
```

`data-toggle="<attribute>" / data-target="<class/id>"` used to target which action and item to switch

`data-parent="<class/id>"` Targets a parent element with the class or id called

## Grouping navigation

Adding a carrot and sub link list

```html
<a href='/about' data-target='#' class='dropdown-toggle' data-toggle='dropdown'>About <span class='caret'></span></a>
<!-- data-toggle="dropdown" adds open class to the ul below
data-target="#" prevents the link if JS is enabled and will open and close the about links as intended but older browsers can use the /about link class="dropdown-toggle" is specifically used to style this as a dropdown-->
<ul class='dropdown-menu' role='menu'>
  <!-- dropdown hides li's -->
  <li><a href='#'>Our Story</a></li>
  <li><a href='#'>Contact Us</a></li>
  <li class='divider'></li>
  <li><a href='#'>Blog</a></li>
  <li class='divider'></li>
  <li><a href='#'>Twitter</a></li>
  <li><a href='#'>Facebook</a></li>
</ul>
```
