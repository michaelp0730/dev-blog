# HTML Introduction - Part 3
### Creating HTML forms
_Jan 10, 2021_

Welcome to the 3rd and final installment of my HTML Introduction series. In the first article we learned about HTML tags and attributes, then in the next article we started creating entire HTML documents from scratch. In this article, the focus will be on creating HTML forms. The reason I chose to focus on forms is that, to me, web development very frequently follows one of the following two workflows:

- Consuming data from somewhere (usually a database), filtering it, and presenting it to the user
- Consuming data from the user, validating it, and sending it somewhere (usually a database)

It's this 2nd scenario, where you're gathering data from the user, that we will focus on today. Generally speaking, if you're gathering data from a user, the way you're doing this is through a form. Certainly there are other scenarios where data is being collected about the user behind the scenes (like via cookies), but we're going to look at scenarios where the user is voluntarily entering their information on a web page.

## A basic HTML form

In the last article, the HTML document we created included a simple mailing list form, so in this article we will expand upon that form by transforming it into something a little closer to what you would see in the real world. For the sake of simplicity, the rest of the HTML document will be ignored. Here's what that form looked like in the last article:

```
<form name="mailing-list">
    <label for="email-input">Sign up for our mailing list</label>
    <input type="email" id="email-input" />
    <button type="submit">Submit</button>
</form>
```

Let's quickly recap what's going on here:

- The form includes a `name` attribute. In this case the name of the form is "mailing-list", but it can be anything you wish.
- The form includes an `input` tag with attribute `type="email"`, meaning it expects a valid email address to be entered here.
- The email input also includes an `id` attribute. The value of this `id` attribute is "email-input", but it could be anything you want.
- Above the email input is a `<label>` element, including `for="email-input"`, indicating that this label corresponds to the email input directly below.
- While labeling your inputs is not strictly required, it is highly recommended. Not only is the label visible on screen, but it gets read by screen readers, meaning it is important in making your website _accessible_ to all users.
- The form includes a submit button. We haven't yet added any details to the form regarding what should happen when the form submits, but we will cover that next.

## Adding to our form

The first thing we're going to add to the form is information about what should happen when it is submitted. Only the opening form tag needs to be modified:

```
<form name="mailing-list" method="POST" action="/form/submission/handler/">
```

### Form methods

The `method` attribute of the `form` element tells the browser how to send form data to a web server. There are 2 potential values for the `method` attribute:

- GET
- POST

#### The GET method

When using `method="GET"`, after the form is submitted all form values entered by the user will be added to the URL via something called a query string. Here's an example of what that would look like:

```
https://website.com/?first-name=John&last-name=Doe&email=johndoe@something.com
```

As you can see, the query string consists of key-value pairs. The query string begins with a `?`, then each additional key-value pair is separated by a `&`. Each key in these key-value pairs would be the `id` or `name` of an element in the form, and the value would be whatever the user entered for that element of the form.

The GET method is not as widely used as POST, mainly because it's not secure. All the data entered by the user is added to the URL, meaning you would never want to do this when collecting sensitive data from the user. There is also a length limit in terms of how many characters can be added to the URL, which is 2048.

#### The POST method

I used `method="POST"` in my form because it's much more common to see in the real world. "Posting" a form means you're sending the data entered by the user _somewhere_. Generally that _somewhere_ is going to be a database, but you can't send data directly from the form to the database; you would need to send it to your web server to be processed and sent to the database. This is where the form's `action` attribute comes in, which we will cover shortly.

One major difference between `method="POST"` and `method="GET"` is that, when posting a form, none of the information entered by the user will end up in the URL. This is a much more secure way of submitting a form and can therefore be used when accepting sensitive information from the user.

### Form Actions

The form `action` attribute is required when `method="POST"` because it tells the form where all the data entered by the user should be sent. The value of the `action` attribute will be a file or location on the server designated for handling the form submission. In my example I used a location, like this: `action="/form/submission/handler/"`. However, you could also specify a file name, like `action="process.php"`, depending on which server-side programming language you're using.

We won't get into the details on processing a form on the server because it's beyond the scope of this article, so here's all you need to know for now:

- Data entered into the form by the user will usually be validated on the client-side by JavaScript before being sent to the server. If errors are found the form will not be submitted.
- Assuming no errors are found during client-side validation, the form data is sent to a server.
- Usually this data will be encrypted before being sent. This is done via SSL or TLS certificate and is very important in terms of web security.
- The server receives the form data and, assuming it was encrypted, the server will decrypt the data.
- Often more form validation will be done by the server. This is called server-side validation.
- The data is now entered into a database.

### More form inputs

Now that we've covered what should happen when our form is submitted, let's add more inputs to the form. Here's a more complete looking mailing list form:

```
<form name="mailing-list" method="POST" action="/form/submission/handler/">
    <label for="first-name">First name</label>
    <input type="text" id="first-name" />

    <label for="last-name">Last name</label>
    <input type="text" id="last-name" />

    <label for="email">Email address</label>
    <input type="email" id="email" />

    <label for="reenter-email">Re-enter your email address</label>
    <input type="email" id="reenter-email" />

    <p>What are you interested in?</p>
    <label for="history">History</label>
    <input type="checkbox" id="history" value="history" />
    <label for="geography">Geography</label>
    <input type="checkbox" id="geography" value="geography" />
    <label for="science">Science</label>
    <input type="checkbox" id="science" value="science" />

    <p>Gender</p>
    <label for="female">Female</label>
    <input type="radio" id="female" name="gender" value="female" />
    <label for="male">Male</label>
    <input type="radio" id="male" name="gender" value="male" />
    <label for="undisclosed">Undisclosed</label>
    <input type="radio" id="undisclosed" name="gender" value="undisclosed" />

    <label for="continent">Where do you live?</label>
    <select id="continent">
        <option value="Africa">Africa</option>
        <option value="Asia">Asia</option>
        <option value="Europe">Europe</option>
        <option value="North America">North America</option>
        <option value="South America">South America</option>
    </select>

    <button type="submit">Submit</button>
</form>
```

Now our form looks a lot more like what you would find on a real website. Most of it should make sense to you, but I tried to include a variety of the most common input types. There are a couple notable input types not included in this form, but I will cover them at the end. First let's look at what's already in the form, and please note that each input type (except the submit button) has a corresponding `label` element.

#### Text input

Text inputs are probably the most common type of input you will find on forms. In this case we are using them when asking for the user's first and last names. Text inputs should be used for short strings of text, like names. Don't use them if you need a whole sentence or paragraph of text (we'll cover that later), but do use them when you need a short string of text, but you don't have a pre-defined list of what the values could be. Again, names are a perfect example.

#### Email input

Visually speaking, the `email` input looks just like a `text` input, and technically speaking you could use a `text` input when asking for an email address, but the `email` input is better because it contains built in validation rules ensuring the value entered conforms to a standard email address. If you use a `text `input, you will have to write your own validation rules, which is a hassel. It's much easier just to use the `email` input type.

Also notice that a second `email` input is included, asking the user to re-enter their address. This is meant for form validation, helping to ensure that the correct address was entered. During the client-side validation step, you would check the values of both `email` inputs to make sure they are equal. If not, an error would be printed on screen and the form would not submit.

#### Checkbox input

Checkboxes are a useful (and common) input type when you have a pre-defined list of options to present to the user, and you want to __allow them to select multiple options__. They don't have to select multiple options, or any in some cases, but the point is that you're allowing them to make multiple selections if they wish. Notice that each `checkbox` input has it's own `label` element. Also notice that each `checkbox` input contains a `value` attribute. The value of this attribute will be included in the form data when the form is posted. Technically you can give each `checkbox` input any value you want, but try to make sure it's clearly associated with the label, so there can be no question about what the user was selecting.

#### Radio input

Radio buttons are another very common type of form input. They are similar to checkboxes in the sense that you are presenting a list of pre-defined options to the user, but in this case only __one selection can be made__. The same rule about the `value` attribute we just discussed with `checkbox` inputs also applies to `radio` inputs.

One other thing to note about radio buttons is that you need a way of grouping them together. This is done via the `name` attribute. In our example we're using `name="gender"` on these radio buttons, but you could use any `name` value you want. It's just important that each radio button in your group has the same `name` attribute, and a different `value` attribute, that way you can tell what they selected when posting the form to the server.

If you wanted to have multiple separate groups of radio buttons in the form, it would be no problem as long as each group of inputs shares a common `name`.

#### Select input

Select inputs, also commonly referred to as drop down menus, are another common form input. Like checkboxes and radio buttons, they are used to allow the user to select from a pre-defined list of options, and like radio buttons, __only one selection can be made__. Technically speaking, any time you have a need for radio buttons, you could replace them with a select menu, or vice versa. Generally the decision on which to use will come down to how it looks on screen. If you had a long list to select from (like every country in the world), radio buttons probably wouldn't be the best choice because they would take up so much space on screen.

Notice that the `select` input consists of a `<select>` tag with a bunch of `<option>` tags nested inside of it. You don't need to provide a `label` for each `<option>`, just for the entire `<select>` element. It's important that each `<option>` tag includes a `value` attribute because that `value` will be included in the form submission.

#### Submit button
Without a submit button, the user wouldn't be able to submit the form, so this input is very important. In our example I chose to write it as `<button type="submit">Submit</button>` but it would also be valid to write it as `<input type="submit" id="submit" value="Submit" />`. Using the `input` tag is how we did it back in the day, but `button` element seems more common to me these days. Either is fine though.

### Other common form inputs

I don't want to cover every single type of form input here because it's too much information and many of them are not that commonly used. If you're interested, [here is a handy article](https://www.w3schools.com/html/html_form_input_types.asp) for you to dive deeper on that topic.

These are some of the other most common inputs that I think you should be aware of for now:

- `date` - Allows the user to enter a date
- `hidden` - This input will be invisible to the user but will be included when the form is submitted to the server
- `number` - Provides the user with a number picker
- `password` - The text entered by the user will show up as bullet points, keeping their password secure and invisible
- `reset` - Clicking this button will reset the form by clearing out all data entered by the user
- `tel` - An input formatted specifically for telephone numbers
- `textarea` - Technically this is not an `input` because it has a tag of it's own: `<textarea>`. You would use this tag when you need longer strings of text, like a sentence or paragraph.

## Conclusion

We've gone over a lot of concepts related to HTML forms in this article. Hopefully it all makes sense, but don't worry if not. It's totally fine if you need to come back to this, either as a quick resource to look something up, or to re-read the entire article. Also feel free to watch my video on this topic, if you prefer that form of learning over reading it to yourself.

As I mentioned at the beginning, forms are a really important aspect of web development because they are the primary tool for collecting data from the user. I encourage you to recreate the form from this article in your own HTML document. It won't look very pretty because only the default browser styles are being applied, but we're not worried about pretty right now. We're worried about getting the right elements on screen by writing clean, semantic HTML. We'll start learning how to make things pretty in the next article, which will begin our introduction to CSS.

You also don't need to worry about posting your form, although feel free to try using `method="GET"` as an exercise. When you submit the form you will see all the data appended to the URL via query string. I hope you found this article, as well as this series of HTML introductory articles, helpful and informative. I look forward to getting started with CSS next!
