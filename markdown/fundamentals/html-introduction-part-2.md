# HTML Introduction - Part 2
### Creating HTML documents
_Jan 2, 2021_

Welcome to part 2 of my HTML introduction! In the last article we learned about HTML tags, their display properties, and how attributes can be added to them. In this article we will take things a step further by creating entire HTML documents and viewing them in a browser. You're going to need to fire up your favorite text editor for this lesson, so go ahead and do that now, or if you're not familiar with text editors, please check out the first article in my Web Development Fundaments series called "Web Development Tools".

## HTML documents
Any file with a `.html` extension is considered an HTML file. Technically there are no requirements regarding the structure of the contents within the HTML file, as we will see in the first example, but in all practicality there are certain requirements for how your HTML file is formatted. When you have an HTML file saved on your computer you can open that file with your browser to view it. You can either go to the File menu, select Open, and select that file from your hard drive, or most browsers will allow you to use the keyboard shortcut Control + o, which allows you to skip the File menu.

## Creating your first HTML file
We'll keep things very simple for starters, so go ahead and create a new file in your text editor, write the words `Hello World!` in that file, and save the file to your desktop as `hello.html`. Now head on over to your browser of choice and open that file. Congratulations, you have just created your first web page, which should look something like this:

// insert hello01.png here

## Giving your file some structure
While the file we just created is technically a valid HTML file, that's now how you would write it in the real world. I'm going to create that document into a valid HTML5 document, then explain everything going on in that file.

```
<!DOCTYPE HTML>
<html>
    <head>
        <title>My Hello World page</title>
    </head>
    <body>
        Hello World!
    </body>
</html>
```

If you convert the file you created into this and open it in the browser, the rendered output on the screen will look identical to what you had before, but now we've got a lot more going on under the hood. Let's break it all down.

### Doctype
You should make it a habit of declaring a doctype on the first line of your HTML file. In the old days of web development, before HTML5 became standard, there were a variety of different doctypes to choose from, each of which had it's own set of rules for how the browser should parse the HTML markup on the page. They tended to be long ugly strings, like this:

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">
```

Obviously no one would ever remember those, so you would always have to copy it from somewhere and paste it into your file. Well, those days are behind us now that we have HTML5. An HTML5 doctype is much cleaner and simpler, making it easy to remember. In my example I wrote it all using uppercase letters, but it's also valid to write it using lowercase letters. Just make sure to include it because it tells the browser to treat this as an HTML5 document.

```
<!DOCTYPE HTML>
```

### The HTML tag
The `<html>` tag should always directly follow your doctype declaration. It's just like any other tag in terms of it's syntax, and notice that it has a closing `</html>` tag at the end of the file. Everything in your document, except the doctype declaration, should be nested within the `<html>` tag, and you should never have more than one `<html>` tag in the file.

### The Head tag
The `<head>` tag is the first thing that should come within the `<html>` tag. The most important thing to note about the `head` of the document is that the contents of this section will not appear on screen. One of the primary purposes of the `head` of the document is to declare _metadata_ about the page. If you're not familiar with metadata, just think of it as data consumed by search engines which help them determine if the content in this page is relevant to what they're searching for. There are plenty of different things that can be added to the `head` of the document, like links to CSS files and various `<meta />` tags, but by far the most important thing to declare in the `head` of your document is the page's `title`, which we'll get to next.

Before moving on though, notice how the `<head>` tag is indented a bit from the `<html>` tag? This is a common convention when writing HTML files, as well as most other types of code files. It just makes things easier to read because you can align the opening and closing tags on different lines. It would be much more difficult to read if written like this:

```
<!DOCTYPE HTML>
<html>
<head>
<title>My Hello World page</title>
</head>
<body>
Hello World!
</body>
</html>
```

The amount you indent each line is up to you, but generally it will either be 2 or 4 spaces. Some developers prefer using tabs over spaces, and setting the default tab length to either 2 or 4 spaces. This can become a heavily debated topic but to me having consistency is the most important thing. Generally when you join a development team they will have things like this already defined, so it's important to stay consistent with how they're doing things. If you're starting your own project from scratch then it's up to you to decide, but try to keep things clean by staying consistent. Most text editors have an option for turning on vertical rulers, making it easy to keep everything correctly aligned.

### The Title tag
In this current example, the only piece of metadata I included in the page was a `title`. I did this in order to keep things simple, but there is no question that a `title` is the single most important piece of metadata on a page. It's the most important piece of information in terms of SEO (Search Engine Optimization), it's what shows up when you bookmark the page, and it will often appear in the browser tab. There aren't too many always or never rules in web development, but I feel confident in saying __you should always include a title on your webpage.__ I honestly can't think of a scenario where a page shouldn't have a `title`.

As far as populating the `<title>` tag, my best advice is to be descriptive without being overly verbose. You wouldn't want to write a full sentence in there, but a single word usually isn't good either. Having a title of "Home" isn't good because it tells the users and search engines nothing about your page. Think of one or two key words relating to the content of your page and try to include them in the page's title. I try to think of it like this - if someone is searching for something related to my web page, and I wanted my page to appear in those listings, what would they be searching for? Once I have an idea of what I think they would be searching for I write a `title` tailored to that search.

SEO is a huge topic that entire courses are dedicated to, and this is just a drop in the bucket in terms of what you would need to learn to become an expert in that field, but it gets you thinking in that direction. For now, just try to cement it in your brain that every web page you build needs to include a `title`.

### The Body tag
Now that we have closed out of the `<head>` tag, it's time to move onto the `<body>` tag, which is where the visible contents of the page live. In our current simple example we only have the text "Hello World!" within the body of the page, but normally the body would be filled with all kinds of `<section>`, `<div>`, `<a>`, and `<img>` tags, plus so much more. It's important to constantly be checking your work by refreshing the page in your browser as you add new content to the body of your page. It's going to take some time to understand how the changes you make to markup of your page result in layout changes in the browser, so just take your time and have fun with it. This is where it becomes kinda like painting a picture, but the nice thing with code (compared to paint) is that you can easily undo your changes with control + z when you make a mistake.

## Adding to the head of the document
I'm now going to continue adding to our HTML file in order to make it look a little more like a real-world website. For this section we'll just stick to the head of the document. Just like before, I'll provide the code example first, then explain what's going on.

```
<head>
    <title>My Hello World page</title>
    <meta name="description" content="Part two of the HTML introduction from Michael Pellegrini's Web Development Fundamentals course. Learning to create HTML documents." />
    <meta name="keywords" content="html, web development, web development fundamentals, learning html, html documents, html files" />
    <link rel="stylesheet" href="/path/to/styles.css" />
</head>
```

Okay now the head of our document is starting to look better. You can see we still have the same `<title>`, but we've added two `<meta>` tags and one `<link>` tag. Notice that all 3 of these new tags are self-closing tags, which we discussed in the previous article. Before we get into the meaning of these tags I just want to mention that the order you write the tags in doesn't strictly matter. It's generally thought of as a best practice to keep your `title` as high up in the head as possible because you want the browser to parse that information as quickly as possible, but if you decided to write the `<link>` tag above the `<meta>` tags, for example, that would be perfectly acceptable.

### The Meta Description tag
With that out of the way, lets dig into each of these 3 new tags, starting with the top one. This is known as the "meta description" tag, and it's probably the second most important piece of metadata on your page, in terms of SEO. The contents within the `value` attribute of this tag will frequently be printed in search results, depending on which search engine you're using, so the content here is extremely important. Remember how I said not to write a sentence as the title of your page? Well, that's true, but you should put that sentence here within the meta description tag instead.

### The Meta Keywords tag
Our next meta tag is known as the "meta keywords" tag, and it too is very important for SEO. In this case, rather than writing a sentence describing your page, like you did for the meta description tag, the value of the meta keywords tag should be a collection of terms relevant to your page. In my example above I chose a variety of terms that would be relevant to this page you're viewing now. Each term is comma-separated, and there is no limit to the number of terms you're allowed to include.

### The Link tag
The final addition I made to the head of the document was adding a `<link>` tag. I know we haven't gotten to CSS yet, but this is how you would include an external stylesheet to your page. I could also replace the `<link>` tag with a `<style>` tag and write all of my CSS here, directly within the head of the document, but we'll get more into that in the CSS section of the course. It's much more common to see an external style sheet linked to the HTML file, which is why I chose that as my example.

You might have noticed that the way we called out the specific CSS file to include was via the `href` attribute on the `<link>` tag. This is the same `href` attribute you would use when creating a link, via an `<a>` tag. While it is technically allowed to write your `<link>` tag within the `body` of the page, this would be considered a bad practice. You want the style sheet to be included in the `head` of the document so the browser will parse all of it before it starts creating elements on the page. Otherwise the browser will create all of the elements on the page using default browser styles, then read the style sheet and have to re-style the whole page. This will be noticeable to the user and gives them a poor experience. Therefore, here's another rule to always follow - __always link your style sheets in the head of the document.__

## Adding to the body of the document
The last thing I'm going to do in this article is give our page some slightly more interesting content. Hello world is always a decent starting point, just to make sure things are working, but we're past that now.

```
<body>
    <h1>My page's main headline</h1>
    <section>
        <h2>A heading for this section of the page</h2>
        <p>Some content for this section of the page. It could be anything but should be relevant. Search engines will read this content to get an idea of the purpose of the page. A link to learn more is included below.</p>
        <p>
            <a href="https://google.com/>Learn more</a>
        </p>
    </section>
    <section>
        <form name="mailing-list">
            <label for="email-input">Sign up for our mailing list</label>
            <input type="email" id="email-input" />
            <button type="submit">Submit</button>
        </form>
    </section>
</body>
```

Hopefully at this point it's fairly easy for you to look at the HTML within the `<body>` tag and have a general idea of what's going on. The primary heading for the entire page is included within an `<h1>` tag, then I'm using `<section>` tags to separate my content. In the first `section` I have a heading, some paragraph text, and a link. Notice that the heading with the first section is an `<h2>` tag. We only want __one__ `<h1>` on the page, so we use `<h2>` tags as the headings within a `<section>`. It would be a violation of _cascading headings_ rules to use an `<h3>` or lower tag as the heading of a `<section>`, so be sure to always start with `<h2>`. Sometimes developers will use an `<h3>` tag as the heading of a `<section>` because the `<h2>` text looks too big, but this is a mistake. You can easily add a `class` to the `<h2>` and style the text with CSS to look however you want. _Always focus on writing clean, semantic HTML._ Then you can style it anyway you like with CSS.

In the second section I added a small mailing list form. The form contains an email input, which is basically just a text input expecting a valid email address to be entered. This input has a `<label>` associated with it, which is great for accessibility to all users (especially those relying on a screen reader), and a submit `button`.

Certainly the complexity of our pages will continue to increase moving forward, but this is a great start. Here's what the whole file now looks like:

```
<!DOCTYPE HTML>
<html>
    <head>
        <title>My Hello World page</title>
        <meta name="description" content="Part two of the HTML introduction from Michael Pellegrini's Web Development Fundamentals course. Learning to create HTML documents." />
        <meta name="keywords" content="html, web development, web development fundamentals, learning html, html documents, html files" />
        <link rel="stylesheet" href="/path/to/styles.css" />
    </head>
    <body>
        <h1>My page's main headline</h1>
        <section>
            <h2>A heading for this section of the page</h2>
            <p>Some content for this section of the page. It could be anything but should be relevant. Search engines will read this content to get an idea of the purpose of the page. A link to learn more is included below.</p>
            <p>
                <a href="https://google.com/>Learn more</a>
            </p>
        </section>
        <section>
            <form name="mailing-list">
                <label for="email-input">Sign up for our mailing list</label>
                <input type="email" id="email-input" />
                <button type="submit">Submit</button>
            </form>
        </section>
    </body>
</html>
```

Feel free to copy this, or even better, write it all out from scratch. Edit things to your heart's content and keep refreshing your browser to see how things change. Once you're ready, move onto the third (and final) HTML Introduction article where we will be building a more fully fledged mailing list form.
