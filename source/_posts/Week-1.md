---
title: Week 1
date: 2016-10-11 17:07:36
tags:
---
#### Setting up our development environment and creating our first website
1. [Download and install Google Chrome](https://www.google.com/chrome/)
  - Right click anywhere in the page and choose the "Inspect" option.
    - You can click around and look at the code for what is creating the stuff on the site. This is how people learned how to create web pages in the early days - by looking at how other people did it first.

  - Right click anywhere in the page and choose the "View Page Source" option.
    - This is not as interactive as "Inspect," but gives a full high level overview of how a web page is structured.

  - We will go over the dev tools more as we progress through the class.

2. [Download and install the Atom text editor](https://atom.io)
  - Text editors are like word processors, but for code. They are useful for editing and reading all types of code, and there are many different editors. We are using Atom for a number of reasons, mainly it's easy set up and learning curve.

  - Poke around the settings a bit, and select Packages then search for "autosave." Click the option that comes up, and look for the "enable" checkbox and check it. Now your files will save whenever you leave the window! Feel free to install other themes and packages you like if you feel like it.

  - Check out their [flight manual](http://flight-manual.atom.io/) for more information about Atom and how to use and customize it.

3. Create a new directory (aka folder) on your desktop or somewhere you can easily access it. Name it "week1" or something similar.
  - In Atom, go to File > Add project folder then find and select your newly created week1 folder. When you see the folder in the left section, right click it and select "New file." Name the file "index.html," and open it.

  - Type "Hello World!" in the file, save it, and double click the file in the location you created it. It should open up in Chrome, and now you've created your first website!

  - But, it's not exactly proper HTML. Lets add an HTML tag so the browser can make more sense of it.

```html
  <h1>Hello World!</h1>
```

  - Save it, and reload your browser. It should be big and bold.

  - Now we need to add the bones of the structure of an HTML page that will make it work online. Go to [html5-boilerplate](https://github.com/h5bp/html5-boilerplate/blob/master/dist/index.html) and look at the code there. We only need to use a few pieces of this for our site.

```html
<!doctype html>
<html class="no-js" lang="">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="x-ua-compatible" content="ie=edge">
    <title>Coding For Rookies</title>
    <meta name="description" content="Coding for rookies Lifelong Learning U of U">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>
  <body>
    <h1>Hello world! This is Coding for Rookies.</h1>
  </body>
</html>
```

- Now you have your first _real_ website.

#### History of computing and the Internet

- The history of computing, begins with the first programmer, [Ada Lovelace](https://en.wikipedia.org/wiki/Ada_Lovelace), and the first "computer," Charles Babbage's [Analytical Engine](https://en.wikipedia.org/wiki/Analytical_Engine) which Ada conceptualized the idea of programming for over snail-mail correspondence in the early 1800s. [Alan Turing](https://en.wikipedia.org/wiki/Alan_Turing) brought the idea back to life in the 1930s.
  - Computers started gaining traction [in the WWII era](https://en.wikipedia.org/wiki/Computer#Pre-twentieth_century) while funding was abundant and were the size of rooms and used vacuum tubes until transistors became mass produced.

 - History of the [Internet](https://) and [World Wide Web](https://en.wikipedia.org/wiki/World_Wide_Web) started with their precursors like [ARPANET](https://en.wikipedia.org/wiki/ARPANET) in the 1960s and 1970s, and remarked on how the University of Utah [played a vital role in the birth of the internet](http://archive.sltrib.com/story.php?ref=/News/ci_14019277) by being one of it's [first four computer network nodes](https://www.scientificamerican.com/gallery/early-sketch-of-arpanets-first-four-nodes/).
   - The difference between the Internet and the World Wide Web is important to note. The Web exists in the Internet among a number of other things like email, file sharing, and others.
   - [Tim Berners-Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee) is credited as the inventor of the World Wide Web in 1989 and Hyptertext some years before that. He also built the first web browser and the first web site went online in 1991.
    - Tim also created [HTML](https://en.wikipedia.org/wiki/HTML) and [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol), two important backbones of the Web.

#### Governing bodies of the Internet

- There are [several governing bodies](https://en.wikipedia.org/wiki/Internet_governance) of the Internet that operate globally and keep things moving smoothly and within standards.
  - Two of the most powerful governers are [ICANN](https://en.wikipedia.org/wiki/ICANN), which controls the naming of domains and their [IP addresses](https://en.wikipedia.org/wiki/IP_address), and the [W3C](https://en.wikipedia.org/wiki/World_Wide_Web_Consortium), which is led by Berners-Lee and creates and regulates the standards of the World Wide Web, including which languages and styles are used and read by browsers and how these evolve.

#### Relationship between hardware and software

- When we write code for the Web, we are basically going several levels of abstraction above the hardware, with the programing language eventually telling the circuits when and where to allow the electrical pulses through. This is what [binary](https://en.wikipedia.org/wiki/Binary_number) (1s and 0s) is, 1 means allow the electrical pulse through (on) and 0 means don't (off).
  - These electrical pulses decide what your machine does from saving form data from a web page to flicking on the right pixels on your monitor.

#### How the Internet and Web work
 - The Web's architecture is built around a [Request-Response](https://en.wikipedia.org/wiki/Request%E2%80%93response) cycle, in which a client (in our case a browser or user) makes a request to a server - like to get a URL of your friend's Facebook profile page, and then the server sends back a response - like returning the HTML code of your friend's Facebook profile page.

#### Hosting and DNS

- [Site44](https://site44.com)
  - If you want to host your projects for the class, set up a [Dropbox](https://dropbox.com) account and then try out the free trial of [Site44](https://site44.com). All you have to do is follow the instructions given, which mainly consist of replacing the index.html file in the newly created Site44 folder in your Dropbox.
  - There are many other ways to host web pages, but this is among the easiest.

- [iwantmyname](https://iwantmyname.com)
  - If you want to purchase custom domain names, I recommend iwantmyname. You can easily hook it up to hosting services like Site44 to route to your domain, among other apps you might need in the future.

#### Extra resources

- My favorite computer history book is [The Innovators by Walter Isaacson](https://www.amazon.com/Innovators-Hackers-Geniuses-Created-Revolution/dp/1476708703). It is a fantastic biography of many of the biggest names in computing.

- Learn more about the Chrome Developer Tools by checking out [this Code School tutorial](https://www.codeschool.com/courses/discover-devtools). This is something you can do one lesson at a time keeping up with the class if you're interested.
