# Harry Lee Site Guide

There are four kinds of pages in this site: 

| Type of Page | Example File | CSS Link |
|:-- |:-- |:-- |
| Lists | [Talks Page](https://harrylee.github.io/talks.html) | [CSS](#list-css) |
| Card | [Now Page](https://harrylee.github.io/now.html) | [CSS](#card-css) |
| Blog | [Family Poem](https://harrylee.github.io/blog/family-poem.html) | [CSS](#blog-css) |
| Artwork | [Fairtale Zine](https://harrylee.github.io/work/fairytale-zine.html) | [CSS](#artwork-css) |

These pages all have slightly different CSS. When adding a page, copy the appropriate CSS type from the bottom of this README. If you are creating a new type of page, include the [Navigation CSS](#navigation-bar-css) to maintain consistent formatting in the navigation bar. 

## Snippets:

Here are some helpful snippets for maintaining the site:

**Conferences**
```html
<li><a href="[URL]"><span class="title">[TITLE]</span> <span class="conference">[CONFERENCE]</span> <span class="year">[YEAR]</span></a></li>
```


**Work**
```html
<li><a href="[URL]"><span class="title">[TITLE]</span> <span class="medium">[MEDIUM]</span> <span class="year">[YEAR]</span></a></li>

```

**Blog**
```html
<li><a href="[URL]"><span class="title">[TITLE]</span> <span class="month">[MONTH]</span> <span class="day">[DAY]</span> <span class="year">[YEAR]</span></a></li>

```


**Sitemap** (Note the indentation)
```xml
	<url>
		<loc>https://hellothisismywebsite.com/[PATH TO FILE]</loc>
		<lastmod>[2025-01-20]</lastmod>
	</url>
```

## CSS Snippets

### List CSS

```css
@font-face { 
font-family: "Inter"; 
font-style: normal; 
font-weight: 500; 
src: url("/Inter-Medium.woff2") format("woff2"); 
font-feature-settings: "ss07", "ss08", "cv10"; 
}
:root {
font-family: "Inter", "Arial", sans-serif;
font-feature-settings: 'liga' 1, 'calt' 1;
font-size: 10pt;
}

body{
background: #fff;
line-height: 1.2;
font-weight: 500;
margin: 1em;
background: #fff;
background-image: linear-gradient(rgba(0,0,0,.04) 1px, transparent 1px), linear-gradient(90deg, rgba(0,0,0,.04) 1px, transparent 1px);
background-size: 1em 6em;
background-position-y: -3em;
}
a{
color:black;
}
h1, h2, h3, h4, h5, h6{
font-size: inherit;
font-weight: inherit;
}
ul#works{
list-style-type: none;
padding:0;
max-width: 800px;
}
ul#works span{padding: 0 0.25em;}
ul#works li a,ul#works li.list-header{
text-decoration: none;
display: flex;
justify-content: space-between;
padding: 0.25em 0;
opacity: 0.5;
}
ul#works span.title{
flex-basis: 20%;
flex-grow: 1;
}
ul#works span.conference{
flex-basis: 30%;
flex-grow: 1;
}
ul#works span.month{
flex-basis: 15%;
}
ul#works span.medium{
flex-basis: 20%;
flex-grow: 1;
}
ul#works span.day{
flex-basis: 5%;
}
ul#works span.year{
flex-basis: 10%;
}
li.list-header{
border-bottom: 1px solid;
}
ul#works{
margin-bottom: 8em;
}
@media (hover: hover) {
	a:hover{opacity: 80%;}
	ul#works li a:hover{opacity: 1;}
}
nav{
position: fixed;
bottom: 3vh;
left:0;
right:0;
width: 100%;
display: flex;
justify-content: center;
}
nav > ul {
background: rgba(255, 255, 255, 0.5);
box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
-webkit-backdrop-filter: blur(10px);
backdrop-filter: blur(10px);
border-radius: 48px;
padding: 1em;
list-style: none;
display: flex;
justify-content: space-around;
}
nav li{padding: 0 0.5em;}
nav a{
color: black;
text-decoration: underline;
text-decoration-color: transparent;
transition-property: text-decoration-color, color;
}
nav a:hover{text-decoration-color: currentColor;}
.active-page{text-decoration: underline;}

@media (prefers-reduced-motion: no-preference) {
  nav a, a{transition: 0.3s;}
}
```

### Card CSS

```css
@font-face { 
font-family: "Inter"; 
font-style: normal; 
font-weight: 500; 
src: url("/Inter-Medium.woff2") format("woff2"); 
font-feature-settings: "ss07", "ss08", "cv10"; 
}
:root {
font-family: "Inter", "Arial", sans-serif;
font-feature-settings: 'liga' 1, 'calt' 1;
font-size: 10pt;
}

body{
background: #fff;
background-image: linear-gradient(rgba(0,0,0,.04) 1px, transparent 1px), linear-gradient(90deg, rgba(0,0,0,.04) 1px, transparent 1px);
background-size: 1em 6em;
background-position-y: -3em;
line-height: 1.2;
font-weight: 500;
margin: 0;
min-height: 100vh;
display: flex;
flex-direction: column;
justify-content: center;
align-items: center;
}
a{
color:black;
}
a:hover{
opacity: 80%;
}
h1, h2, h3, h4, h5, h6{
font-size: inherit;
font-weight: inherit;
}
.card{
background-color: white;
background-image: url("/grain.png");
background-size: 64px 64px;
background-repeat: repeat;
width: 90%;
max-width: 36em;
min-height: 22em;
border-radius: 1px;
box-sizing: border-box;
box-shadow: 
  -1px 2px 8px #00000050,
  0px 0px 30px 5px #ffffff30 inset;
padding: 1em;
margin: 1em;
transition: 0.5s;
transition-property: box-shadow;
}

.card > *:first-child{margin-top:0}
.card > *:last-child{margin-bottom:0}
.card:last-of-type{margin-bottom: 4vh;}

.corners{
height:20em;
/* height based on the hard-coded min-height in card */
display:flex;
flex-direction: column;
justify-content: space-between;
}
.corners p{
display: inline;
margin:0;
}
.corners > .top{
display:flex;
justify-content: space-between;
align-items: start;
flex-wrap: wrap;
}
.corners > .bottom{
flex-wrap: wrap;
display:flex;
justify-content: space-between;
align-items: end;
}
@media (max-width: 36em) {
  body{
    justify-content: start;
  }
  .card:first-of-type{
    margin-top: 10%;
  }
  .card:last-of-type{
    margin-bottom: 8em;
  }
}
@media (prefers-reduced-motion: no-preference) {
  .card:hover{
    box-shadow: 
      0px 8px 12px #00000050,
      0px 0px 30px 5px #ffffff30 inset;
  }
}
nav{
position: fixed;
bottom: 3vh;
left:0;
right:0;
width: 100%;
display: flex;
justify-content: center;
}
nav > ul {
background: rgba(255, 255, 255, 0.5);
box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
-webkit-backdrop-filter: blur(10px);
backdrop-filter: blur(10px);
border-radius: 48px;
padding: 1em;
list-style: none;
display: flex;
justify-content: space-around;
}
nav li{padding: 0 0.5em;}
nav a{
color: black;
text-decoration: underline;
text-decoration-color: transparent;
transition-property: text-decoration-color, color;
}
nav a:hover{text-decoration-color: currentColor;}
.active-page{text-decoration: underline;}

@media (prefers-reduced-motion: no-preference) {
  nav a, a{transition: 0.3s;}
}
```

### Blog CSS

```css
@font-face { 
font-family: "Inter"; 
font-style: normal; 
font-weight: 500; 
src: url("/Inter-Medium.woff2") format("woff2"); 
font-feature-settings: "ss07", "ss08", "cv10"; 
}
:root {
font-family: "Inter", "Arial", sans-serif;
font-feature-settings: 'liga' 1, 'calt' 1;
font-size: 10pt;
}

body{
background: #fff;
line-height: 1.4;
font-weight: 500;
margin: 1em;
background: #fff;
background-image: linear-gradient(rgba(0,0,0,.04) 1px, transparent 1px), linear-gradient(90deg, rgba(0,0,0,.04) 1px, transparent 1px);
background-size: 1em 6em;
}

article{
max-width: 40em;
font-size: 11pt;
margin: 1em auto;
}
a{
color:black;
}
a:hover{
opacity: 80%;
}
a.image{cursor: zoom-in;}


h1{
position:fixed;
top:1em;
margin:0;
font-size: 10pt;
font-weight: inherit;
line-height: 1.2;
}
h2{
border-bottom: rgba(0,0,0,.2) 1px solid;
}
hr{
border:none;
border-bottom: rgba(0,0,0,.2) 1px solid;
}
p{
font-size: 1;
}

h2.title{
margin-bottom:0
}
p.time{
margin-top:0;
}

article > p:last-of-type{
margin-bottom: 15vh;
}


@media (max-width: 48em){
  h1{
    position:static;
  }
}
nav{
position: fixed;
bottom: 3vh;
left:0;
right:0;
width: 100%;
display: flex;
justify-content: center;
}
nav > ul {
background: rgba(255, 255, 255, 0.5);
box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
-webkit-backdrop-filter: blur(10px);
backdrop-filter: blur(10px);
border-radius: 48px;
padding: 1em;
list-style: none;
display: flex;
justify-content: space-around;
}
nav li{padding: 0 0.5em;}
nav a{
color: black;
text-decoration: underline;
text-decoration-color: transparent;
transition-property: text-decoration-color, color;
}
nav a:hover{text-decoration-color: currentColor;}
.active-page{text-decoration: underline;}

@media (prefers-reduced-motion: no-preference) {
  nav a, a{transition: 0.3s;}
}
```

### Artwork CSS

```css
@font-face { 
font-family: "Inter"; 
font-style: normal; 
font-weight: 500; 
src: url("/Inter-Medium.woff2") format("woff2"); 
font-feature-settings: "ss07", "ss08", "cv10"; 
}
:root {
font-family: "Inter", "Arial", sans-serif;
font-feature-settings: 'liga' 1, 'calt' 1;
font-size: 10pt;
}

body{
background: #fff;
background-image: linear-gradient(rgba(0,0,0,.04) 1px, transparent 1px), linear-gradient(90deg, rgba(0,0,0,.04) 1px, transparent 1px);
background-size: 1em 6em;
background-position-y: -3em;
line-height: 1.2;
font-weight: 500;
margin:0;
}

a{color:black;}
a:hover{opacity: 80%;}
a.image{cursor: zoom-in;}

h1{
font-size: inherit;
font-weight: inherit;
}

section{
width:100vw;
height:100vh;
display:flex;
flex-direction: row-reverse;
isolation: isolate;
}
section .photo, section .card-container{
display:flex;
justify-content: center;
align-items: center;
flex-direction: column;
}
section .photo{
flex-direction: row;
justify-content: start;
overflow-x: scroll;
scroll-snap-type: x mandatory;
gap: 1em;
margin: 0 2em;
}
section .card-container{
flex-shrink: 0;
}

section .photo > img, section .photo > iframe{
border: solid 1px;
scroll-snap-align: center;
max-width: 90%;
max-height: 80vh;
width:inherit;
}
.card{
background-color: white;
background-image: url("/grain.png");
background-size: 64px 64px;
background-repeat: repeat;
width: 90%;
max-width: 36em;
min-height: 22em;
max-height: 30vh;
overflow: scroll;
border-radius: 1px;
box-sizing: border-box;
box-shadow: 
  -1px 2px 8px #00000050,
  0px 0px 30px 5px #ffffff30 inset;
padding: 1em;
margin: 1em;
transition: 0.5s;
transition-property: box-shadow;
}

.card > *:first-child{margin-top:0}
.card > *:last-child{margin-bottom:0}

.card ul{
padding-inline-start:1.4em;
}
.attribution{
display: block;
text-align:right
}

@media (orientation: portrait){
  section{
    flex-direction: column;
    min-height: unset;
  }
  section .photo > img{
    max-height: 90%;
    margin: auto
  }
}
nav{
position: fixed;
bottom: 3vh;
left:0;
right:0;
width: 100%;
display: flex;
justify-content: center;
}
nav > ul {
background: rgba(255, 255, 255, 0.5);
box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
-webkit-backdrop-filter: blur(10px);
backdrop-filter: blur(10px);
border-radius: 48px;
padding: 1em;
list-style: none;
display: flex;
justify-content: space-around;
}
nav li{padding: 0 0.5em;}
nav a{
color: black;
text-decoration: underline;
text-decoration-color: transparent;
transition-property: text-decoration-color, color;
}
nav a:hover{text-decoration-color: currentColor;}
.active-page{text-decoration: underline;}

@media (prefers-reduced-motion: no-preference) {
  nav a, a{transition: 0.3s;}
}
```

### Navigation Bar CSS

```css
nav{
position: fixed;
bottom: 3vh;
left:0;
right:0;
width: 100%;
display: flex;
justify-content: center;
}
nav > ul {
background: rgba(255, 255, 255, 0.5);
box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
-webkit-backdrop-filter: blur(10px);
backdrop-filter: blur(10px);
border-radius: 48px;
padding: 1em;
list-style: none;
display: flex;
justify-content: space-around;
}
nav li{padding: 0 0.5em;}
nav a{
color: black;
text-decoration: underline;
text-decoration-color: transparent;
transition-property: text-decoration-color, color;
}
nav a:hover{text-decoration-color: currentColor;}
.active-page{text-decoration: underline;}

@media (prefers-reduced-motion: no-preference) {
  nav a, a{transition: 0.3s;}
}
```

