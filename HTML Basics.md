[[HTML]] is, in its most basic abstraction, a series of [[Element]]s used to make content appear in a certain way, allowing you to change formatting, link to other pages and many more things.
HTML files live, of course, in `.html` files, the most common of these being the `index.html`
# Tags and elements

To make a paragraph in HTML: 

```html
<p>Your waitress was miserable</p>
```

This is a paragraph element.
That's really easy!, this also works for headings.
Another important thing is that tags in HTML are *case insensitive*.
Also, you can nest elements: 

```html
<p>And so was <strong>your food</strong></p>
```
# Void elements 
Elements that cannot contain other HTML elements are called *void elements*, and as such, they do not follow the pattern of opening an closing tags. One such element is the `<br>` element, which inserts a line break into text.

```html
<p>
The car went up the avenue <br>
And disappeared around the bend.
</p>
```

It's not uncommon to see `/` at the end of a void element's tag, but it's not strictly needed. You may see it to improve readability.
# Attributes
Attributes contain extra information about an element.
The `class` attribute assigns, well, a class to an element for targeting it later with styles through [[CSS]] or scripting by using [[JavaScript]].

```html
<p class="editor note">Well now then, Mardy Bum</p>
```

Attributes can be placed and matched depending on the element, for instance, the `<img>` element, which is used to display images, is compatible with the following attributes:
- `src`: specifies the [[URL]] of the image
- `alt`: allows for a description of the image to be given
- `width`, `height`: allows for manipulation of the dimensions of the image

```html
<img src="https://assets.nintendo.com/image/upload/q_auto/f_auto/store/software/switch/70010000001107/fc38578b345af43fbc7bd1eb5be84594ab6c28bd8927ce8fca97e08071f2705d"
alt="bayo"
height="300" />
```

This displays an image of Bayonetta 2, assigns it with the description *bayo* and modifies its height to 300.![[Pasted image 20260223092754.png]]
## Boolean attributes
There is a certain kind of attribute that is written without values, those are *boolean attributes*. Whenever they're added their value is set to `true`, if an attribute is not included in a tag, then its value is `false`.
Take, for example, the `disabled` attribute and how it interacts with the `<input>` element.

```html
<label for="first-input">This input is disabled</label>
<input id="first-input" type="text" disabled />
<br />
<label for="second-input">This input is not disabled</label>
<input id="second-input" type="text" />
```
![[Pasted image 20260223155102.png]]
## Quotes and attribute values
It's generally good practice not to omit quotes when giving attributes values, but in certain cases it's okay not to.

For instance, an attribute interprets its value as a string, so if it has no spaces, it's safe to not use them; in the case of *anchors*, which are wrappers for text that embed links in them, syntax can look like this:
```html
<a href=https://www.monkeytype.org>The best typing test on the internet</a>
```
However, if we were to add the `title` attribute to provide a description of the website and omit the quotes, everything breaks:
```html
<a href=https://www.monkeytype.org title=Customizable writing test>The best typing test on the internet</a>
```
![[Pasted image 20260223163948.png]]
Clearly unintended behaviour.
# Anatomy of an HTML document
While elements aren't that impressive on their own, they truly shine when they come together in an HTML document.

This,
is a webpage.
```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```

Let's break it down:
1. `<!doctype html>`:  A historical artifact of the early days of HTML, once needed to act as links to sets of rules that the HTML page had to follow to be considered good. Nowadays, it's only used to make sure that everything functions correctly.
2. `<html></html>`:  The `<html>`/root element, wraps everything on the page.
3. `<head></head>`: This element houses information about the page that isn't visible to the user.
4. `<meta charset="utf-8" />`:  The meta element, it represents [[Metadata]] that describes the page. The `charset` attribute specifies the [[Character Encoding]] that the document will use. UTF-8 is one of the most adopted ones and includes glyphs from many languages.
5. `<title></title>`: Sets the title of the page, who would've thought... It's the same name that gets used when bookmarking a page or hovering over it on a browser.
6. `<body></body>`: This contains all of the content that is displayed on the page. ALL OF IT.

Putting it all together:
```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>My test page</title>
  </head>
  <body>
    <h1>Music and human emotion</h1>
    <p>
      Music acts as a bridge between people and cultures in a way that natural language could never hope to achieve. Sound is <strong>instinctual, primitive and yet complex</strong>. <a href=https://www.youtube.com/watch?v=C2IKm9gGipY>Emotion</a> is carried through the air and into our hearts when we listen to music. <br />
<a href=https://www.youtube.com/watch?v=pI5-LvbE4AE>Be lonely no more.</a>
    </p>
    <image 
      src="https://preview.redd.it/bill-evans-v0-09hb5shpl0te1.jpeg?width=640&crop=smart&auto=webp&s=9c61290c5c961425593b00940a39c23556e1e5b7" 
      alt="Bill Evans"
      width=400
      />
  </body>
</html>
```
This renders on a webpage as follows:
![[Pasted image 20260223172740.png]]
