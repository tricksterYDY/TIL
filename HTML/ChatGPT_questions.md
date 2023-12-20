# Q :

## "Why does the browser automatically add the <tbody> tag when creating a table in HTML without explicitly including it?"

# A : (explained below)

HTML has optional tags, and the <tbody> tag is one of them. When you create a table in HTML without explicitly including the <tbody> tag, the browser will still generate it in the Document Object Model (DOM) during the rendering process.

In your provided example, even though you didn't include <tbody> in your HTML code, the browser's developer tools are adding it in the DOM representation. The browser automatically adds <tbody> to group the table rows (<tr>) when it's not explicitly provided.

So, your HTML code without <tbody>:
```html
<table>
  <tr>
    <th>용도</th>
    <th>중량</th>
    <th>갯수</th>
    <th>가격</th>
  </tr>
  <!-- ... (other rows) ... -->
</table>
```

Is essentially interpreted by the browser as:
```html
<table>
  <tbody>
    <tr>
      <th>용도</th>
      <th>중량</th>
      <th>갯수</th>
      <th>가격</th>
    </tr>
    <!-- ... (other rows) ... -->
  </tbody>
</table>
```

This behavior is specified in the HTML5 specification. The <tbody> element is automatically created by the browser if not explicitly provided, and it serves as a container for the rows in the table. It's a part of the HTML standard to enhance the structure of tables in the DOM.

# Q :

## Self-contained tags list

# A : `<img>`, `<br>`, `<hr>`, `<input>`, `<meta>`, `<link>`, `<base>`, `<wbr>`, `<col>`

If by "self-contained tags list" you are referring to HTML tags that are considered self-contained or void elements (elements that cannot have content and don't need a closing tag), here are some common examples:

1. **`<img>`:**
   - Used to embed images.
   - Example: `<img src="image.jpg" alt="Description">`

2. **`<br>`:**
   - Represents a line break.
   - Example: `<p>First line<br>Second line</p>`

3. **`<hr>`:**
   - Represents a thematic break (horizontal line).
   - Example: `<hr>`

4. **`<input>`:**
   - Represents an input field.
   - Example: `<input type="text" name="username">`

5. **`<meta>`:**
   - Provides metadata about the HTML document.
   - Example: `<meta charset="UTF-8">`

6. **`<link>`:**
   - Specifies external resources, such as stylesheets.
   - Example: `<link rel="stylesheet" href="styles.css">`

7. **`<base>`:**
   - Specifies a base URL for all relative URLs in a document.
   - Example: `<base href="https://example.com/">`

8. **`<wbr>`:**
   - Represents a word break opportunity within text.
   - Example: `This is a long text with a <wbr>wordbreak.`

9. **`<col>`:**
   - Specifies column properties for each column within a `<colgroup>` element.
   - Example: `<col style="background-color:yellow">`

These tags are considered self-contained or void elements because they don't have content and don't require a closing tag. They are often used to embed or define specific elements within the HTML structure.

 # Q :
 
 ## Why type="hidden" is needed?
 
 # A : (explained below)
 The type="hidden" attribute is used in HTML to create hidden input fields in forms. Hidden fields are not visible to users but can carry data that needs to be submitted when the form is processed on the server side. Here are some common use cases for type="hidden" fields:

Passing Values Between Pages:
Hidden fields are often used to pass information between different pages or steps in a form. For example, you might store a user's session ID, a token, or some other data in a hidden field that is submitted with the form. This allows the server to recognize the user or maintain state across multiple requests.
```html
<input type="hidden" name="sessionID" value="abc123">
```

Storing Default Values:
You can use hidden fields to store default values for certain form fields. If you have a form with optional fields, you can set default values in hidden fields and update them dynamically with JavaScript if needed.
```html
<input type="hidden" name="defaultSetting" value="someDefault">
```

Security Tokens:
Hidden fields are commonly used to include security tokens in forms. These tokens help protect against cross-site request forgery (CSRF) attacks by ensuring that the form is submitted by the same user who requested the form.
```html
<input type="hidden" name="csrfToken" value="randomTokenValue">
```

Tracking Information:
Hidden fields can be used to track information that doesn't need to be displayed to the user but is relevant to the server-side processing. This information can include analytics data, source page information, or any other data you want to associate with the form submission.
```html
<input type="hidden" name="trackingInfo" value="someData">
```
In summary, type="hidden" is needed when you want to include data in a form that should be submitted but doesn't need to be displayed to the user. This is useful for various purposes, including maintaining state, passing information between pages, and enhancing the security of form submissions.


