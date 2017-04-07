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

**No escaping for handlebar examples**

```
/**
 * No escape character:
 * {{#ember-doc-block.no-escape.wrong-way}}
 *     Hello, I'm invisible
 * {{/ember-doc-block.no-escape.wrong-way}}
 *
 * Wrong escape character:
 * /{{#ember-doc-block.no-escape.wrong-way}}
 *     Hello, I'm invisible
 * {{/ember-doc-block.no-escape.wrong-way}}
 */
```

#VSLIDE

**Escape handlebar examples with backslash**

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

**No blank line after description**

```
/**
 * Demonstrates doc blocks
 * @class DocBlock
 * @namespace Component
 * @extends Ember.Component
 */
```

#VSLIDE

**Insert blank line after description**

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

**No @class level doc block**

* If @property is defined but @class is not, the property shows up as if it belongs
to different @class.
* @class should be defined if any primary tags are defined in the file.

---

**Incorrect type definitions**

* Try to be as specific as possible when defining the type.

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

**No @public for bound properties**

* If a property is bound to outer components, `@public` should be used.

---

### Future improvement

* Link to dependent properties
* queryParams helper
* Per file linting
* @private properties that are not bound to outer components
* More readable theme

---
