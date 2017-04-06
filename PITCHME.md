# Ember Doc Block

---

## Showtime

* Navigating to type definition
* Navigating through method parameters
* Dependent properties for computed properties and observers
* Component usage with code example
* crossLink helper to help navigate easily

---

## Common mistakes

---

### Not escaping code examples

**Incorrect**
```
/**
 * ``````
 * {{some-component
 *     property1=myProperty
 * }}
 * ``````
 */
```

#VSLIDE

**Correct**
```
/**
 * ``````
 * \{{some-component
 *     property1=myProperty
 * }}
 * ``````
 */
```

---

### Not defining @class level docblock

* You should define @class
* If @property is defined but not @class, the property shows up as if it belongs
to different @class

---

### Not having blank line between description and tag groups

---

### Incorrect type

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

### Please read through Examples page at least twice

This page will likely have an example for a doc block you are trying to create.
If it's missing, please let me know.

---

## Known issues

---

## Future improvement

---
