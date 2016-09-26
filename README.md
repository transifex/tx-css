# Transifex Marketing CSS UI toolkit

In this repository you will find all of the styles that are used in Transifex marketing and documentation websites.

Our architecture follows the concept of Style Guide Driven Development and is influenced by [ITCSS](http://www.creativebloq.com/web-design/manage-large-css-projects-itcss-101517528). It uses the [BEMIT](http://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/) technique for HTML classes naming and focuses on keeping a modular, scalable and maintenable stylesheet codebase.

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
