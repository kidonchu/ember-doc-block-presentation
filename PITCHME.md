# Ember Doc Block

---

## Showtime

* Navigating to type definition
* Navigating through method parameters
* Dependent properties for computed properties and observers
* Component usage with code example
* crossLink helper to help navigate easily

---

### Easy to navigate

**Old way**

- Find substring `{{#ac-table` in project
- Figure out what should be passed into the component

---

## Common mistakes

---

Not escaping handlebar examples

```
/**
 * {{#ember-doc-block.no-escape.wrong-way}}
 *     Hello, I'm invisible
 * {{/ember-doc-block.no-escape.wrong-way}}
 *
 * /{{#ember-doc-block.no-escape.wrong-way}}
 *     Hello, I'm invisible
 * {{/ember-doc-block.no-escape.wrong-way}}
 */
```

#VSLIDE

Escape handlebar examples with backslash

```
/**
 * \{{#ember-doc-block.no-escape.right-way}}
 *     \{{#ember-doc-block.no-escape.right-way.embedded}}
 *         Hello, I'm visible
 *     {{/ember-doc-block.no-escape.right-way.embedded}}
 * {{/ember-doc-block.no-escape.right-way}}
 */
```

---

### No blank line between description and tag groups

```
/**
 * Demonstrates doc blocks
 * @class DocBlock
 * @namespace Component
 * @extends Ember.Component
 */
```

#VSLIDE

There should be a blank line between description and tag groups.

**Correct**
```
/**
 * Demonstrates doc blocks
 *
 * @class DocBlock
 * @namespace Component
 * @extends Ember.Component
 */
```

---

### Not defining @class level docblock

You should define @class if you are adding any primary tags to the file.

If @property is defined but @class is not, the property shows up as if it belongs
to different @class.

---

### Wrong type declaration

---

### Mixing up @namespace and @class

```
/**
 * @class Drawer/Item
 * @namespace Component
 * @extends Ember.Component
 */
```

@TODO Show some examples of all cases

---

### Using tabs inside of doc block

---

### Not specifying @public in components

If a property is bound to outer components, @public tag should be used, for both
properties and functions.

---

### Please read through Examples page at least twice

This page will likely have an example for a doc block you are trying to create.
If it's missing, please let me know.

---

## Known issues

---

## Future improvement

---
