---
title: Week 3
date: 2016-10-26 20:37:01
tags:
---
#### Intro to CSS
1. Create a new folder called "week3" and open it up in Atom by selecting File > Add project folder. Then create a new file in that folder by right-clicking it and selecting "New file." Name the file "index.html" and select it.
    - Copy the HTML from week 1 and paste it into the new file.
2. Create another new file in the same folder called "styles.css," and leave it blank for now.
    - Now link the CSS file to the HTML file by adding the line `<link rel="stylesheet" href="styles.css">`
    just before the closing `<head>` tag.
3. We are going to be switching between both files quite often which is common for development. Keep both files open in Atom, and create a `<header>` element inside the body, and fill it in with the navigation structure we see in most websites.

```html
<header>
  <nav>
    <img src="http://placekitten.com/60/60" alt="logo" />
    <ul>
      <li><a href="#about">About</a></li>
      <li><a href="http://google.com">Google</a></li>
    </ul>
  </nav>
</header>
```

- We are introducing [semantic tags](https://en.wikipedia.org/wiki/Semantic_HTML) which help with user accessibility and developer readability, so we know exactly what each tag in the structure means.
- Here we have created a navigation with a logo image (pulled from Placekitten.com) and an unordered list with a couple links - one that links internally on the same page and another that links externally to Google.

#### Cross-browser compatibility

1. Now lets go back to the CSS file. First we will do a couple boilerplate styles to our page that will help it stay consistent across different browsers.

```css
* {
    vertical-align: top;
}

body {
    margin: 0;
}
```

- These styles ensure that all elements start their content at the top of the element which isn't always default in every browser, and that there is no default margin around the body causing unwanted whitespace bordering the page.
- This is a minimal version of what is known as a [CSS reset](http://cssreset.com/what-is-a-css-reset/).

#### Anatomy of a CSS rule

1. Each style block in CSS is called a [rule](http://www.w3schools.com/css/css_syntax.asp). A rule starts with a [selector](http://www.w3schools.com/cssref/css_selectors.asp) followed by a [declaration](http://reference.sitepoint.com/css/declarations) which is denoted by the curly braces `{}`. Inside the declaration are [properties](http://www.htmldog.com/references/css/properties/) with values.

2. Lets style the header we created in the HTML. In your CSS file under the `body` declaration:

```css
header {
  height: 80px;
  background-color: #3498db;
  padding: 10px;
}
header img{
  border-radius: 50%;
}
header nav, header ul, header li {
  display: inline-block;
}
header li a{
  padding-left: 20px;
}
```

- When we have more than one selector listed next to each other, we are using CSS's specificity to drill into exactly the element that is nested inside the previous selector and style that.
- When we have commas between selectors, we are telling CSS to apply the style to each individual selector separated by the commas.
- Add each property one by one, and save and reload your page to see the styles being applied so you get the feel of what each one does.
- A good place to find colors for CSS is at [flatuicolors.com](https://flatuicolors.com). CSS defines most colors in [hexadecimal](https://en.wikipedia.org/wiki/Hexadecimal), and this is a nice place to see a color and copy the code for it. Choose any color and paste it in the `background-color` property of the `header` rule.

#### Building and styling the rest of our page

1. Add a banner section to our page with a fun little style gimmick called [parallax](https://en.wikipedia.org/wiki/Parallax).

- Add the following HTML underneath the closing `</header>` tag:

```html
<section class="banner">
  <h1>Mike's Cool Website!</h1>
</section>
```

- And the CSS underneath the header styles from above:

```css
section.banner {
  padding-top: 150px;
  height: 300px;
  background: url("http://placekitten.com/500/500") fixed;
  background-size: cover;
}
h1{
  color: white;
  font-size: 72px;
  text-align: center;
}
```
- Since our section has a class of "banner" we can use that as a selector with the "dot notation" (like `section.banner`) in our CSS.
- The background url is just a Placekitten image which we fix to the background of the section allowing for other content to scroll over it creating our parallax effect.

2. In order to see the effect, we need to add more content. Lets add the About section to our page underneath the previous banner section we created:

```html
<section id="about">
  <p>Occupy meggings subway tile poutine, bitters slow-carb trust fund XOXO master cleanse venmo. Occupy fap etsy, pour-over brooklyn snackwave blue bottle VHS. Helvetica marfa brooklyn, pok pok deep v hammock +1 actually mlkshk lomo swag activated charcoal cliche ethical selfies. Yr taxidermy austin pop-up salvia, sustainable asymmetrical kickstarter wayfarers plaid succulents craft beer jean shorts. PBR&B affogato air plant, art party umami kickstarter heirloom literally letterpress biodiesel blue bottle next level. Truffaut retro man bun, fap unicorn jianbing blog franzen tacos keytar tumeric pug meditation beard cliche. Fap keffiyeh mlkshk drinking vinegar, chillwave hella prism put a bird on it neutra readymade tbh forage deep v microdosing cold-pressed.
  </p>
</section>
```

- I got that placeholder text from [hipster ipsum](https://hipsum.co), a silly take on [Lorem ipsum](https://en.wikipedia.org/wiki/Lorem_ipsum) which has been used as placeholder text for design purposes since time immemorial.
- Notice the id of "about" in this section - this will correspond to our anchor tag (hyperlink) from the header section where we use the id notation (like `#about`), and the click of that link will bring you to this section.
- Lets style that section. Since we only have one `p` tag in our page, we don't have to specify what it's HTML parent is for illustration purposes, although it is good practice to do so.

```css
p {
  margin: 5%;
  text-align: center;
}
```

3. Lets build out the footer section of our page.

```html
<footer>
  <h1><a href="tel:1-800-call-me">1-800-Call-Me</a></h1>
</footer>
```
- Notice the semantic tag `footer` as has been our habit throughout this page.
- The `href` attribute of the `a` tag here is not a web hyperlink, but we let the browser know that it is a telephone number by the "tel:" prefix. Open this page on your phone if you're hosting it, and you should see that link takes you to dial out at that number.
- Style our footer now:

```css
footer {
  height: 170px;
  background-color: #3498db;
  padding: 10px;
}
footer a {
  font-size: 50px;
}
```
- Use the same background color as the header for consistency, and a contrasting color for the font.

4. Final touches

- We can use a couple more styles that will help with user experience, like a better font throughout the page and a way to know what text is hyperlinked.
    - In the `body` declaration, add `font-size: 22px;` and `font-family: 'Helvetica', sans-serif;` for a nicer default font.
    - At the bottom of the CSS file, add 2 new rules:
    ```css

    a {
        color: #f1c40f;
        text-decoration: none;
    }
    a:hover {
        color: gray;
    }
    ```

    - The `:hover` is a [psuedo-selector]() which reacts to a user behavior, and we want it on all the `a` tags.

5. Your final HTML file should look something like this:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Best Home Page</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <header>
      <nav>
        <img src="http://placekitten.com/60/60" alt="logo" />
        <ul>
          <li><a href="#about">About</a></li>
          <li><a href="http://google.com">Google</a></li>
        </ul>
      </nav>
    </header>
    <section class="banner">
      <h1>Mike's Cool Website!</h1>
    </section>
    <section id="about">
      <p>
        Occupy meggings subway tile poutine, bitters slow-carb trust fund XOXO master cleanse venmo. Occupy fap etsy, pour-over brooklyn snackwave blue bottle VHS. Helvetica marfa brooklyn, pok pok deep v hammock +1 actually mlkshk lomo swag activated charcoal cliche ethical selfies. Yr taxidermy austin pop-up salvia, sustainable asymmetrical kickstarter wayfarers plaid succulents craft beer jean shorts. PBR&B affogato air plant, art party umami kickstarter heirloom literally letterpress biodiesel blue bottle next level. Truffaut retro man bun, fap unicorn jianbing blog franzen tacos keytar tumeric pug meditation beard cliche. Fap keffiyeh mlkshk drinking vinegar, chillwave hella prism put a bird on it neutra readymade tbh forage deep v microdosing cold-pressed.
      </p>
    </section>
    <footer>
      <h1><a href="tel:1-800-call-me">1-800-Call-Me</a></h1>
    </footer>
  </body>
</html>
```
- And the CSS:

```css
* {
  vertical-align: top;
}
body {
  font-size: 22px;
  font-family: 'Helvetica', sans-serif;
  margin: 0;
}
header {
  height: 80px;
  background-color: #3498db;
  padding: 10px;
}
header img {
  border-radius: 50%;
}
header nav, header ul, header li {
  display: inline-block;
}
header li a {
  padding-left: 20px;
  color: black;
}
section.banner {
  padding-top: 150px;
  height: 300px;
  background: url("http://placekitten.com/500/500") fixed;
  background-size: cover;
}
h1 {
  color: white;
  font-size: 72px;
  text-align: center;
}
p {
  margin: 5%;
  text-align: center;
}
footer {
  height: 170px;
  background-color: #3498db;
  padding: 10px;
}
footer a {
  font-size: 50px;
}
a {
  text-decoration: none;
  color: #f1c40f;
}
a:hover {
  color: gray;
}
```

#### Basic user experience principles

- [Basic UX Framework](https://uxmag.com/articles/basic-ux%E2%80%8A%E2%80%94%E2%80%8Aa-framework-for-usable-products)
- [UX crash course](http://thehipperelement.com/post/75476711614/ux-crash-course-31-fundamentals)
- [5 Simple Design Principles](https://www.sitepoint.com/5-simple-ux-principles-guide-product-design/)
