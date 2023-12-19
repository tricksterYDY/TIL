
HTML has optional tags, and the <tbody> tag is one of them. When you create a table in HTML without explicitly including the <tbody> tag, the browser will still generate it in the Document Object Model (DOM) during the rendering process.

In your provided example, even though you didn't include <tbody> in your HTML code, the browser's developer tools are adding it in the DOM representation. The browser automatically adds <tbody> to group the table rows (<tr>) when it's not explicitly provided.

So, your HTML code without <tbody>:
'''html
<table>
  <tr>
    <th>용도</th>
    <th>중량</th>
    <th>갯수</th>
    <th>가격</th>
  </tr>
  <!-- ... (other rows) ... -->
</table>
'''

Is essentially interpreted by the browser as:
'''html
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
'''

This behavior is specified in the HTML5 specification. The <tbody> element is automatically created by the browser if not explicitly provided, and it serves as a container for the rows in the table. It's a part of the HTML standard to enhance the structure of tables in the DOM.

Q: self-contained tags list
A: If by "self-contained tags list" you are referring to HTML tags that are considered self-contained or void elements (elements that cannot have content and don't need a closing tag), here are some common examples:

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
