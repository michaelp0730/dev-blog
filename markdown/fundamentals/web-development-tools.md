# Web Development Tools
_Dec 29, 2020_

## Course introduction
Welcome to the first installment in my Web Development Fundamentals course! The goal of this course is to teach anyone, with any level of computer experience, how to get started building websites. Each article in this series is accompanied by a video on YouTube, and you can find the video for this article [here](https://www.youtube.com/c/MichaelPellegrini/videos). As we progress through the course, you will gain the real-world skills needed to become a web developer, and by the time you have completed these lessons, you will be well prepared for the next step in your web development journey. That next step could be entering a coding bootcamp, moving onto a college/university, or continuing on the self-taught path. Although I do have a formal education in web and application development, I firmly believe that taking the self-taught path is a perfectly viable approach in building a career as a web developer. Often, the biggest impediment in this approach is not know what to study next, but if you have someone there to curate the curriculum to you in an appropriate order, it then just comes down to your own dedication.

One thing I always tell junior developers is that when you're starting a career as a web developer or software engineer, what you're really signing up for is a life of learning. This isn't the type of career where you learn something once and then do it the same way forever. You're constantly learning new things, taking new steps, and reinventing yourself. Chances are the way you're building websites or writing software today isn't the way you will be doing those things 5 years from now. There's also a good chance that at any point in your career, when you look at code you wrote 6 months ago, you will cringe a bit. That's a good thing though, as it shows how much you're constantly learning an progressing.

For me, with a little over a decade of experience in web development, part of that next step that I'm currently focusing on is improving my skills as a teacher, writer, and presenter. I love teaching and take pride in being able to break something technical down into simple, understandable terms that anyone can understand. I'm also looking at this as my way of giving back to the web development community. Obviously there are already tons of resources out there, so I appreciate you choosing to spend your time learning with me! I'm going to do everything I can to make sure it's time well spent.

## About web development tools
To me, web development is about building experiences on the web and debugging issues in code. Just like any occupation involving building something, you're going to need different types of tools to help you get the job done. While a carpenter relies on tools like a hammer, screwdriver, and saw, the web developer relies on things like a web browser, text editor, and terminal. Luckily for you, there are free / open source versions of everything you need as a web developer, so it won't cost you anything (other than the initial cost of a computer) to get going. Certainly there are tools you can pay for as well, some of which will be discussed here, but by no means are they a requirement. The best advice I can give when it comes to selecting tools is to try out a variety of them and see which ones you like. There may be particular features in one tool that appeal to you, but you won't know until you've had a chance to compare and contrast them. I would also recommend not becoming too dogmatic about a particular tool, as new ones are frequently becoming available and it can be fun to switch things up from time to time.

## Browsers
We'll start with browsers because, regardless of your level of experience with web development, you're already going to have some level of familiarity with browsers. After all, you're reading this article online, so you must be using some type of browser to do that. I'd say the main difference between how a web developer uses a browser compared to a non-web developer is that web developers often need to inspect sites, and they do so by utilizing the browser's built-in inspector tools. One easy way to open the inspector tools is by right-clicking somewhere on the page and choosing "Inspect" or "Inspect Element" (depending on which browser you're using), but most browsers also provide keyboard shortcuts like Control+Shift+I that do the same thing.

One thing to note about browser inspector tools is that there are tons of features available. So much so that an entire course could easily be written just digging into all of them. Perhaps that would be a good thing for me to focus on in the future, but for now I would just recommend trying to get a general sense of how they are organized. There are a series of tabs across the top of the inspector with different tools available in each one. If you need to look at the HTML source code of an element, look under the Elements / Inspector tab. The Console tab is very useful in writing and debugging JavaScript. The Network tab is used to look at every element loaded over the network when the page loaded. There will be options for looking at specific files, setting breakpoints, testing a page's performance, and so much more. Often the verbiage will differ from one browser to the next but once you learn how to do something in one browser it will be trivial to learn it in another. I don't recommend spending too much time trying to learn the inspector tools inside out at this stage, but it's going to start familiarizing yourself with them. Over time your usage of these tools will get deeper.

### Chrome
As we look at individual browsers it seems appropriate to begin with Chrome, as it is the most popular browser in the world. Chrome is a Google product and it essentially set the standard for JavaScript performance on the web, leading to the rise in popularity of single-page applications a few years ago. Don't worry if you're not familiar with that term, or know nothing about JavaScript. We'll get there. For now all you need to know is that Chrome is the most commonly used browser in the world, it is actively maintained by a large team at Google, it runs really fast, and it contains all the tools you will ever need as a developer. I've worked with plenty of engineers over the years who literally only use Chrome as their browser, and that's a perfectly viable option. For me personally, I like running a few different browsers at the same time so I can test my work in various environments, but I always have Chrome open. If you don't already have Chrome installed, I would recommend heading over to the [Chrome download page](https://www.google.com/chrome/) and choosing the appropriate distribution for your computer. Whether you're running Mac, Windows, Linux, 64 bit, 32 bit, whatever, they make a Chrome distribution for your system. As with all major browsers, it's completely free to use.

### Firefox
I've always been a big fan of [Mozilla Firefox](https://www.mozilla.org/en-US/firefox/new/). It's the only major browser out there not running on Chromium (the rendering engine Google developed for Chrome), so it's a good idea to test your work there and make sure there are no issues. Firefox is pretty strict in how it parses code, so sometimes you'll write some code that runs on other browsers, but gets flagged in Firefox. Overall Firefox is really big on privacy and security so, in my opinion, it's worth trying out. For me it's one of the browsers I always have open, and I love the fact that they even make a developer-specific variant called [Firefox Developer Edition](https://www.mozilla.org/en-US/firefox/developer/) containing extra inspector tools.

### Edge
Microsoft has been developing the [Edge browser](https://www.microsoft.com/en-us/edge) for a few years now, but it's only been in the past year or so that they switched it over to the Chromium rendering engine. Chrome users will find it extremely similar, but it still has a few options making it unique. Honestly I've been impressed with Edge and have recently been using it as my default browser on Windows machines. Edge's popularity growth over the past year has been incredible. It has recently surpassed Firefox in usage and currently sits behind Chrome as the second most popular browser in the world. It runs on all platforms and is definitely worth checking out.

### Opera
[Opera](https://www.opera.com/) rounds out our list of browsers to check out. It features a built-in VPN (Virtual Private Network) for safe browsing, dark mode, and runs everywhere, including mobile. Although it's the least popular browser on this list, it still has a dedicated fanbase and can't hurt to try.

## Text editors
While browsers are certainly an area of preference an opinion amongst developers, I feel like text editors take it to the next level. There are so many options out there, most of which are free but some can be purchased, and it's not uncommon to find developers who swear by one of the other. While they all share the ability to edit text, most of them can also be customized to perform common operations easily. One of the mantras of web developers and software engineers is to be lazy, so if you find yourself performing the same task over and over, you may want to find a shortcut, and customizing your editor will generally be that shortcut. I couldn't possibly list all the text editors here, so I'm just going to pick a handful of my favorites, along with industry standards, and leave it up to you to find what works best.

### VS Code
- Developed by Microsoft and quickly becoming the most popular editor out there
- Maintained by a large team and constantly growing in features
- Includes a built-in terminal, debugger, and source control (Git) tools
- Excellent 3rd party plugin support
- Totally FREE
- Would be my choice if I had to pick only 1 text editor
- More info: [https://code.visualstudio.com/](https://code.visualstudio.com/)

### Atom
- Developed by GitHub, based on JavaScript and NodeJS
- Excellent 3rd party plugin support
- Works great with Git and GitHub
- Totally FREE
- More info: [https://atom.io/](https://atom.io/)

### Sublime Text
- Possibly the fastest, snappiest editor out there
- Revolutionized the editor world when it was first released
- Excellent 3rd party plugin support
- Not techinically free to own, but you can download it free and use it unregistered as long as you want.
- More info: [https://www.sublimetext.com/](https://www.sublimetext.com/)

### Vim
- My personal favorite of the 'classic' editors
- Runs in the terminal / command line and can be very useful for editing files when working in the terminal
- Excellent 3rd party plugin support
- Has separate insert, visual and command modes
- No mouse necessary - all navigation is done on the keyboard, allowing you to edit files very quickly once you get comfortable with the keys
- Comes installed as the default text editor on Linux systems
- Totally FREE
- More info: [https://www.vim.org/](https://www.vim.org/)

### Emacs
- Another very popular 'classic' editor
- Possibly the most configurable editor out there, but it's also the most different from everything else
- Includes built-in documentation and a tutorial for new users
- Totally FREE
- More info: [https://www.gnu.org/software/emacs/](https://www.gnu.org/software/emacs/)

## IDE's (Integrated Development Environments)
You can think of an IDE as a more fully-featured text editor. Most IDE's are meant to work with specific languages or frameworks and therefore provide more language-specific features like code completion and intellisense. They are less likely to be free than text editors (although there are still plenty of free ones out there), and they tend to be a little 'heavier' than text editors, meaning they take longer to start up and they consume more system resources. There are some text editors, like VS Code, which are so feature-rich that they are starting to straddle the line between text editor and IDE, so once again it just comes down to personal preference. Generally speaking, if you're working with languages like Java or C#, you're going to want to use an IDE rather than a text editor because of all the language-specific tools it provides you. By comparison, when I'm writing HTML, CSS, or JavaScript, I usually just use a text editor.

### Visual Studio
- Probably the most widely used IDE in the world
- Excellent for any type of development related to Microsoft technologies and languages
- Available for Windows, Mac and Linux
- Actively maintained by a large team at Microsoft - constantly growing in features
- Available in a variety of free and paid versions
- More info: [https://visualstudio.microsoft.com/](https://visualstudio.microsoft.com/)

### Eclipse
- Probably the most popular IDE for Java development, but it supports various other languages as well
- Excellent 3rd party plugin support
- Can be easily extended based on your needs
- Totally FREE
- More info: [https://www.eclipse.org/ide/](https://www.eclipse.org/ide/)

### Jetbrains
- Jetbrains is a company who makes many different IDE's for different languages and frameworks
- Their products are not free, but their quality is excellent
- Whether you're using Java, JavaScript, Python, PHP, Ruby, or many other languages, JetBrains makes an IDE for you
- More info: [https://www.jetbrains.com/](https://www.jetbrains.com/)

## Terminals
Also known as command line interfaces (or CLI's), terminals provide an handy way to navigate file systems, quickly edit files, run programs, use version control systems (like Git), and so much more. To be honest, I avoided terminals a bit in the early stages of my development career because I was so used to working in a GUI (Graphical User Interface) environment that I found the command line to be a bit intimidating. However, it didn't take long for me to see the benefits of terminals and get comfortable using them. Now hardly a day goes by without me using a terminal as part of my workflow.

One thing to note about terminals is that they are just a shell for running a particular type of software. You can think of the software running within your terminal as a miniature operating system, and it's pretty easy to switch from one to another. Some of the most common terminal applications are Bash, Git Bash, ZSH, and PowerShell. The first 3 all have very similar syntax and commands, while PowerShell is pretty much it's own thing. If you're just getting started, I'd recommend getting familiar with Bash, then you can start experimenting with others. Regardless of which one you get good at, your productivity will increase drastically compared to doing everything point-and-click style with a mouse.

Pretty much all operating systems are going to come with a terminal application already built in, but there are several 3rd party applications, all of which are free, that are worth checking out. If you're using VS Code as your text editor, then you already have a nice terminal built in (just click 'New Terminal' under the Terminal menu), but if not here are a couple other nice ones that I have used over the years.

### iTerm2
- A must-have for developers working on Macs
- Includes many more features than the default terminal
- Automatically copies anything you select to the clipboard
- More info: [https://iterm2.com/](https://iterm2.com/)

### ConEmu
- An excellent terminal for developers working on Windows machines
- Allows you to 'emulate' many different shell types, so you can easily switch from Bash to Powershell, for instance
- Automatically copies anything you select to the clipboard
- More info: [https://conemu.github.io/](https://conemu.github.io/)

## Conclusion
I'm going to wrap it up here for now. Are these all the types of tools you're ever going to use as a developer? No! There will be plenty more tools for you to become acquainted with as your learning progresses, but I don't want to overwhelm you at this stage. Most notably, there are some great tools out there for working with version control systems, but I always recommend learning those systems via the terminal first anyway, and we're not ready for that quite yet.

I realize that many of these tools aren't yet useful to you since we're not writing code yet, but it's good to start famiarizing yourself with them and absorbing some of the terminology. In our next lesson we're going to start learning HTML, meaning we will be writing code, but for now I'd recommend checking out some different browsers, downloading an editor or two, and playing around with a terminal. Don't worry if you're feeling lost at times - Rome wasn't built in a day. It's going to take time to learn all this stuff so just take it day by day and enjoy the process. See you in our next lesson!
