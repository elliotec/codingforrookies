---
title: Week 2
date: 2016-10-18 23:22:17
tags:
---
#### HTML
1. Create a new folder called "week2" and open it up in Atom by selecting File > Add project folder. Then create a new file in that folder by right-clicking it and selecting "New file." Name the file "index.html" and select it.
  - Copy the HTML from last week (at the end of step 3 in the previous article) and paste it into the new file.

2. Now we will introduce some new HTML [tags](http://www.w3schools.com/tags/). First, lets look at the `<img>` tag, which is for images. `<img>` [elements](http://www.w3schools.com/html/html_elements.asp) don't require a closing tag because they can't have any content, since all their information is contained within it's [attributes](http://www.w3schools.com/html/html_attributes.asp). Let's put an image on our page right below the `<h1>` tag:

```html
<img src="http://placekitten.com/1000/300" alt="Kitten" />
```

- The `src` attribute is the source of the image we want. It can be within our website directory, or a URL from somewhere else on the web like in our case where we get a placeholder image from placekitten.com. The numbers in that URL correspond to the width and height of the image respectively.

- The `alt` attribute is the alternate text that would show up if the image couldn't be found or is broken, and what [screen readers](https://en.wikipedia.org/wiki/Screen_reader) will use to read instead of the image.

- Save and reload your page. You should see a cute kitten!

#### Emmet

- Before we move on, lets add another useful package to Atom. From the menu bar, select Atom > Preferences, then click "install" on the tree in the left. Search for "Emmet," and click "install" when it pops up.

- Now when you start typing the name of an HTML tag (without it's first bracket), a little popup will show next to the cursor and you can click the item that shows up or press "enter" to have the element autocomplete. This is super useful to speed up writing your HTML. It will autocomplete many of the common attributes in the tags, so stick to the following examples to remove or add attributes as necessary.

#### Forms
1. Below our new `<img>` tag, lets create a web form. We'll put a few input fields in there, and post the form to a back end - which will be our own email in this case - using [formspree](https://formspree.io) which will be the value of the `action` attribute:

```html
<form class="" action="https://formspree.io/your@email.com" method="post">
  <label for="firstName">Name:</label>
  <input type="text" name="firstName" value="">

  <label for="email">Email:</label>
  <input type="email" name="email" placeholder="your@email.com" value="">

  <label for="subject">Subject:</label>
  <input type="text" name="subject" value="">

  <label for="textarea">Message:</label>
  <textarea name="textarea" rows="8" cols="40"></textarea>

  <button type="submit" name="button">Submit!</button>
</form>
```

- There are many different [form elements](http://www.w3schools.com/html/html_form_elements.asp) in which a user can input information. We are focusing only on a few to keep it simple.
  - The `<label>` tag names our `<input>`s and it's `for` attribute corresponds with the `<input>`'s `name` attribute.

- Save and reload your page. You should see a form with a button under the kitten.
  - Notice the email field will validate that there is an @ symbol, or it will show an error. This is because the `<input>` tag's `type` attribute specifies that it is an email field.

##### Posting the form

- If you have Site44 set up as shown in the last part of the notes for Week 1, you can create a new site in it and replace the `index.html` file in that folder with the one in `week2` which you're working in.
  - Now fill out the form and click submit. You should receive an email at the address in the `action` attribute with the form contents!

- You can try submitting the form even if the site isn't hosted, but it will take you to a page that says it needs to be online in order to work. If you get that far you know you did it right anyway.

#### Bootstrap

- Time to make our page look like a real web page and improve the ugly default styling.

- We are going to use a CDN ([content delivery network](https://en.wikipedia.org/wiki/Content_delivery_network)) to link a useful stylesheet framework called [Bootstrap](https://getbootstrap.com) to our page.
  - Google search "bootstrap cdn" and click the first link. Then, under "Complete CSS," click the arrow dropdown. Copy the long `<link>` tag in the field under the "HTML" portion. Paste this tag at the bottom of your `<head>`, just above the closing `</head>` tag and below the last `<meta>` tag, so it looks like this:

```html
<head>
  <meta charset="utf-8">
  <meta http-equiv="x-ua-compatible" content="ie=edge">
  <title>Coding For Rookies</title>
  <meta name="description" content="Coding for rookies Lifelong Learning U of U">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
</head>
```

- Now we will add a few `<div>` wrapper elements and apply some `class` attributes throughout our page to improve the styling.
  - First, wrap the entire content of the `<body>` into a "container," with `<div class="container">` at the top and the closing `</div>` tag at the bottom of the `<body>`. This will give nice margins to our page.
  - Find the ["Forms" section](http://getbootstrap.com/css/#forms) in Bootstrap's documentation, and look at the example. The nice fonts, softened inputs with focus highlights, etc. Thats what we want our form to look like, so we'll implement the elements and class names around the elements as shown in the example.
  - Find the ["Buttons" section](https://getbootstrap.com/css/#buttons) and lets add `class="btn btn-primary"` to the `<button>` element to make it more prominent. The `type="submit"` implicitly tells the form to run it's `action` attribute.
  - Finally, lets wrap our 2 elements above the `<form>` into a `class="jumbotron"` to separate them from the page with some color contrast and font changes.

- Now your entire page should look something like this:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="x-ua-compatible" content="ie=edge">
    <title>Coding For Rookies</title>
    <meta name="description" content="Coding for rookies Lifelong Learning U of U">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">
  </head>
  <body>
    <div class="container">
      <div class="jumbotron">
        <h1>Hello world! This is Coding for Rookies.</h1>
        <img src="http://placekitten.com/1000/300" alt="Kitten" />
      </div>
      <form action="https://formspree.io/your@email.com" method="post">
        <div class="form-group">
          <label for="firstName">Name:</label>
          <input type="text" class="form-control" name="firstName" value="">
        </div>
        <div class="form-group">
          <label for="email">Email:</label>
          <input type="email" class="form-control" name="email" placeholder="your@email.com" value="">
        </div>
        <div class="form-group">
          <label for="subject">Subject:</label>
          <input type="text" class="form-control" name="subject" value="">
        </div>
        <div class="form-group">
          <label for="textarea">Message:</label>
          <textarea class="form-control" name="textarea" rows="8" cols="40"></textarea>
        </div>
        <button type="submit" class="btn btn-primary" name="button">Submit!</button>
      </form>
    </div>
  </body>
</html>
```
- Go ahead and play around with this and try implementing some more tags and seeing if you can get them to submit to your email.

#### Extra resources

- My favorite book on HTML (and CSS) is [HTML & CSS by John Duckett](https://www.amazon.com/HTML-CSS-Design-Build-Websites/dp/1118008189). If you read this entire book back to front, and do the exercises along the way, you'll have an excellent foundation in these languages.

- If you want a more extensive introduction to HTML, try out the course on [FreeCodeCamp](https://www.freecodecamp.com). This is a wonderful free online course that is far superior to others like [Codecademy](https://codecademy.com), but don't hesitate trying others too.

- Learn more about how HTML forms work by reading [this article](http://www.javascript-coder.com/html-form/html-form-tutorial-p1.phtml).

