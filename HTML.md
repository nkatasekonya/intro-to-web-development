# HyperText Markup Language

## What is HTML5
- HTML describes the structure of a webpage
- The current version, HTML5 introduced semantic elements
- HTML files have a .html extention
- HTML elements are represented by tags

## Basic HTML Document
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello World</title>
    <link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
</head>
<body>
    
</body>
</html>
```

## HTML Comments
```html 
<!-- this is a HTML comment -->
```

## HTML Paragraph
```html
<p>This is a paragraph</p>
```

## HTML Headings
```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

## Block Level Elements
- These elements occupy a whole block on the page
- With the following element going to the next line
- Examples include the Heading and Paragraph elements

## Inline Elements
- These elements take out the width required to display the element
- Meaning, the next element will not be on the next line
- Examples include the span, img and links

## Lists
- Enables us to display elements in a list, either ordered or unordered
  ### Unordered List
  ```html
  <ul>
      <li>item 1</li>
      <li>item 2</li>
  </ul>
  ```
  ### Ordered List
  ```html
  <ol>
      <li>item 1</li>
      <li>item 2</li>
  </ol>
  ```
  ### Nested Lists
  ```html
  <ul>
      <li>item 1</li>
      <ul>
           <li>item 1</li>
           <li>item 2</li>
      </ul>
  </ul>
  ```

## Links
```html
<a href="https://example.com" target="_blank">Click Me</a>
```

## Images
```html
<img src="./html5.jpeg" alt="HTML Logo" width="150" height="100"/>
```

## Images and Links
```html
<a href="#">
    <img src="./html5.jpeg" alt="HTML5 Logo" width="150" height="100" />
</a>
```

## Forms
```html
<form action="#" method="post">
    <label for="username">Username</label>
    <input type="text" id="username" name="username" placeholder="nkatasekonya">
    <input type="submit" value="Add Username">
</form>
```
- the ***```name```*** attribute is required to reference the form data after it has been submitted; on the backend
- the ***```id```*** is used to associate the element with the label
- the ***```placeholder```*** acts as a hint to the expected input
- ```required```, ```min``` and ```max``` can be used for validation of input elements
- different HTML Form ***input types***
  -  ```type="text"``` 
  -  ```type="password"``` 
  -  ```type="submit"```
  -  ```type="radio"```
  -  ```type="checkbox"```
  -  ```type="button"```
  -  ```type="date"```
  -  ```type="email"```
  -  ```type="file"```
  -  ```type="search"```
  -  ```type="url"```
  -  ```type="number" required min="0" max="5"```

## Input Type Radio vs. Checkbox
- ***Radio*** buttons lets a user select only ***ONE*** of a limited number of choices
- the value given to ***name*** is the same, cause ultimately we are sending one choice
```html
<h1>Gender</h1>
<form action="#" method="post">
    <label for="male">Male</label>
    <input type="radio" id="male" name=gender>
    <label for="female">Female</label>
    <input type="radio" id="female" name=gender>
    <input type="submit" value="Add Gender">
</form>
```
- with ***Checkboxes*** we allow the user more options
- this is achieved by having different values for ***name***
- on the backend we individually check for values (var1...var_n) 

## Input Type Select
```html
<form action="#" method="post">
    <select name="module" id="module">
        <option value="module1">Module 1</option>
        <option value="module2">Module 2</option>
    </select>
    <input type="submit" value="submit module">
</form>
```

## The TextArea Element
- The ```<textarea>``` element defines a multi-line input field
```html
<textarea name="review" id="review" cols="30" rows="10">
</textarea>
```

## HTML5 Tables
- enables the arangement of data into rows and columns
```html
<table>
    <tr>
        <th>Name</th>
        <th>Surname</th>
    </tr>
    <tr>
        <td>Nkata</td>
        <td>Sekonya</td>
    </tr>
    <tr>
        <td>Zak</td>
        <td>Lebete</td>
    </tr>
</table>
```

## The Details Element
```html
<details open>
    <summary>Final marks</summary>
    <p>The final marks will be released on Friday</p>
</details>
```

## HTML5 Symbols
- ```&copy``` is the copyright sign
- ```&reg``` is the registered sign
- ```&trade``` is the trademark sign
- ```&hearts``` is a black heart sign

## HTML5 Semantic Elements
- A Semantic element clearly describes its meaning to both the browser and the developer
- ```<header>``` defines a container for introductory content
- ```<nav>``` defines a set of navigation links
- ```<section>``` defines a section in a document
- ```<article>``` specifies independent, self-contained content
- ```<aside>``` defines some content aside the main one, ussually in a sidebar
- ```<footer>``` defines a footer for a document or section
- find more info [here](https://www.w3schools.com/html/html5_semantic_elements.asp)

## HTML Video
- The ```<video>``` element is used to show a video on a webpage
```html
<video src="./welcome.mp4">Welcome Video</video>
```

## HTML Audio
- The ```<audio>``` element is used to show an audio on a webpage
```html
<audio src="./welcome.mp3" controls>Welcome Audio</audio>
```

## *iframe:* Embedding Youtube Videos
- generate this from Youtube *(copy embed code)*
```html
<iframe width="853" height="480" src="https://www.youtube.com/embed/yv5vOHUCHCM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

## Others
- ```<div>``` used to group elements
- ```<br>``` breaks to the next line
- ```<hr>``` draws a horizontal line 
- ```<b>``` bold text
- ```<strong>``` important text
- ```<i>``` italic text
- ```<em>``` emphasized text
- ```<mark>``` marked text
- ```<small>``` smaller text
- ```<del>``` deleted text
- ```<ins>``` inserted text
- ```<sub>``` subscript text
- ```<sup>``` superscript text


