# HTML Introduction - Part 1
### Learn the basics of HTML, including tag types, tag attributes, and their display properties
_Dec 30, 2020_

Hypertext Markup Language, also known as HTML, can be thought of as the foundational building block of web development. When you inspect the source code for an element on the page, you're going to see the HTML markup for that element. Before we get into specific details related to HTML, I want to start by giving you a conceptual overview. I won't go into the history of HTML because it's not relevant for our purposes in learning how to use it, but if you're interested there's plenty of information available online.

I find it helpful to think of a web page as a document. Sure, it may have images, forms, and fancy interactive widgets, but at it's core it is just a document. The purpose of HTML is to be able to format, or mark up, a document to give it structure. If you think of any type of document, chances are it will have some, or all, of the following:

- Headings
- Subheadings
- List(s)
- Text formatted with bold or italics

If documents didn't have elements like these they would be much harder to read because it would just be endless text with no structure or emphasis on anything. HTML provides us with a simple way to add structure to our documents using something called _tags_.

## HTML Tags
HTML tags allow us to format elements like text or images on our page to look or act a certain way. Tags are written using angle brackets, also known as greater-than and less-than symbols. Here is an example of a paragraph tag containing some text:

```
<p>Some paragraph text!</p>
```

There are a few things worth noticing here:

1. Our paragraph began with an opening paragraph tag (usually referred to as a 'p tag'): `<p>`
1. Our paragraph ended with a closing p tag: `</p>`
1. The difference between the opening p tag and the closing p tag is the `/`, which comes right after the first angle bracket in the closing p tag. This slash denotes the closing of a tag.
1. We can have as much text between the opening p tag and the closing p tag as we want. I kept my example short, but you can add as much or little text within a paragraph as you like. All text within this p tag will be formatted in our document as a single paragraph.

### Common HTML Tags
Here are some very common HTML tags that you should get familiar with. This is not a complete list of all HTML tags, but it's a good starting point.

- `<h1>` - Heading level 1. This is the highest level heading available and should only be used once on a page.
- `<h2>` - Heading level 2. H2's are typically used as a heading for individual sections on a page.
- `<h3>`, `<h4>`, `<h5>`, `<h6>` - The remaining heading tags, used to add headings to different parts of a page. It's not common to see all types of heading tags on a page but you could if you needed to. As you move down towards `<h6>` the text becomes smaller and can be thought of as less important.
- `<div>` - A generic _block level_ container. We will cover the meaning of _block level_ later in this article.
- `<span>` - A generic _inline_ container. We will cover the meaning of _inline_ later in this article.
- `<section>` - Another common _block level_ container representing a standalone section of the page. Sections will typically, but not always, have a heading within them.
- `<p>` - The paragraph tag we were just looking at. It is used to contain a paragraph of text.
- `<a>` - The anchor tag, which is used to create links on the page.
- `<ul>` - An unordered list. This collection of bullet points you're reading right now is an unordered list.
- `<ol>` - An ordered list. When a list uses numbers instead of bullet points, as is the case directly above this section, it's called an ordered list.
- `<li>` - This is a list item. Each individual item in the list goes within an `<li>` tag.
- `<img>` - An image tag, used to specify an image to display on the page.
- `<strong>` - The strong tag formats text as __bold__.
- `<em>` - The emphasis tag formast text with _italics_
- `<form>` - The form tag is used to create the shell of a form on the page.
- `<input>` - Input tags are commonly used within forms. They can be used to represent text inputs, buttons, checkboxes, radio buttons, and many other elements.

### Nesting Tags
Most tags allow you to add text, as well as other tags, within them. When one tag is added within another tag, it's called nesting tags. The exception to this rule is if you're using a _self-closing tag_, which we will get to in a minute. Here is an example where we have a `<p>` tag containing some text, and we're nesting a `<strong>` tag within the paragraph in order to bold one of the words:

```
<p>Some <strong>paragraph</strong> text!</p>
```

In your browser screen, the HTML from that example would look like:

Some __paragraph__ text!

Another common example of nesting tags is when you're creating a list. You first choose a tag for the type of list you want, then use `<li>` tags for each item in the list, like this:

```
<ul>
    <li>The first item in my list</li>
    <li>The second item in my list</li>
    <li>The third item in my list</li>
</ul>
```

### Self-closing Tags
While most tags consist of an opening tag and a closing tag, there are some tags that close themselves, and therefore cannot contain any text or nested tags. Two of the most common self-closing tags are the `<img>` and `<input>` tags. Here's an example of a very basic image tag:

```
<img src="/path/to/image.png" />
```

Notice the slash at the end, right before the angle bracket? That's an easy way to tell that this is a self-closing tag. As of the release of HTML5 it is no longer necessary to end self-closing tags with a slash, so you _can_ write them like this:

```
<img src="/path/to/image.png">
```

However, I personally prefer including the slash because it means my HTML is written with valid XML syntax, and it makes it obvious that I'm acknowledging a tag as being a self-closing tag. In the end it's up to you to decide how you write them, unless you're part of a team who has a convention for these types of tags. As usual, consistency is key.

### Tag Attributes
If we look at the image example from the self-closing tags you'll notice that it included `src="/path/to/image.png"` within the tag. The `src` part is known as an _attribute_, and `="/path/to/image.png"` is the value of that attribute. Attributes can be written on any HTML tag, not just the self-closing ones, but not all attributes are valid on all tags. For example, `src` is a valid attribute on an `<img />` tag because it specifies the location of the image you want to display, but `src` would not be a valid attribute on a `<p>` tag. Frequently tags will contain multiple attributes, like this:

```
<img src="/path/to/image.png" alt="Show this text to screen readers, or if the image fails to load." />
```

`alt` is another attribute that works with `<img>` tags only. Let's look at another example of using attributes, this time for creating a link on our page:

```
<a href="https://google.com">Search on Google</a>
```

Technically the `<a>` tag is all that is necessary to create a link, but if you didn't include the `href` attribute, the link wouldn't point anywhere and would be useless. In this case we are linking to an external site (google.com), but we could also be linking to another page within our site, like this:

```
<a href="about.html">About me</a>
```

Here's one more example of tag attributes to help drive it home. This one creates a text input, which would commonly be used in a form. This text input also contains a `name` attribute, which is helpful when creating form elements:

```
<input type="text" name="first-name" />
```

#### Universal Tag Attributes
While some attributes are only valid on certain tags, there are others which can be used on any tag. Here are a few of the most common ones:

- `id` - A unique identifier for an element on the page. Id's should __never be repeated__ on the page.
- `class` - Classes are used in conjunction with CSS and JavaScript. You can have as many classes within the attribute as you like, just make sure to separate them by a blank space, like this: `class="class1 class2 class3"`. Unlike Id's, you can repeat classes by using them on as many elements as needed.
- Data Attributes - These are a slightly more advanced topic. Basically you can provide custom names to data attributes, like `data-language="JavaScript"` and then write JavaScript or CSS to handle them accordingly. Don't worry too much about these for now.

### Block-level versus Inline tags
#### Block-level tags
When we talk about block-level versus inline tags, what we're referring to is how much space the tag takes up on the page. A block-level tag will consume the full width of it's container, assuming there is a container, otherwise it will consume the entire width of the page. Even if you write the tags side-by-side, they will still be broken out into separate lines.

Here's an example - you could write these two paragraph either like this:

```
<p>First paragraph</p>
<p>Second paragraph</p>
```

or like this:
```
<p>First paragraph</p> <p>Second paragraph</p>
```

But either way the text would be rendered on page on two separate lines/rows, like this:

First paragraph

Second paragraph

They render this way because `<p>` tags are block-level, and unless you doing some custom CSS styling, block-level tags don't render side-by-side on the page.

##### Common block-level tags
- `<div>`
- `<section>`
- `<h1>` - `<h6>`
- `<p>`
- `<ul>`
- `<ol>`

#### Inline tags
Unlike block-level tags, inline tags _do_ render side-by-side on the page. They only take up as much width as is needed by the content within them, or as their styling rules dictate (more on that when we get to CSS). They will not take up a full row by default like block-level tags do. `<a>` and `<span>` are two very common examples of inline tags, so you could easily do somthing like this without worrying about the text breaking up into muliple rows:

```
<span class="red-text">Please click</span> <a href="https://yahoo.com">My Yahoo link</a>
```

##### Common inline tags
- `<span>`
- `<a>`
- `<img>`
- `<strong>`
- `<em>`

### Whitespace
One more important concept to cover early revolves around whitespace (blank spaces) in your code. You can't rely on whitespace between tags or words in your HTML code to handle spacing between them on the rendered page. The browser will respect one blank space between tags in your HTML code, but no more than that. So, if you had two inline tags and you wanted them separated by 5 empty spaces, you couldn't do this:
```
<span>First element</span>     <span>Second element</span>
```

Ultimate the browser would treat it like this:
```
<span>First element</span> <span>Second element</span>
```

Even if you wrote this:
```
<span>One     Two     Three</span>
```

The browser would still treat it like this:
```
<span>One Two Three</span>
```

The moral of the story here is to not rely on whitespace to handle spacing in your page. Webpage layout should always be handled with CSS, which we will get to in a future article.

## Conclusion
We covered a lot in this article so it might not be a bad idea to read it twice, or just follow along with the video as well. Before moving onto the next lesson, try to get some experience writing HTML tags. Don't worry about creating HTML files yet, just utilize one of the following sites, which allow you to write little code snippets and see them rendered on screen:

- [Codepen](https://codepen.io/pen/)
- [JsFiddle](https://jsfiddle.net/)
- [JsBin](https://jsbin.com/?html,output)

__Challenges__

- Write a paragraph of text
- Bold one of the words in your paragraph
- Turn a word in your paragraph into a link, linking to a website of your choice
- Research to figure out what attribute to add to your link to make it open in a new browser tab when clicked
