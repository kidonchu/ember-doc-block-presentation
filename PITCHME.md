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

**Incorrect @namespace and @class**

* UpperCamelCased
* @namespace: <class_type>.<directory_path>
* @class: <file_name>. If generic filename, then <parent_directory>

#VSLIDE

### Quiz Time

<dl>
	<dt>File</dt>
	<dd>
	app/addresses/delete-address-modal/component.js
	export default Component.extend()
	</dd>
</dl>

#VSLIDE

<dl>
	<dt>File</dt>
	<dd>
	app/addresses/delete-address-modal/component.js
	export default Component.extend()
	</dd>
	<dt>Class</dt>
	<dd>DeleteAddressModal</dd>
	<dt>Namespace</dt>
	<dd>Component.Addresses</dd>
</dl>

---

**No @public for bound properties**

* If a property is bound to outer components, `@public` should be used.

---

### Any other mistakes?

---

### Future improvement

* Link to dependent properties
* queryParams helper
* Per file linting
* @private properties that are not bound to outer components
* More readable theme

---
