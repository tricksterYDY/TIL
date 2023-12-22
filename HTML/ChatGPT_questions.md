# Q :

## Why does the browser automatically add the <tbody> tag when creating a table in HTML without explicitly including it?

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

# Q :

## What do 'link', 'rel', & 'href' stand for?

# A : (explained below)

Certainly! In the context of HTML, "rel" and "href" are attributes used in anchor (`<a>`) and link (`<link>`) elements. Here's what each attribute means:

1. **rel:**
   - **Meaning:** The "rel" attribute stands for "relationship," and it specifies the relationship between the linked document and the current document. It is commonly used with the `<link>` element for stylesheets and the `<a>` element for hyperlinks.

   - **Example with link element:**
     ```html
     <link rel="stylesheet" href="styles.css">
     ```
     In this example, the "stylesheet" value for "rel" indicates that the linked document (styles.css) is a stylesheet.

   - **Example with anchor element:**
     ```html
     <a href="https://www.example.com" rel="nofollow">Visit Example.com</a>
     ```
     In this example, the "nofollow" value for "rel" indicates that search engines should not follow the link.

2. **href:**
   - **Meaning:** The "href" attribute stands for "hypertext reference," and it specifies the URL or location of the linked resource. It is used to create hyperlinks.

   - **Example with anchor element:**
     ```html
     <a href="https://www.example.com">Visit Example.com</a>
     ```
     In this example, the "https://www.example.com" value for "href" indicates the URL that the hyperlink points to.

These attributes are crucial for creating navigation and linking documents in HTML. The "rel" attribute defines the relationship of the linked resource, while the "href" attribute specifies the location of that resource.

# Q :

## What are em and rem in CSS?

# A : (explained below)

In CSS, `em` and `rem` are units of measurement that are used to define the size of elements. Here's an explanation of each:

1. **em:**
   - The `em` unit is a relative unit of measurement in CSS. It stands for "emphasized". It is based on the font size of the parent element. When you set a property using `em`, it is calculated relative to the font size of the element's nearest parent with a defined font size.

   Example:
   ```css
   body {
       font-size: 16px; /* Assume a base font size for the body */
   }

   h1 {
       font-size: 2em; /* This will be 32px (2 * 16px) */
   }

   p {
       font-size: 1.5em; /* This will be 24px (1.5 * 16px) */
   }
   ```

   In this example, the `em` unit is used to set the font size of `h1` and `p` elements relative to the font size of the `body`.

2. **rem:**
   - The `rem` unit is also a relative unit, but it is based on the font size of the root element (usually the `<html>` element). It stands for "root em". This makes `rem` more predictable and easier to manage, especially in complex layouts.

   Example:
   ```css
   html {
       font-size: 16px; /* Set a base font size for the entire document */
   }

   h1 {
       font-size: 2rem; /* This will be 32px (2 * 16px) */
   }

   p {
       font-size: 1.5rem; /* This will be 24px (1.5 * 16px) */
   }
   ```

   In this example, the `rem` unit is used to set the font size of `h1` and `p` elements relative to the root (`html`) font size.

Using relative units like `em` and `rem` is beneficial for creating flexible and scalable designs, especially in responsive web development where elements need to adapt to different screen sizes. `rem` is often preferred in modern web development because it avoids the compounding effects of nested elements that use `em`.

# Q :

## What are rgb(or rgba) and hsl(or hsla)?

# A : (explained below)

RGB (Red, Green, Blue) and HSL (Hue, Saturation, Lightness) are two different color models used in digital design and computer graphics to represent and manipulate colors.

1. **RGB (or RGBA):**
   - **RGB:** In the RGB color model, colors are represented as combinations of red, green, and blue light. Each color component can have values in the range of 0 to 255, where 0 represents the absence of color, and 255 represents the maximum intensity of that color. The combination of these three colors produces a wide range of colors. For example, (255, 0, 0) represents pure red, (0, 255, 0) represents pure green, and (0, 0, 255) represents pure blue.

   - **RGBA:** RGBA is an extension of RGB that includes an additional component, "A" for Alpha, which represents the transparency or opacity of the color. The alpha channel ranges from 0 (fully transparent) to 1 (fully opaque). This allows for the creation of semi-transparent or translucent colors.

2. **HSL (or HSLA):**
   - **HSL:** In the HSL color model, colors are represented by three components: Hue, Saturation, and Lightness. 
     - **Hue (H):** It represents the type of color (e.g., red, green, blue) and is expressed as an angle from 0 to 360 degrees.
     - **Saturation (S):** It represents the intensity or vividness of the color and is expressed as a percentage. A saturation of 100% means the color is fully saturated, while 0% represents a shade of gray.
     - **Lightness (L):** It represents the brightness of the color and is also expressed as a percentage. A lightness of 0% is black, 100% is white, and 50% is the normal color.

   - **HSLA:** Similar to RGBA, HSLA is an extension of HSL that includes an alpha channel for controlling transparency.

In summary, RGB is based on the additive color model using red, green, and blue light, while HSL is based on the perceptual aspects of human vision, categorizing colors by their hue, saturation, and lightness. Both models are widely used in web development, graphic design, and other digital applications.
