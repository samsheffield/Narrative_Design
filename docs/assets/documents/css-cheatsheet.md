# Cascading Style Sheets

Cascading Style Sheets (CSS) are used to describe to a web browser how to display HTML elements. CSS is often saved in .css files. 

## CSS syntax
CSS syntax consists of rules defined by a `selector` and a `declaration block`.

For example:
```
body {
  background-color: white;
}
```

- `body` is the selector. It refers to the _selected__ HTML elements to style.
- The text between `{ }` is the declaration block and contains a `property` followed by a `value`, separated by a `:`. Each property:value pair is ended with a `;`

## Common HTML Elements
Here are some common HTML elements that you'll find in the web exported Ink game:
- body: The entire web browser window and the elements contained within
- h1 and h2: Text headers for titles
- p: Paragraphs and the elements contained within
- a and a:hover: Properties for links
- img: Images

## Common CSS properties
Some properties are used to style many different kinds of HTML elements:
- font-family: The font used for text
- font-weight: The weight of the font such as normal, bold, or lighter
- background: The color of the background of an HTML element
- color: The color of an HTML element

## Editing CSS
You will need some sort of plain text editor to make changes to your CSS file. This can be something as simple as Notepad (PC) or TextEdit (Mac). However, I would recommend a programming editor like [VS Code](https://code.visualstudio.com/) because it will make some basic tasks like selecting colors much more straightforward.

## IMPORTANT!
__Once you start editing the style.css file, it is important that you do not choose to Export the project to Web. This will overwrite your style.css file! Use Export story.js only.__


## Useful Ink-related CSS
The CSS file which styles an web-based Ink game is `style.css`, which is located in the web export folder you create.

### Change background color

## Container issues
If we change the color property of .container you'll notice that the background box is scaling to fit text but ignoring images. One option is to remove the color property, which will then just show the background of body instead.

### Change container color
```
.container
{
    color: white;
}
```

### Colors for the web
Color properties for HTML elements can be specified by name from a [small list of available color keywords](https://www.w3.org/wiki/CSS/Properties/color/keywords) or by providing a hexadecimal number representing the Red, Green, and Blue values (#RRGGBB or #RGB). More info [here](https://www.w3schools.com/css/css_colors_hex.asp#:~:text=A%20hexadecimal%20color%20is%20specified,the%20components%20of%20the%20color.)

### Change font color
Choose the HTML text element you want to change (h1, h2, p) and change the appropriate color property in its selector. For example:

```
p {
    color: #888;
}
```

### Change choice color

```
a {
    color: blue;
}
```

### Fonts
Fonts on the web are a little confusing at first. When you specify a font by name, the person viewing the web page must have that font installed on their own device. Consequently, web designers often list several fonts in their CSS, in order of preference, separated by commas, such as:

```
body {
    font-family: "Quattrocento", Georgia, 'Times New Roman', Times, serif;
}
```

#### Quotes?
Only non-standard fonts or fonts with special characters such as ! or $ need to be quoted. However, it's also a recommendation for web designers to also use them around names containing spaces.

### Web-safe fonts
Generally speaking, these fonts are considered "web safe":
- Arial (sans-serif)
- Verdana (sans-serif)
- Tahoma (sans-serif)
- Trebuchet MS (sans-serif)
- Times New Roman (serif)
- Georgia (serif)
- Garamond (serif)
- Courier New (monospace)
- Brush Script MT (cursive)

### Web Fonts
This is obviously very limiting, but thankfully there are now options to link to web-based fonts provided by companies like [Google](https://fonts.google.com/) or [Adobe]()

An example of a web font provided by Google looks like this:
```
@import url('https://fonts.googleapis.com/css?family=Open+Sans:300,700|Quattrocento:700');
```

The @import rule should be at the top of your CSS file. Note: Google provides this between `<style></style>` tags. Do not include those tags in your CSS.

### Overflow
If you are running into issues with your game being cut off at the bottom of the web browser window, you can try removing the `overflow:hidden` property in the `body` selector.

