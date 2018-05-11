# Introduction to HTML

**Note:** This lecture involves a lot of show-and-tell with the students (after all,
seeing is believing)! Prep and 'making the lecture our own' is key. The basics
of HTML can be lackluster when provided in text-book format. Lucky for us, HTML
is so easy to bring to life with the browser. This should be a constant back and
forth between lecture/explanation and looking at results in
Chrome/Firefox/Internet Explorer. Make sure you read through these notes before
hand and have your example flow prepared!

## Objectives

This lesson will focus on introducing students to the essentials of HTML, as
well as its real interaction in the browser. As opposed to taking a "memorize
the top used tags" approach, this lesson focuses on communicating the higher
level concepts of HTML.

## SWBATS

HTML - Communicate the role of HTML
HTML - Create valid HTML pages
HTML - Identify the core tags
HTML - Create a browser ready HTML file

## Introduction

HTML, or HyperText Markup Language, is a **markup language** which describes the
structure and organization of web pages. Web browsers, such as Mozilla Firefox,
Internet Explorer, and Google Chrome read HTML and use it to display websites.
Unlike Ruby, JavaScript, and other programming languages, markup languages like
HTML don't have any logic behind them (we can't make an `array.each` with plain
HTML).

Every website you use is running with HTML as the core component that describes
how it looks.  

**NOTE:** Show students the Chrome developer tools. Specifically, show them the HTML of
some website. Perhaps ask them "Someone give me a website. Let's look at the
HTML for it!" Following, go to the website, open up Chrome developer tools,
(`command + option + i` on mac, or right click), and go to the 'Elements' tab.
From there, do something with an immediate visual effect (i.e. change the text
on some major title element).

Ok, so now you 'hacked' the page. In front of the whole class, you altered the
data on a webpage. Of course, we didn't really change the webpage. If someone
else goes to the website, they won't see the changes you made. What actually
happened then?

**Note:** Now is an excellent time to describe that the HTML you received was only a copy
of the real website, sent from their server, to our computer. Don't take for
granted that this might be a completely new concept to many of your students.
Our computer's browser (Chrome, in this case) simply got a copy of the
HTML/CSS/JavaScript from the server behind the URL we went to, and presented a
**copy** of it. If we make changes in our browser, all we are changing is the
copy of it, _not_ the actual website.

## HTML Document structure

Every HTML document requires some basic structures:

```html
<!DOCTYPE html>
<html>
<head>
  <!-- Contains resources, such as styling links, meta data about the site and the page title -->
</head>
<body>
  <!-- Contains all visible elements of a page -->
</body>
</html>
```

#### `<!DOCTYPE html>`

At the top of every HTML document, you're always going to start off with the
same element, `DOCTYPE`. The `DOCTYPE` element starts with a `<`, followed by
an `!` and `DOCTYPE`, then specifies which version of HTML we want to use. In
HTML5, we just say `html`, and the browser will interpret the rest of the
document as HTML5. To close the element, add a `>` at the end. Go ahead and
add `<!DOCTYPE html>` to your `index.html` file.

#### `<html> </html>`

The next element is also always required: `<html>`. This tells the browser
that everything that falls between the opening and closing `html` tags is to
be interpreted as HTML code.

One attribute that is important to include in the `<html>` tag is `lang`, which
declares what language the webpage is written in. In our case, writing in
English, we will use `lang="en"`. This helps search engines to know what
language a page is written in. Our `index.html` should now look like this:

```
<!DOCTYPE html>
<html lang="en">
</html>
```

#### `<head> </head>`

Inside our `<html>` tags, we divide the page into two main sections, `<head>`,
and `<body>`, which both play unique roles. Before we get to adding viewable
content, there are some additional bits of information we need to declare about
our webpage, and this information will be stored in the `<head>`.

In the `<head>` section, we place a number of specific tags.

* The `<meta>` tag provides metadata about the document, including what
  character set to use, a description of the content, specific keywords, and the
  author. Adding this metadata on the content of the page helps search engines
  to know what the page contains. There is also a `viewport` method, which
  instructs the browser on how to control the page's dimensions and scaling.
  Examples of `<meta>` tags we can add into our `head` section:

```
<meta charset="UTF-8">
<meta name="description" content="Kode with Klossy example HTML site">
<meta name="keywords" content="klossy, html lecture">
<meta name="author" content="You">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

* The `<link>` tag is also used here, and is for importing in external files.
  Most commonly, we'll see this being used to import in CSS style sheets as
  well as fonts. In the below example, `link` is used to import in a specific
  Google font:

```
<link href="https://fonts.googleapis.com/css?family=Monoton" rel="stylesheet">
```

* Another common tag in the `<head>` is `<title>`. The `<title>`, as its name
  implies, is where the title of the webpage should be entered. Text added inside
  the `<title>` tags will appear up on your browser tab. Let's add a title for
  our `index.html` page:

```
<title>My Example Website - About</title>
```

#### `<body> </body>`

The `<body>` part of an HTML page contains all of the displayable parts of a web
page, including all the page's text, navigation, links, images, videos, etc..
While you need to know how to set up the document structure, almost all of
your time working with HTML will be spent on setting up content inside the
body section.

## HTML Elements

We want to get you all building a website ASAP and having fun with HTML and we
could spend weeks examining different specifics of HTML, but there is only one
core concept we need to teach to get you successfully adding things to the
screen: _HTML Elements_.

HTML consists of different elements. Most elements use a 'tag' to identify what
kind of element they are. This 'tag' wraps around content. Take a look at our
most basic HTML element:

```HTML
<div>
  Hello, World!
</div>
```

**Note:** Throw this in a brand new file (`file-name.html`) and open it up in Chrome.
Alter the inner text and then refresh to show them the change.

In this example, the `<div>` element/tag is just the HTML communicating: "Hey,
this is general division of content. Everything in here belongs to this `<div>`
element."  

Let's see what happens when add a header tag to the top level of our HTML:

```HTML
<h1>
  This text is wrapped inside a header element!
</h1>

<div>
  Hello, World!
</div>
```

**Note:** Refresh to show the changes

As we see, text is rendering to the screen differently when its inside of a
different tag. In this case, the `<h1>` tag is specifically saying "I represent
header content."  

Elements can also be nested within others, à la:

```HTML
<h1>
  This text is wrapped inside a header element!
</h1>

<div>
  <h1>
    This section shows how different tags manage whitespace
  </h1>

  <div>
    I am not haiku
    Newlines mean nothing to divs
    One line, must I be
  </div>

  <pre>
    I am a haiku
    Wrapped in a preserved text tag
    My line breaks you see
  </pre>


</div>
```

Elements aren't just for text, they are for every type of content we experience
on web pages. There exist elements for:
  - displaying lists
  - saying what the text on the top of the page tab should be
  - drawing pictures on the page
  - images
  - sounds (that's right, not just visual things!)
  - scripts (they surround custom programs that interact with our website)
  - and many more!

**Student 10 minute Student Empowerment Pair Exercise:** First, show students
how to open an html file from your computer in Chrome/their browser. Students
should the break up into small groups and work on the following:

  - Create a new HTML file
  - Find out (with Google-fu) what tag is used to represent images and GIFs
  - Find our how those tags use urls to link images/GIFs
  - Use the following url in the correct tag to get the GIF displaying when they
open the file with Chrome: https://gph.to/2JFqv97

**Note:** Bring the class back together and grab some solutions from students. Dissect as
a group what the "src=" part of the tag is for (some groups may not have been
successful, so explore the solution from the beginning). This will transition us
nicely into **attributes!**.  

## HTML Attributes

Attributes flesh a tag out by providing additional information. A simple example
is the `<img src="imageurl.gif">` attribute, which was used to provide more
context to the image tag. Without the source value, all we have is the skeleton
of a tag, and it has no clue what content it should be displaying!

Attributes have a wide variety of jobs, from describing the size, color, and
other visual facets of a tag to the sound file that it should play. Let's see
how we can use attributes to describe more specific visual effects:

```HTML
<body style="background-color:blue">

</body>
```

Don't worry at this point about memorizing which attributes do what, or which
tags are most appropriate where. There are simply too many tags and attributes
to memorize in one sitting. Your time is better spent using your Google-fu
whenever you encounter an obstacle to displaying what you would like to in HTML.  

## Moving Forward

We'll return to talk more in depth about HTML later, but with _only_ what we've
covered so far, you are all capable of creating the structure of entire webpages.  

Our examples aren't very stylish just yet, and that is okay! HTML is really the
_skeleton_ of a web page and we need to know it before we can start adding in
all the stylish parts.
