# Yieldmo CSS Style Guide

*Principles of writing consistent, idiomatic CSS*

The following document outlines a reasonable style guide for CSS development.
These guidelines strongly encourage the use of existing, common, sensible
patterns. They should be adapted as needed to create your own style guide.

If you want to dive deeper, there is a more detailed code guide **[HERE ☞](http://mdo.github.io/code-guide)**


## Table of contents

1. [General principles](#general-principles)
2. [Whitespace](#whitespace)
3. [Comments](#comments)
4. [Format](#format)
5. [Components](#components)
    - [Modifiers](#modifiers)
    - [State](#state)
6. [Practical example](#example)


<a name="general-principles"></a>
## 1. General principles

> "Part of being a good steward to a successful project is realizing that
> writing code for yourself is a Bad Idea™. If thousands of people are using
> your code, then write your code for maximum clarity, not your personal
> preference of how to get clever within the spec." - Idan Gazit

* Don't try to prematurely optimize your code; keep it readable and
  understandable.
* All code in any code-base should look like a single person typed it, even
  when many people are contributing to it.
* Strictly enforce the agreed-upon style, which is this one.
* If in doubt when deciding upon a style use existing, common patterns.


<a name="whitespace"></a>
## 2. Whitespace

Only one style should exist across the entire source of your code-base. Always
be consistent in your use of whitespace. Use whitespace to improve
readability.

* _Never_ mix spaces and tabs for indentation.
* Choose between soft indents (spaces) or real tabs. Stick to your choice
  without fail. (Preference: spaces)
* If using spaces, choose the number of characters used per indentation level.
  (Preference: 2 spaces)

Tip: configure your editor to "show invisibles" or to automatically remove
end-of-line whitespace.

Tip: use an [EditorConfig](http://editorconfig.org/) file (or equivalent) to
help maintain the basic whitespace conventions that have been agreed for your
code-base.


<a name="comments"></a>
## 3. Comments

Well commented code is extremely important. Take time to describe components,
how they work, their limitations, and the way they are constructed. Don't leave
others in the team guessing as to the purpose of uncommon or non-obvious
code.

Comment style should be simple and consistent within a single code base.

* Place comments on a new line above their subject.
* Keep line-length to a sensible maximum, e.g., 80 columns.
* Make liberal use of comments to break CSS code into discrete sections.
* Use "sentence case" comments and consistent text indentation.

Tip: configure your editor to provide you with shortcuts to output agreed-upon
comment patterns.

Example:

```css
/* ==========================================================================
   Section comment block
   ========================================================================== */

/* Sub-section comment block
   ========================================================================== */

/**
 * Short description using Doxygen-style comment format
 *
 * The first sentence of the long description starts here and continues on this
 * line for a while finally concluding here at the end of this paragraph.
 *
 * The long description is ideal for more detailed explanations and
 * documentation. It can include example HTML, URLs, or any other information
 * that is deemed necessary or useful.
 *
 * @tag This is a tag named 'tag'
 *
 * TODO: This is a todo statement that describes an atomic task to be completed
 *   at a later date. It wraps after 80 characters and following lines are
 *   indented by 2 spaces.
 */

/* Basic comment */

**Note: Do not append CSS at the end of the file, always try to find the proper section where that CSS belongs to.**


```


<a name="format"></a>
## 4. Format

The chosen code format must ensure that code is: easy to read; easy to clearly
comment; minimizes the chance of accidentally introducing errors; and results
in useful diffs and blames.

* Use one discrete selector per line in multi-selector rulesets.
* Include a single space before the opening brace of a ruleset.
* Include one declaration per line in a declaration block.
* Use one level of indentation for each declaration.
* Include a single space after the colon of a declaration.
* Use lowercase and shorthand hex values, e.g., `#aaa`.
* Use single or double quotes consistently. Preference is for double quotes,
  e.g., `content: ""`.
* Quote attribute values in selectors, e.g., `input[type="checkbox"]`.
* _Never_ specify units for zero-values, e.g., `margin: 0`.
* Include a space after each comma in comma-separated property or function
  values.
* Include a semi-colon at the end of the last declaration in a declaration
  block.
* Place the closing brace of a ruleset in the same column as the first
  character of the ruleset.
* Separate each ruleset by a blank line.

```css
.selector-1,
.selector-2,
.selector-3[type="text"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  display: block;
  font-family: helvetica, arial, sans-serif;
  color: #333;
  background: #fff;
  background: linear-gradient(#fff, rgba(0, 0, 0, 0.8));
}

.selector-a,
.selector-b {
  padding: 10px;
}
```

#### Declaration order

If declarations are to be consistently ordered, it should be in accordance with
a single, simple principle.

Smaller teams may prefer to cluster related properties (e.g. positioning and
box-model) together.

This is optional for small amount of declarations, but for large amount of declarations. But should strive to avoid such situation.

```css
.selector {
  /* Positioning */
  position: absolute;
  z-index: 10;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;

  /* Display & Box Model */
  display: inline-block;
  overflow: hidden;
  box-sizing: border-box;
  width: 100px;
  height: 100px;
  padding: 10px;
  border: 10px solid #333;
  margin: 10px;

  /* Other */
  background: #000;
  color: #fff;
  font-family: sans-serif;
  font-size: 16px;
  text-align: right;
}
```

Larger teams may prefer the simplicity and ease-of-maintenance that comes with
alphabetical ordering.

#### Exceptions and slight deviations

Large blocks of single declarations can use a slightly different, single-line
format. In this case, a space should be included after the opening brace and
before the closing brace.

```css
.selector-1 { width: 10%; }
.selector-2 { width: 20%; }
.selector-3 { width: 30%; }
```

Long, comma-separated property values - such as collections of gradients or
shadows - can be arranged across multiple lines in an effort to improve
readability and produce more useful diffs. There are various formats that could
be used; one example is shown below.

```css
.selector {
  background-image:
    linear-gradient(#fff, #ccc),
    linear-gradient(#f3c, #4ec);
  box-shadow:
    1px 1px 1px #000,
    2px 2px 1px 1px #ccc inset;
}
```

### Preprocessors: additional format considerations

Different CSS preprocessors have different features, functionality, and syntax.
Your conventions should be extended to accommodate the particularities of any
preprocessor in use. The following guidelines are in reference to Sass.

* Limit nesting to 1 level deep. Reassess any nesting more than 2 levels deep.
  This prevents overly-specific CSS selectors.
* Avoid large numbers of nested rules. Break them up when readability starts to
  be affected. Preference to avoid nesting that spreads over more than 20
  lines.
* Always place `@extend` statements on the first lines of a declaration
  block.
* Where possible, group `@include` statements at the top of a declaration
  block, after any `@extend` statements.
* Consider prefixing custom functions with `x-` or another namespace. This
  helps to avoid any potential to confuse your function with a native CSS
  function, or to clash with functions from libraries.

```scss
.selector-1 {
  @extend .other-rule;
  @include clearfix();
  @include box-sizing(border-box);
  width: x-grid-unit(1);
  // other declarations
}
```


<a name="components"></a>
## 5. Components

> Use the `.component-descendant-descendant` pattern for components.

Components help encapsulate your CSS and prevent run-away cascading styles and keep things readable and maintainable. Central to componentizing CSS is namespacing. Instead of using descendant selectors, like `.header img { … }`, you’ll create a new hyphen-separated class for the descendant element, like `.header-image { … }`.

Here’s an example with descendant selectors:

``` LESS
.global-header {
  background: hsl(202, 70%, 90%);
  color: hsl(202, 0%, 100%);
  height: 40px;
  padding: 10px;
}

.global-header .logo {
  float: left;
}

.global-header .logo img {
  height: 40px;
  width: 200px;
}

.global-header .nav {
  float: right;
}

.global-header .nav .item {
  background: hsl(0, 0%, 90%);
  border-radius: 3px;
  display: block;
  float: left; 
  -webkit-transition: background 100ms;
  transition: background 100ms;
}

.global-header .nav .item:hover {
  background: hsl(0, 0%, 80%);
}
```

And here’s the same example with namespacing:

``` LESS
.global-header {
  background: hsl(202, 70%, 90%);
  color: hsl(202, 0%, 100%);
  height: 40px;
  padding: 10px;
}

.global-header-logo {
  float: left;
}

.global-header-logo-image {
  background: url("logo.png");
  height: 40px;
  width: 200px;
}

.global-header-nav {
  float: right;
}

.global-header-nav-item {
  background: hsl(0, 0%, 90%);
  border-radius: 3px;
  display: block;
  float: left; 
  -webkit-transition: background 100ms;
  transition: background 100ms;
}

.global-header-nav-item:hover {
  background: hsl(0, 0%, 80%);
}
```

Namespacing keeps specificity low, which leads to fewer inline styles, !important declarations, and makes things more maintainable over time.

Make sure **every selector is a class**. There should be no reason to use id or element selectors. No underscores or camelCase. Everything should be lowercase.

Components make it easy to see relationships between classes. You just need to look at the name. You should still **indent descendant classes** so their relationship is even more obvious and it’s easier to scan the file. Stateful things like `:hover` should be on the same level.

This necessitates the use of single class with the exception of modifiers.


### Modifiers

> Use the `.component-descendant.mod-modifier` pattern for modifier classes.

Let’s say you want to use a component, but style it in a special way. We run into a problem with namespacing because the class needs to be a sibling, not a child. Naming the selector `.component-descendant-modifier` means the modifier could be easily confused for a descendant. To denote that a class is a modifier, use a `.mod-modifier` class.

For example, we want to specially style our sign up button among the header buttons. We’ll add `.global-header-nav-item.mod-sign-up`, which looks like this:

``` HTML
<!-- HTML -->

<a class="global-header-nav-item mod-sign-up">
  Sign Up
</a>
```

``` LESS
// global-header.less

.global-header-nav-item {
  background: hsl(0, 0%, 90%);
  border-radius: 3px;
  display: block;
  float: left; 
  -webkit-transition: background 100ms;
  transition: background 100ms;
}

.global-header-nav-item.mod-sign-up {
  background: hsl(120, 70%, 40%);
  color: #fff;
}
```

We inherit all the `global-header-nav-item` styles and modify it with `.mod-sign-up`. This breaks our namespace convention and increases the specificity, but that’s exactly what we want. This means we don’t have to worry about the order in the file. For the sake of clarity, put it after the part of the component it modifies. Put modifiers on the same indention level as the selector it’s modifying.

**You should never write a bare `.mod-` class**. It should always be tied to a part of a component. `.header-button.mod-sign-up { background: green; }` is good, but `.mod-sign-up { background: green; }` is bad. We could be using `.mod-sign-up` in another component and we wouldn’t want to override it.

You’ll often want to overwrite a descendant of the modified selector. Do that like so:

``` LESS
.global-header-nav-item.mod-sign-up {
  background: hsl(120, 70%, 40%);
  color: #fff;

  .global-header-nav-item-text {
    font-weight: bold;
  }
}
```

Generally, we try and avoid nesting because it results in runaway rules that are impossible to read. This is an exception.

Put modifiers at the bottom of the component file, after the original components.


### State

> Use the `.component-descendant.is-state` pattern for state. Manipulate `.is-` classes in JavaScript (but not presentation classes).

State classes show that something is enabled, expanded, hidden, or what have you. For these classes, we’ll use a new `.component-descendant.is-state` pattern.

Example: Let’s say that when you click the logo, it goes back to your home page. But because it’s a single page app, it needs to load things. You want your logo to do a loading animation. This should sound familiar to Trello users.

You’ll use a `.global-header-logo-image.is-loading` rule. That looks like this:

``` LESS
.global-header-logo-image {
  background: url("logo.png");
  height: 40px;
  width: 200px;
}

.global-header-logo-image.is-loading {
  background: url("logo-loading.gif");
}
```

JavaScript defines the state of the application, so we’ll use JavaScript to toggle the state classes. The `.component.is-state` pattern decouples state and presentation concerns so we can add state classes without needing to know about the presentation class. A developer can just say to the designer, “This element has an .is-loading class. You can style it however you want.”. If the state class were something like `global-header-logo-image--is-loading`, the developer would have to know a lot about the presentation and it would be harder to update in the future.

Like modifiers, it’s possible that the same state class will be used on different components. You don’t want to override or inherit styles, so it’s important that **every component define its own styles for the state**. They should never be defined on their own. Meaning you should see `.global-header.is-hidden { display: none; }`, but never `.is-hidden { display: none; }` (as tempting as that may be). `.is-hidden` could conceivably mean different things in different components.

We also don’t indent state classes. Again, that’s only for descendants. State classes should appear at the bottom of the file, after the original components and modifiers.


<a name="example"></a>
## 6. Practical example

An example of various conventions.

```css
/* ==========================================================================
   Grid layout
   ========================================================================== */

/**
 * Column layout with horizontal scroll.
 *
 * This creates a single row of full-height, non-wrapping columns that can
 * be browsed horizontally within their parent.
 *
 * Example HTML:
 *
 * <div class="grid">
 *   <div class="cell cell-3"></div>
 *   <div class="cell cell-3"></div>
 *   <div class="cell cell-3"></div>
 * </div>
 */

/**
 * Grid container
 *
 * Must only contain `.cell` children.
 *
 * 1. Remove inter-cell whitespace
 * 2. Prevent inline-block cells wrapping
 */

.grid {
  height: 100%;
  font-size: 0; /* 1 */
  white-space: nowrap; /* 2 */
}

/**
 * Grid cells
 *
 * No explicit width by default. Extend with `.cell-n` classes.
 *
 * 1. Set the inter-cell spacing
 * 2. Reset white-space inherited from `.grid`
 * 3. Reset font-size inherited from `.grid`
 */

.cell {
  position: relative;
  display: inline-block;
  overflow: hidden;
  box-sizing: border-box;
  height: 100%;
  padding: 0 10px; /* 1 */
  border: 2px solid #333;
  vertical-align: top;
  white-space: normal; /* 2 */
  font-size: 16px; /* 3 */
}

/* Cell states */

.cell.is-animating {
  background-color: #fffdec;
}

/* Cell dimensions
   ========================================================================== */

.cell-1 { width: 10%; }
.cell-2 { width: 20%; }
.cell-3 { width: 30%; }
.cell-4 { width: 40%; }
.cell-5 { width: 50%; }

/* Cell modifiers
   ========================================================================== */

.cell--detail,
.cell--important {
  border-width: 4px;
}
```



<a name="license"></a>
## License

_Principles of writing consistent, idiomatic CSS_ by Nicolas Gallagher is
licensed under the [Creative Commons Attribution 3.0 Unported
License](http://creativecommons.org/licenses/by/3.0/). This applies to all
documents and translations in this repository.

Based on a work at
[github.com/necolas/idiomatic-css](https://github.com/necolas/idiomatic-css).

**[⬆ back to top](#table-of-contents)**