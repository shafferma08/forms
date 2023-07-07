# Revised Web Development Lecture Notes on Forms

## 1. Forms and Form Validation

- **Form:** A form in web development is a user interface component that collects data from the user. They are primarily used for activities such as registration, login, data submission, etc.

- **Form Validation:** The process of ensuring that the user has provided valid information in the expected format before the data is sent to the server. Validation enhances user experience and protects your system from malicious or erroneous data.

## 2. Review of Form Elements and Their Events

**Form Elements Include:**

- `<input type="text">`: For single-line text input.
- `<textarea>`: For multi-line text input.
- `<input type="checkbox">`: For allowing the user to select zero or more options of a limited number of choices.
- `<input type="radio">`: For allowing the user to select exactly one of a predefined set of mutually exclusive options.
- `<select>`: Creates a drop-down list. `<option>` elements nested inside define the available options.
- `<button>`: Defines a clickable button.

**Form Event Handlers Include:**

- `input`: Triggers when the value of an input element changes.
- `change`: Similar to `input`, but doesn't trigger until the control loses focus.
- `focus`: Triggers when the input field gets focus.
- `blur`: Triggers when the input field loses focus.

## 3. The Form Object and Its Attributes

The Form object represents an HTML form element. It provides properties and methods to manipulate the form:

- `action`: Specifies where to send the form-data when a form is submitted.
- `method`: Specifies the HTTP method (GET/POST) to be used when submitting the form-data.
- `target`: Specifies where to display the response after submitting the form.
- `enctype`: Specifies how the form-data should be encoded when submitting it to the server.
- `autocomplete`: Specifies whether a form should have autocomplete on or off.
- `checkValidity()`: Returns true if an element's value satisfies its constraints; false otherwise.
- `validity`: Represents the validity state of an input element.
- `setCustomValidity()`: Sets the validationMessage property of an input element, or the element it is contained within.
- `validationMessage`: Holds the message that the browser will display when the validity is false.
- `valid`: Returns true if an input element contains data that matches its data type; false otherwise.
- `invalid`: Returns true if an input element contains data that does not match its data type; false otherwise.

## 4. HTML Form Validation Attributes

These are HTML attributes used for validation:

- `required`: Specifies that an input field must be filled out before submitting the form.
- `pattern`: Specifies a regular expression that an `<input>` element's value is checked against.
- `min` and `max`: Define the minimum and maximum values for an `<input>` element.
- `minlength` and `maxlength`: Define the minimum and maximum number of characters for an `<input>` element.

## 5. Client-Side Form Validation

Client-side form validation is performed in the user's browser before data is sent to a server. Validation can be done using HTML5 validation attributes, JavaScript-based validation for more complex requirements, or custom validation.

## 6. Difference Between Client-Side and Server-Side Validation

- **Client-Side Validation:** Provides immediate feedback to users and helps catch errors early. However, it should not be used alone as users can easily bypass it.
- **Server-Side Validation:** Takes place on the server, is more secure, and should always be performed because it can't be bypassed by users.
- 
Always use both client-side and server-side validation to ensure both user friendliness and data integrity. Client-side validation provides immediate feedback, while server-side validation ensures data integrity even if a user bypasses the client-side checks.

## 7. GET and POST Methods

- **GET:** Appends form-data to the URL in name/value pairs. It's best for non-sensitive data and when you want to bookmark the result.
- **POST:** Form-data is sent as HTTP message body. It's used when dealing with sensitive data or large amounts of data.

