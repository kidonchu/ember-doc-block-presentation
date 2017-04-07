## Ember Doc Block

---

### Goals

* Convince you that doc blocks are useful
* Prevent from making mistakes

---

### Showtime

---

### Common mistakes

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

**Missing blank line after description**

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

**Missing @class level doc block**

* If @property is defined but @class is not, the property shows up as if it belongs
to different @class.
* @class should be defined if any primary tags are defined in the file.

---

**Incorrect type definitions**

* Try to be as specific as possible when defining the type.
* Think of type as what you expect to get when you call
  `this.get('your_property_name')`

---

**Incorrect @namespace and @class**

* UpperCamelCased
* @class: {file_name}. If generic filename, then {parent_directory}
* @namespace: {class_type}[.directory_path...]

---

### Quiz Time

#VSLIDE

<dl>
	<dt>Filename</dt>
	<dd>app/services/heartbeat.js</dd>
	<dt>File Content</dt>
	<dd>export default Service.extend()</dd>
</dl>

#VSLIDE

<dl>
	<dt>Filename</dt>
	<dd>app/services/heartbeat.js</dd>
	<dt>File Content</dt>
	<dd>export default Service.extend()</dd>
	<dt>Class</dt>
	<dd>Heartbeat</dd>
	<dt>Namespace</dt>
	<dd>Service</dd>
</dl>

#VSLIDE

<dl>
	<dt>Filename</dt>
	<dd>app/models/contact/contact-log.js</dd>
	<dt>File Content</dt>
	<dd>export default DS.Model.extend()</dd>
</dl>

#VSLIDE

<dl>
	<dt>Filename</dt>
	<dd>app/models/contact/contact-log.js</dd>
	<dt>File Content</dt>
	<dd>export default DS.Model.extend()</dd>
	<dt>Class</dt>
	<dd>ContactLog</dd>
	<dt>Namespace</dt>
	<dd>Model.Contact</dd>
</dl>

#VSLIDE

<dl>
	<dt>Filename</dt>
	<dd>app/components/auto-complete.js</dd>
	<dt>File Content</dt>
	<dd>export default Component.extend()</dd>
</dl>

#VSLIDE

<dl>
	<dt>Filename</dt>
	<dd>app/components/auto-complete.js</dd>
	<dt>File Content</dt>
	<dd>export default Component.extend()</dd>
	<dt>Class</dt>
	<dd>AutoComplete</dd>
	<dt>Namespace</dt>
	<dd>Component</dd>
</dl>

#VSLIDE

<dl>
	<dt>Filename</dt>
	<dd>app/contacts/edit/info/position/route.js</dd>
	<dt>File Content</dt>
	<dd>export default Route.extend()</dd>
</dl>

#VSLIDE

<dl>
	<dt>Filename</dt>
	<dd>app/contacts/edit/info/position/route.js</dd>
	<dt>File Content</dt>
	<dd>export default Route.extend()</dd>
	<dt>Class</dt>
	<dd>Position</dd>
	<dt>Namespace</dt>
	<dd>Route.Contacts.Edit.Info</dd>
</dl>

#VSLIDE

<dl>
	<dt>Filename</dt>
	<dd>app/doc-block/query-params-example/controller.js</dd>
	<dt>File Content</dt>
	<dd>export default Controller.extend()</dd>
</dl>

#VSLIDE

<dl>
	<dt>Filename</dt>
	<dd>app/doc-block/query-params-example/controller.js</dd>
	<dt>File Content</dt>
	<dd>export default Controller.extend()</dd>
	<dt>Class</dt>
	<dd>QueryParamsExample</dd>
	<dt>Namespace</dt>
	<dd>Controller.DocBlock</dd>
</dl>


---

**No @public for bound properties**

* If a property is bound to outer components, `@public` should be used.

#VSLIDE

```
{{can-i-help-you
	what='I want to make an order'
	when=1491577341
	afterHelp=(action 'hangup')
}}
```

#VSLIDE

```
/**
 * What the help is about
 *
 * @property what
 * @type {String}
 * @default ''
 * @public
 */
what: '',

/**
 * Help date in unix timestamp
 *
 * @property when
 * @type {Number}
 * @default 0
 * @public
 */
when: 0,

/**
 * What to do after done helping out
 *
 * @property afterHelp
 * @type {Function}
 * @default null
 * @public
 */
afterHelp: null,

/**
 * {{#dependentProperties}}
 * when
 * {{/dependentProperties}}
 *
 * @property helpDate
 * @type {Date}
 */
helpDate: Ember.computed('when', function() {
	return convertUnixTimestampToDate(this.get('when'));
}),
```

---

### Any other mistakes?

---

### Future improvement

* Link to dependent properties
* queryParams helper
* crossLink helper
* Per file linting
* @private properties that are not bound to outer components
* More readable theme

---
