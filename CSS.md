# Cascading Style Sheets
- CSS describes how the HTML elements should appear
- The current version is CSS3, files have a .css extention

## Adding CSS to HTML files
- There are 3 ways of adding CSS to HTML files  
1. ***Inline CSS***         
       - used to apply a unique style to a single element
1. ***Internal CSS***        
       - used to apply a unique style to a HTML page        
       - defined in ```<style>``` tags in the ```<head>``` section
1. ***External CSS*** *(Best Practice)*        
       - having all your CSS styles in a separate file        
       - scala and maintainable        
       - ```<link rel="stylesheet" href="style.css">```

## A CSS Rule
- A CSS rule consists of a ***selector***, and a ***declaration block***
```css
h1 {
    color: blue;
}
```
- ```h1``` is the selector
- ```{}``` is the declaration block
- ```color``` is the property
- ```blue``` is the property value

## CSS Selectors
- are used to find (or select) an HTML element you want style
1. ***the CSS ID Selector***
   - uses the ***id*** attribute of an HTML element to select and style
   - the ***id*** selector is used on unique elements
   - to select an element, ```#element_id```
1. the CSS ***Class*** Selector        
   - the ***class*** selector selects HTML elements with a specific class attribute
   - to select an element, ```.class_name```

## CSS Comments
- ``` /* this is a CSS comment */ ```

## CSS ```box-sizing``` Property
- The CSS ```box-sizing``` property sets how the total width and height of an element is calculated
1. ***content-box*** *(default)*
    - if you set an element's width to 100px, the element's content box will be 100px wide
    - and the width of any border or padding will be added to the final rendered width making the element wider than 100px
1. ***border-box***
    - accounts for any border and padding in the values you specify for an element's width and height
    - so 100px will will include the content, border and padding

## CCS Starter
```css
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
```

## CSS Measurement Units
1. ***Absolute Lengths***
   - units are fixed and a length will appear exactly the same size on different devices, e.g. ```px```
1. ***Relative Lengths***
   - units specify a length relative to another, scales better across devices, e.g. ```rem, %```
1. ```vh and vw```
   - you can specify units relative to the viewport (screen)
   - 100vh takes up the whole page height, 100wv for width

## CSS Variables
- also known as custum properties, they look like regular CSS but with a -- before the property name
```css
* {
    --primary-color: blue;
}

h1 {
    color: var(--primary-color);
}
```

## Common Styles
- ```*{}``` styles that apply to all elements
- ```text-decoration: none``` is used mostly to remove underlines from links
- ```list-style: none``` removes bullets from the list 
- ```color``` specifies the color of the element
- ```background-color``` specifies the background color of an element
- ```display``` describes the display behaviour of an element *(```block, inline, flex, grid```)*
- ```line-height``` specifies the line of text content
- ```font-family``` specifies a font for text content
- ```font-style``` specifies the style of the text
- ```font-size``` specifies the size of the text
- ```font-weight``` specifies the thick(thin)ness of text
- ```opacity``` describes transparancy on a scale of 0 to 1
- ```height``` describes the height of an element
- ```width``` describes the width of an element
- ```border-radius``` allows us to make round corners of a border
- ```outline: none``` removes the outline around elements
- ```cursor: pointer``` changes the cursor to a pointer

## The CSS Box Model
- In CSS, the term ***Box Model*** is used when talking about design and layout
- All HTML elements can be viewed as boxes
- The CSS Box Model is essentially a BOX that wraps around every HTML element
- It consists of Margins, Borders, Padding, and the actual Content as shown [here](https://www.w3schools.com/css/css_boxmodel.asp)
1. ***Content***
    - this is the actual content, i.e. HTML elements
1. ***Padding***
    - used to generate space around an element's content, inside any defined borders
    - ```padding: top right bottom left```
1. ***Border***
    - allows us to specify the width, style (required), and color of an element's border
    - ```border: 5px solid red```
1. ***Margin***
    - used to generate space around elements, outside of any defined borders
    - ```border: top right bottom left```
- ***Centering an Element***
```css
.content {
    width: 300px;
    margin: 100px auto;
}
```

## CSS Shadow Effects
- adds a shadow to text or box elements
- the CSS ***text-shadow*** property applies shadow to text
- the CSS ***box-shadow*** property applies shadow to box elemnts         
```property: x_shadow_size y_shadow_size blur_effect_size shadow_color```

## CSS Hover
- custom style when you hover over an element
```css
.element_class:hover {
    /* custom styles here like a shadow*/
}
```
## Pseudo Classes
- ```a:link``` a normal, unvisited link
- ```a:visited``` a visited link
- ```a:active``` a link, the moment is clicked
- ```log_in_form:focus``` custum styles when the pointer focuses on this element

## Pseudo Element
- ```p::selection``` selects a portion of an element that is selected by a user

## The CSS Transition Property
- allows us to change property values smoothly, over a given durating
- ```transition: property duration (in seconds)```
```css
h1 {
    transition: font-size 3s;
}

h1:hover {
    font-size: 50px;
}
```

## The CSS Overflow Property
- specifies what should happen if content overflows an element's box
- can use ```overflow-x or overflow-y``` to set them individually
- ```overflow: visible | hidden | scroll | initial | inherit```

## The CSS z-index Property
- specifies the stack order of an element
- an element with a greater stack order is always on top of an element with lower stack order
- ```z-index``` only works on positioned elements, i.e not ```position: static``` which is default

## The CSS ```@media``` rule
- used to apply different styles to different devices
```css
h1 {
    color: blue
}

@media screen and (max-width:500px) {
    h1 {
        color: black;
    }
}
```
- ```max-width``` is the maximum width of the display area
   - desktop: 1200px
   - laptop: 1024px
   - tablet: 768px
   - phone: 480px

## CSS Layout: the ```position``` property
- specifies the type of positioning method used for an element (there are 5 methods)
- a ***positioned*** element is one where ```position``` is set to anything except ```static```
1. ```position: static``` *(default)*
    - elements positioned according to the normal flow of the document
1. ```position: relative```
    - an element is positioned relative to its normal position
    - using ```top, right, bottom, left``` an element can be moved relative to its original position
    - other content will not be adjusted to fit into the gap left by the element, hence this position is not commonly used to move elements
1. ```position: absolute```
    - positioned relative to the nearest positioned ancestor (does not disrupt normal flow)
    - if an ```absolute``` positioned element has no positioned ancestors, it uses the document body and move along with the page scrolling
    - Commonly used with ```top, right, bottom and left```
    ```css
    .parent {
        position: relative;
    }

    .parent .child {
        position: absolute;
        top: 50%;
        left: 50%;
    }
    ```
1. ```position: fixed```
    - positioned relative to the viewport, meaning it stays in the same place even when the page is scrolled
    - ```top, right, bottom, and left``` are used to position the element
    ```css
    .menu {
        position: fixed;
        top: 0;
    }
    ```
1. ```position: sticky```
    - positioned based on the user's scroll position
    - it is positioned relative until a given offset is met, then it sticks in place
    - ```top, right, bottom, and left``` are used to position the element
    ```css
    .menu {
        position: sticky; /* acts relative but when top hits 0, it sticks */
        top: 0;
    }

## CSS Flexbox Layout Module
- makes it easier to design flexible responsive layouts without using float or positioning
- To use ```flexbox``` you need to define a ***container***, with ***items***
```html
<div class="container">
    <div>A</div>
    <div>B</div>
    <div>C</div>
</div>
```
- ***Flexbox container properties***
```css
.container {
    display: flex; /* the container becomes flexible */
    flex-direction: column; /* defines in which direction the container should stack the flex items (other option is row, which is the default) */
    flex-wrap: wrap; /* specifies whether the flex items should wrap or nor (other option: nowrap) */
    justify-content: center; /* used to align flex items horizontally (other options: flex-start, flex-end, space-around, space-between) */
    align-items: center; /* used to aligh flex items vertically */
}
```
- ***Perfect Centering***
```css
.container {
    display: flex;
    justify-content: center;
    align-items: center;
}
```
