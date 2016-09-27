# Transifex Marketing CSS UI toolkit

In this repository you will find all of the styles that are used in Transifex marketing and documentation websites.

## Architecture 
Our architecture follows the concept of Style Guide Driven Development and is based on [ITCSS](http://www.creativebloq.com/web-design/manage-large-css-projects-itcss-101517528). It uses the [BEMIT](http://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/) technique for HTML classes naming and focuses on keeping a modular, scalable and maintenable stylesheets codebase.

Files are structured as much simple as possible so that everything is easily discoverable. Each developer is free to create subfolders in each of the following folders in order to group files. First level folders though cannot be changed, only subfolders.

### Config
Files with global settings.

*Note: You don't have to keep all of your variables in these files. In this folder we keep only variables like breakpoints and brand colors that need to be accessed from everywhere. If you want to keep for example the padding of a specific object, you should write it in the object file with a scope or namespace in order to avoid conflicts with global variables.*
```
config
├── _typography.scss
├── _colors.scss
└── etc.
```

### Helpers
Files with mixins & functions.
```
helpers
├── _pxtorem.scss
├── _imagepath.scss
└── etc.
```

### Base
Default styles of base elements. A Base rule is applied to an element using an element selector, a descendent selector, or a child selector, along with any pseudo-classes. **It doesn’t include any class or ID selectors**.
```
base
├── _reset.scss
├── _typography.scss
└── etc.
```

### Objects
Class-based selectors which define undecorated design patterns like grid or media object.
```
objects
├── _headings.scss
├── _inline-list.scss
├── _tables.scss
├── _grid.scss
├── _container.scss
└── etc.
```

### Components
Class-based selectors that contain cosmetic CSS.
```
components
├── _modals.scss
├── _form.scss
├── _primary-nav.scss
├── _footer-nav.scss
├── _tabs.scss
├── _breadcrumb.scss
├── _accordion.scss
└── _hero.scss
```

### Utilities
These are single-purpose, highly reusable classes that do one thing extremely well. We have utilities for things like margins, paddings, text alignment, font sizing, display properties, positioning properties, and more.
```
utilities
├── _typography.scss
├── _align.scss
├── _display.scss
└── etc.
```

### Scope
These classes signify that a class creates a new styling context or Scope. They are used when we want to apply styles to auto-generated markup where we do not have control of HTML classes (eg. WYIWYG editors)
```
scopes
├── _blog-content.scss
└── etc.
```

### Shame.scss
All hacks we are not proud of, together. Read more [here](http://csswizardry.com/2013/04/shame-css/).
```
_shame.scss
```

### Manifest files
Files that include only ```@import``` statements. These are the main files that will be compiled to actual CSS and imported into our project.
```

├── _base.scss
├── _signup.scss
├── _main.scss
└── etc.
```

### HTML Class naming

As menitoned before, we use the [BEMIT technique](http://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/) with custom prefixes.

**Block**
* o-name for objects (e.g. o-button)
* c-name for components (e.g. c-form)
* u-name for utilies (e.g. u-display-inlineBlock)
* s-name for scopes (e.g. s-home)

**Element**
E.g. ```<input type="text" class="c-form__input" />```

**Modifier**
E.g. ```<form class="c-form--horizontal">```

### Naming conventions & guidelines
* [is|has]-stateName for states, e.g. is-open / has-dropdown
* @breakPoint - for screen specific styles e.g. u-textAlign-center@md (align center only on medium devices)
* js-name for JS specific use. We never use classes without js prefix in our scritps.

### Further read
* [More Transparent UI Code with Namespaces](http://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces/)
* [Contextual Styling: UI Components, Nesting, and Implementation Detail](http://csswizardry.com/2015/06/contextual-styling-ui-components-nesting-and-implementation-detail/)
* [The specificity graph](http://csswizardry.com/2014/10/the-specificity-graph/)
* [Hacks for dealing with specificity](http://csswizardry.com/2014/07/hacks-for-dealing-with-specificity/)
* [What no one told you about z-index](http://philipwalton.com/articles/what-no-one-told-you-about-z-index/)
