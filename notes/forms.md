## Forms ##
Can be initialized using the `form` element
- Will wrap all of the elements in the form
- Most common attributes are `action` and `method`
  - `action` contains the URL to which the submitted info will be sent
  - `method` specifies with HTTP method to use on submission
```html
<form action="/login" method="post">
  ...
</form>
```
### `input` element ###
Used to obtain input from the user
- Most common attributes are `type` and `name`
- `type` specifies type of input ex:
  - `text`
  - `number`
  - `email`
  - `tel`
  - `url`
  - `date`
  - `search`
  - `time`
- `name` is used to identify the data that is sent to the server
  - It is also submitted and what you'd use to identify the data server-side

**Other attributes**
- `required` --> makes input required
- `disabled` --> disables input
- `placeholder` --> can set a placeholder value e.g `placeholder="example@emai.com"`

### `radio` and `checkbox` ###
- These are another `type` for `input` elements with additional options
- Allow for multiple choice selection from a set of `value`s
  - **Note** that `radio` only allows a single selectuon, `checkbox` allows multiple
- To preselect an option, can use `checked` attibute
- For radio and checkbox, names should be shared since the data is in a group
```html
<input type="radio" name="day" value="Friday" checked> Friday
<input type="radio" name="day" value="Saturday"> Saturday
<input type="radio" name="day" value="Sunday"> Sunday

<input type="checkbox" name="day" value="Friday" checked> Friday
<input type="checkbox" name="day" value="Saturday"> Saturday
<input type="checkbox" name="day" value="Sunday"> Sunday
```
```html
<input type="date" name="birthday">
<input type="time" name="game-time">
<input type="email" name="email-address">
<input type="url" name="website">
<input type="number" name="cost">
<input type="tel" name="phone-number">
```

### `textarea` ###
This is an element used to capture larger passages of texts, spanning multiple lines
- Typically used for comment style input
```html
<textarea name="comment">Add your comment here</textarea>
```

### Dropdown and multiple selection ###
These can be achieved using the `select` element
- Only difference between drop-down and multiple select `multiple` attribute
  - down down does not have `multiple` attribute
- Has an `option` element
  - Has a `value` attribute
  - Also a default selection using `selected` attribute
  
```html
<select name="day" multiple>
  <option value="Friday" selected>Friday</option>
  <option value="Saturday">Saturday</option>
  <option value="Sunday">Sunday</option>
</select>
```

## Form buttons ##
### Submit input ###
- Can use `input` element to submit a form
  - `type` and `name` should be "submit", `value` will show up as text on buttom
```html
<input type="submit" name="submit" value="Send">
```
### Submit button ###
- For more flexibility, we can use a `button` to submit a form
  - More flexible since the element is **not self-contained** like input
  - As such, can wrap other elements
- Has `type` and `name` attributes, `type` for buttons is `submit` by default
  - `type` can technically be omitted if submitting a form because of this

```html
<button name="submit">
  <strong>Send Us</strong> a Message
</button>
```

### `formAction` attribute ###
A button has a `formaction` attribute that can be used to override the `action` attribute of the `form`


## Oranizing form elements ##
Form elements should be given a preceding or wrapping `label` element
- Should also be explicitly given an `id` attribute
- Allows you to specify a different URL for the form data to be sent, as well as new method
```pug
<button formaction="/contacts" formmethod="get">
  Cancel
</button>
```
### `label` element ###
Used to describe inputs or controls that they pertain to
- Includes a `for` attribute that should be same as `name` and `id`
- For `radio` and `checkbox` elements, `label` can wrap `input` instead
  - No need for any attributes on label in this scenario
```html
<label for="username">Username</label>
<input type="text" name="username" id="username">
```
```html
<label>
  <input type="radio" name="day" value="Friday" checked> Friday
</label>
<label>
  <input type="radio" name="day" value="Saturday"> Saturday
</label>
```
