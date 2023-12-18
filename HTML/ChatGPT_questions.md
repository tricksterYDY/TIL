
HTML has optional tags, and the <tbody> tag is one of them. When you create a table in HTML without explicitly including the <tbody> tag, the browser will still generate it in the Document Object Model (DOM) during the rendering process.

In your provided example, even though you didn't include <tbody> in your HTML code, the browser's developer tools are adding it in the DOM representation. The browser automatically adds <tbody> to group the table rows (<tr>) when it's not explicitly provided.

So, your HTML code without <tbody>:
<table>
  <tr>
    <th>용도</th>
    <th>중량</th>
    <th>갯수</th>
    <th>가격</th>
  </tr>
  <!-- ... (other rows) ... -->
</table>


Is essentially interpreted by the browser as:
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

This behavior is specified in the HTML5 specification. The <tbody> element is automatically created by the browser if not explicitly provided, and it serves as a container for the rows in the table. It's a part of the HTML standard to enhance the structure of tables in the DOM.
