# CSS Architecture & Coding Guidelines

Transifex's stylesheet architecture follows the concept of Style Guide Driven Development and is mainly influenced by [OOCSS](http://oocss.org) & [ITCSS](https://www.youtube.com/watch?v=1OKZOV-iLj4). It uses the [BEMIT](http://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/) methodoly for HTML classes naming and maintains an upward trending [Specificity Graph](http://csswizardry.com/2014/10/the-specificity-graph/) without creating any spikes helping you to keep a modular, scalable and maintenable stylesheet codebase.

The used preprocessor is LESS with django-compressor for the compilation and minification of final CSS.

## Table of contents
--
2. [File Structure](#file-structure)
3. [HTML Class Naming](#html-class-naming)
4. [Preprocessor and tools used](#tools-and-libraries)
5. [LESS coding guidelines](#less-coding-guidelines)
5. [Further read](#further-read)
6. [Resources](#resources)

File Structure
--
The file structure is as much simple as possible so that everything is easily discoverable. Each developer is free to create subfolders in each of the following folders in order to group files. First level folders though cannot be changed, only subfolders.

### Config
Files with variables and other configurations.

*Note: You don't have to keep all of your variables in these files. In this folder only global variables like breakpoints, brand colors and font-sizes should be stored. If yout want to keep for example the padding of a specific object like ```input type="text"```, you should write it in the object file with a scope or namespace in order to avoid conflicts with global vars (more about this below).*
```
config
├── _typography.scss
├── _colors.scss
├── _breakpoints.scss
├── _grid.scss
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
Default styles of base elements. A Base rule is applied to an element using an element selector, a descendent selector, or a child selector, along with any pseudo-classes. **It doesn’t include any class or ID selectors**. It is defining the default styling for how that element should look in all occurrences on the page.
```
base
├── _reset.scss
├── _inputs.scss
├── _lists.scss
├── _headings.scss
├── _tables.scss
├── _links.scss
├── _paragraphs.scss
└── etc.
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

### Layout
Only layout styles. Every page is considered as UI blocks and these styles build the layout.

*Note: For example, we keep here grid classes for columns, containers and wrappers. We don't care about colors, fonts, backgrounds etc. It's like looking on the wireframe and not the mockup. Just layout without any cosmetics.*
```
layout
├── _grid.scss
├── _sidebar-left.scss
├── _container-fixed.scss
├── _container-fluid.scss
└── etc.
```

### Objects
Standalone basic reusable UI elements.
```
objects
├── _headings.scss
├── _links.scss
├── _buttons.scss
├── _inputs
|   ├── _text.scss
|   ├── _select.scss
|   ├── _checkbox.scss
|   ├── _radio-button.scss
|   └── etc.
├── _lists.scss
├── _tables.scss
└── etc.
```

### Components
Collection of objects. Chuncks of UI.
```
components
├── _modals.scss
├── _forms.scss
├── _navigation
|   ├── _primary-nav.scss
|   ├── _footer-nav.scss
|   ├── _pagination.scss
|   ├── _tabs.scss
|   └── _breadcrumbs.scss
├──  _accordion.scss
├── _single-comment.scss
└── _intro-text.scss
```

### Pages
Page specific styles.
```
pages
├── _home.scss
├── _product.scss
├── _order.scss
└── etc.
```

### Shame.scss
All hacks we are not proud of, together. Read more [here](http://csswizardry.com/2013/04/shame-css/).
```
_shame.scss
```

### Style.scss
This is where all styles are included (must have a table of contents for includes, like this [one](https://github.com/csswizardry/csswizardry.github.com/blob/master/css/csswizardry.scss)).
```
_style.scss
```

## HTML Class naming
We use the [BEMIT technique](http://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/) with custom prefixes.
#### Block
* u-name for utilies (e.g. u-display-inlineBlock)
* l-name for layouts (e.g. l-container-fluid
* o-name for objects (e.g. o-button)
* c-name for components (e.g. c-form)
* p-name for pages (e.g. p-home)

#### Element
E.g. ```<input type="text" class="c-form__input" />```

#### Modifier
E.g. ```<form class="c-form--horizontal">```

#### State, responsive suffix and js hooks
* [is|has]-stateName for states, e.g. is-open / has-dropdown
* @breakPoint - for screen specific styles e.g. u-textAlign-center@md (align center only on medium devices)
* js-name for JS specific use. We should never use classes without js prefix in scritps.

## Tools and libraries
* LESS - For nesting, variables, mixins and colors functions.
* django-compressor for compilation and minification of LESS.
* Bootstrap clone for grid.

## LESS coding guidelines
You can visit this [page](...) to see a complete refernece of how you should develop your scss files.

## Further read
* [More Transparent UI Code with Namespaces](http://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces/)
* [Contextual Styling: UI Components, Nesting, and Implementation Detail](http://csswizardry.com/2015/06/contextual-styling-ui-components-nesting-and-implementation-detail/)
* [The specificity graph](http://csswizardry.com/2014/10/the-specificity-graph/)
* [Hacks for dealing with specificity](http://csswizardry.com/2014/07/hacks-for-dealing-with-specificity/)
