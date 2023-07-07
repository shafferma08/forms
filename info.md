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

# GET and POST Methods

- **GET:** Appends form-data to the URL in name/value pairs. It's best for non-sensitive data and when you want to bookmark the result.
- **POST:** Form-data is sent as HTTP message body. It's used when dealing with sensitive data or large amounts of data.

## 1. GET Method

- The **GET** method sends the encoded user information appended to the page request. The page and the encoded information are separated by the `?` character.

- Data sent by **GET** method can be accessed using `$_GET` array in PHP.

- It's the default method for sending form data.

- **GET** requests can be cached, bookmarked, and remain in the browser history, and have length restrictions.

- **GET** is less secure compared to **POST** because data sent is part of the URL. It is not suitable for passing sensitive information like passwords.

- It is used when the interaction is idempotent, and when you want to retrieve data, not modify it.

## 2. POST Method

- The **POST** method transfers information via HTTP headers. The information is encoded as described in case of **GET** method and put into a header called QUERY_STRING.

- Data sent by **POST** method goes through HTTP header so security depends on HTTP protocol. By using Secure HTTP you can make sure that your information is secure.

- Data sent by **POST** method can be accessed using `$_POST` array in PHP.

- **POST** requests cannot be cached, bookmarked, do not remain in the browser history, and do not have length restrictions.

- It is used when you want to send sensitive, confidential, large amounts of data, or non-idempotent requests.

# Storing and Processing Data

The data collected by HTML forms can be stored and processed in various ways, typically involving a server-side language like PHP, JavaScript (Node.js), Python, Ruby, Java, etc., and a database system like MySQL, PostgreSQL, MongoDB, etc.

1. **Storing Data**: Once the form data is validated, it can be stored in a database for future use. The server-side language will connect to the database, create an appropriate SQL query to insert the data, and execute it.

2. **Processing Data**: This could mean many things depending on the application. It might involve checking the data against existing data in the database (e.g., check if a username already exists), performing calculations (e.g., calculating cost based on input quantities and prices in a shopping app), or updating related data in the database (e.g., updating an 'last active' timestamp in a user profile).

3. **Returning a Response**: After the data has been processed, the server will typically send a response back to the client. This might be as simple as a confirmation message, or it could involve returning some data to the client (e.g., search results, updates).



The methods `GET` and `POST` in an HTML form merely dictate how the data is sent to the server, not how it's processed. Both `GET` and `POST` can lead to a new HTML page, but the data handling and processing happens server-side, which involves a backend language like PHP, Node.js, Python, etc.

**HTML Forms and the GET/POST Methods:**

- `GET`: When a form uses the `GET` method, the form data is appended to the URL as query parameters when the form is submitted. This can be useful when you want to allow users to bookmark a specific state of the form or when the form is idempotent (i.e., it doesn't cause a change on the server).

- `POST`: When a form uses the `POST` method, the form data is included in the body of the HTTP request when the form is submitted. This is typically used when the form data is expected to cause a change on the server (such as creating a new record in a database, updating a record, etc.), or when you're sending sensitive or a large amount of data.

**Server-Side Processing:**

However, merely sending the form data to the server does not imply that it is processed. Processing the form data is a separate step that is handled by your server-side code:

- When the server receives a request containing form data, your server-side code needs to parse the form data from the request.

- Then, it needs to do something with that data—typically, this might involve writing the data to a database, reading from a database, updating a database, sending an email, etc.

- The server-side code may then generate a response to send back to the client. This could be a whole new HTML page, a redirect instruction, a small snippet of data, or a status code.

It's important to note that the `GET` and `POST` methods in an HTML form are completely separate from the HTTP GET and POST requests your server-side code might make when interacting with other servers or APIs. The HTTP methods used in an HTML form dictate how the form data is sent from the client to your server, while the HTTP methods used in server-side code dictate how your server interacts with other servers.
