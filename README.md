# SASS Workshop
*Let's get sassy*

## Base instructions
* Fork this repo and clone it to a new Cloud9 project
* Each exercise should be in a separate branch, branched off `master`
* Create a pull request for each exercise

## Exercise 1: styling the blog
### Discovery
* *Take your time* to do this exercise! It's an occasion to discover new CSS/CSS3 features, as well as
a new coding style for stylesheets, called [BEM](https://css-tricks.com/bem-101/)
* Read [this article about BEM](https://css-tricks.com/bem-101/) if you haven't already.
* Look at the file `blog/index.html` and notice how almost every element has a hierarchical class name.
* BEM stands for Block, Element, Modifier. It's a way to look at the parts of a web page or web
application as components, or "Blocks". A block is a logical unit of your page, like the main header,
or an article, or an author information element (contains an image and a block of text about the author)
* In BEM, almost every element gets its own class name. This is the 101 of the 101:
  1. You start by finding a logical block of code, and giving it a unique class name.
  2. Then, all the elements inside that block will get a class name that starts the same way,
  followed by `__`, followed by the name of the Element.
  3. If an element needs to look a bit different, we will add a second class name, same as the element's
  class name but followed by a modifier.
* For example, in `blog/index.html`, we have `article` as a **Block**. We consider it to be a main component of the page.
* Under article, we have many **Elements**: the featured image has class `article__featured-image` and the paragraphs have `article__paragraph`.
* One special paragraph, the first one, has a **Modifier**: it has two classes, both `article__paragraph` and `article__paragraph--first`
* One may ask the valid question: *"Why don't we just use `:first-child` here?"* and they would be right. In BEM, we try to not rely on an element's nature or placement, but add class names to get things done.
While it may seem repetitive and overboard, most of the time the HTML will be generated by a dynamic process like a blog engine.
* One of the advantages of BEM is that since class names are more thought out, it becomes pretty much impossible to duplicate a class name.
* Also, as you'll see while doing your exercise, it creates a flat CSS structure which relies on well-defined components rather than clumsy nesting.

### Doing
* Keeping the HTML code the same, write some code inside of `blog/scss/main.scss` to style the blog **as you wish**.
* Take the time to create something beautiful out of this boring HTML page! Use CSS3 functionality where appropriate, and don't hesitate to make the page your own.
* To use the BEM classes but keep the nesting, you will need to do something like this:
```scss
.article {
  &__paragraph {
    // ...
    
    &--first {
      // ...
    }
  }
}
```
* **NOTICE**: Even though you have nesting, since you're mostly using `&` followed by `__`, your CSS will be flat.

## Exercise 2: mixins!
* You'll be doing this exercise in the `mixins` directory
* Create a file in the `mixins/scss` directory called `_lib.scss`. The `_` means that this file will not be compiled by SASS, but can be `import`ed.
* In `main.scss`, import the library file by writing `@import "lib";` on top of the file.
* In `_lib.scss`, create the following mixins:
  1. Create a mixin called `rounded` that will make an element round, with a border and a drop-shadow. This mixin should take a border color, shadow color and border width as parameters, and create the rounded element like this. All parameters should be optional, and you can choose whichever defaults you like.
  2. Create a second mixin called `rounded-corner-box` that will make an element have rounded corners. The mixin should take a border radius, border color, border width and background color as parameters. It should give that border to the element it's mixed in with.
* Then, by looking at `index.html`, style elements by using your mixins in `main.scss`:
  1. Style the main title by giving it rounded corners of 8 pixels, no border, and a background color of pink.
  2. Style the first kitty picture by making it rounded, with a 6-pixel blue-ish border and a pink-ish drop shadow. *Experiment with `hsl`* to find some nice colors!
  3. Style the "featured" paragraph by giving it rounded corners, a 4-pixel black border, and a nice background color of your choice.
  4. Style the author image by making it rounded, no visible border, and a semi-transparent black shadow.

## Exercise 3: The "Holy Grail" Layout
* Note that this exercise is not SASS-specific. You can and should use SASS to complete it as it's more maintainable!
* Go through the [Flexbox in 5 tutorial](http://flexboxin5.com/)
* Read about the [Holy Grail Layout](https://en.wikipedia.org/wiki/Holy_Grail_(web_design))
* Based on your newly acquired knowledge, you will create the holy grail layout using flexbox
* Look at `flexbox/index.html` for the structure, and create the holy grail layout without changing the HTML.
* The header should be on top, footer on the bottom. Navigation on the left, ads on the right, and content in the middle.
* If you are having trouble, you can inspire yourself from [solved by flexbox's solution](https://philipwalton.github.io/solved-by-flexbox/demos/holy-grail/)

## Exercise 4: your own page!
* For this exercise there is no pull request. Please point us to the repository of your page on slack
* In this exercise, you will convert your personal page that you have been working on to use SASS
* This exercise is open-ended. Take some time to work on your personal page using your newly found knowledge, plus
reading up and getting inspired about CSS features.