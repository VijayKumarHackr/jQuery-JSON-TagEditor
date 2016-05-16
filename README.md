jQuery JSON Tag Editor
======================

*jQuery JSON Tag Editor* is a fork of [jQuery-tagEditor](https://goodies.pixabay.com/jquery/tag-editor/demo.html), originally developed by Simon Steinberger for
[Pixabay.com](https://pixabay.com) and licensed under the [MIT license](https://opensource.org/licenses/MIT). This fork maintains the same license.

*jQuery JSON Tag Editor* adds a separation between the visual representation of a tag and the tag itself. Tags are plain JavaScript objects with a `tagValue` 
that is its visual representation in the tag editor. `tagValue` plus any other properties that the tag object may have are all stored as 
[data attributes](https://developer.mozilla.org/en/docs/Web/Guide/HTML/Using_data_attributes) in each `<div class="tag-editor-tag">` element.

So, using the `addTag` public method, this:
```
$('#id').jsonTagEditor('addTag', '{"tagValue": "Car", "tagType": "string", "category": "vehicle"}')
```

Produces the markup below:
```
<div class="tag-editor-tag" data-tag-value="Car" data-tag-type="string" data-category="vehicle">Car</div>
```

If a string is provided as an argument then an object with only the `tagValue` property is created. This is the case when tags are manually typed into the editor. 

Features added:
---------------
* Tags are complex objects: what you see in the editor is the property `tagValue`, but you can add arbitrary data to your tags
* Tag object properties are stored as data attributes of their corresponding `<div>` element
* A new option `maxTagLength` can trim and ellipsify tags while keeping the original value in `data-tag-value`

Features removed:
-----------------
* Auto-grow width of `<input>` editors
* Support for cut: the original feature was Window-specific but buggy as tags weren’t put in the clipboard 
* `removeDuplicates`: as tags aren’t strings it was the simplest way to deal with this issue
* The `delimiter` is hard-coded to `\t` and `\n` 

---

What follows are the original contents of jQuery-tagEditor’s README.md file:

jQuery-tagEditor
================

A powerful and lightweight tag editor plugin for jQuery based on jQuery-tagEditor by Pixabay

Compatible with jQuery 1.7.0+ in Firefox, Safari, Chrome, Opera, Internet Explorer 8+. IE7 technically works, but no care has gone into CSS/layout bugs.
Released under the MIT License: http://www.opensource.org/licenses/mit-license.php

This plugin was developed by and for [Pixabay.com](https://pixabay.com/) - an international repository for sharing free public domain images.
We have implemented this plugin in production and we share this piece of software - in the spirit of Pixabay - freely with others.

## Demo and Documentation

https://goodies.pixabay.com/jquery/tag-editor/demo.html

## Features

* Lightweight: 8.5 kB of JavaScript - less than 3.2 kB gzipped
* Edit in place tags
* Intuitive navigation between tags with cursor keys, Tab, Shift+Tab, Enter, Pos1, End, Backspace, Del, and ESC
* Optional jQuery UI sortable
* Optional jQuery UI autocomplete
* Copy-paste or delete multiple selected tags
* Duplicate tags check
* Custom delimiter/s
* Placeholder
* Custom style for faulty tags
* Public methods for reading, adding and removing tags + destroy function
* Callbacks
* Allows tabindex for form navigation
* Graceful degradation if JavaScript is disabled

## Changelog

### Version 1.0.20 - 2016/01/30

* Fixed #62: tagEditor is blocking key events on other input and textarea elements on page.

### Version 1.0.19 - 2015/12/02

* Fixed #60: Tag editor fails to handle HTML operator chars.

### Version 1.0.18 - 2015/08/12

* Pull #43: Escape HTML special characters on input.

### Version 1.0.17 - 2015/07/14

* Allow beforeTagSave() to return `false` for discarding certain tag values.

### Version 1.0.16 - 2015/07/01

* Fix #5, #35, #37, #38: "TypeError: owner is null" backspace browser history issue.

### Version 1.0.15 - 2015/05/24

* Fix #31, #33, #34: Added maxTags, removeDuplicates, and animateDelete options.

### Version 1.0.14 - 2015/04/05

* Fix #24: Auto-close tag after selecting autocomplete suggestion by mouse click.

### Version 1.0.13 - 2015/01/26

* Fix #9: Added bower support.

### Version 1.0.12 - 2015/01/16

* Fix #17: Make use of tabindex for form navigation.

### Version 1.0.11 - 2015/01/08

* Use beforeTagSave return value for overwriting new tags.

### Version 1.0.10 - 2015/01/04

* Fix for IE8

### Version 1.0.9 - 2014/12/17

* Optimized internal input autogrow function.

### Version 1.0.8 - 2014/12/14

* Added bower.json file.

### Version 1.0.7 - 2014/11/26

* Removing accursoft's caret plugin (http://code.accursoft.com/caret) from tagEditor source (and adding caret as a dependency).

### Version 1.0.6 - 2014/10/22

* Fixed: Detection for selected field (.tag-editor) on backspace/delete keypress failed in some cases.

### Version 1.0.5 - 2014/09/30

* Merged pull - Added logic for selected field to be .tag-editor only:
  https://github.com/jegarts/jQuery-tagEditor/commit/498435b562d72c3e502863312b0b2ccbb9e80cab

### Version 1.0.4 - 2014/09/24

* Merged pull stop aco.select form calling itself:
  https://github.com/jegarts/jQuery-tagEditor/commit/fd0340ba46272290cedc8991f58769945d0fc2c2

### Version 1.0.3 - 2014/09/13

* Removed unnecessary vendor prefixes in CSS stylesheet.

### Version 1.0.2 - 2014/07/16

* Fixed removal of placeholder after calling addTags.

### Version 1.0.1 - 2014/07/16

* Fixed tagEditor for IE8 and IE7. IE7 still has some obvious layout alignment bugs, that can be fixed by conditional CSS rules.

### Version 1.0.0-beta - 2014/07/15

* First release
