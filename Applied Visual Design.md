## Applied Visual Design

### COLOR

#### rgba()

> Instead of adjusting your overall background or the color of the text to make the foreground easily readable, you can add a `background-color`to the element holding the text you want to emphasize. This challenge uses `rgba()`instead of `hex`codes or normal `rgb()`.
>
> > rgba stands for:
> >   r = red
> >   g = green
> >   b = blue
> >   a = alpha/level of opacity
>
> The RGB values can range from 0 to 255. The alpha value can range from 1, which is fully opaque or a solid color, to 0, which is fully transparent or clear. `rgba()`is great to use in this case, as it allows you to adjust the opacity. This means you don't have to completely block out the background.
>
> You'll use `background-color: rgba(45, 45, 45, 0.1)`for this challenge. It produces a dark gray color that is nearly transparent given the low opacity value of 0.1.
>
> To make the text stand out more, adjust the `background-color`of the `h4`element to the given `rgba()`value.

![1541425743676](D:\MarkDownPic\1541425743676.png)
#### hsl()

> Colors have several characteristics including hue, saturation, and lightness. CSS3 introduced the `hsl()`property as an alternative way to pick a color by directly stating these characteristics.
>
> **Hue** is what people generally think of as 'color'. If you picture a spectrum of colors starting with red on the left, moving through green in the middle, and blue on right, the hue is where a color fits along this line. In `hsl()`, hue uses a color wheel concept instead of the spectrum, where the angle of the color on the circle is given as a value between 0 and 360.
>
> **Saturation** is the amount of gray in a color. A fully saturated color has no gray in it, and a minimally saturated color is almost completely gray. This is given as a percentage with 100% being fully saturated.
>
> **Lightness** is the amount of white or black in a color. A percentage is given ranging from 0% (black) to 100% (white), where 50% is the normal color.
>
> | Color   | HSL                 |
> | ------- | ------------------- |
> | red     | hsl(0, 100%, 50%)   |
> | yellow  | hsl(60, 100%, 50%)  |
> | green   | hsl(120, 100%, 50%) |
> | cyan    | hsl(180, 100%, 50%) |
> | blue    | hsl(240, 100%, 50%) |
> | magenta | hsl(300, 100%, 50%) 

#### linear-gradient()

> Applying a color on HTML elements is not limited to one flat hue. CSS provides the ability to use color transitions, otherwise known as gradients, on elements. This is accessed through the `background`property's `linear-gradient()`function. Here is the general syntax:
>
> ```
> background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...);
> ```
>
> The first argument specifies the direction from which color transition starts - it can be stated as a degree, where 90deg makes a vertical gradient and 45deg is angled like a backslash. The following arguments specify the order of colors used in the gradient.
>
> Example:
>
> ```
> background: linear-gradient(90deg, red, yellow, rgb(204, 204, 255));
> ```
>
> ![1541429662845](D:/MarkDownPic/1541429662845.png)
>
> ![1541429675676](D:/MarkDownPic/1541429675676.png)

+ repeating-linear-gradient()

  ![1541429953316](D:/MarkDownPic/1541429953316.png)

  > The `repeating-linear-gradient()`function is very similar to `linear-gradient()`with the major difference that it repeats the specified gradient pattern. `repeating-linear-gradient()`accepts a variety of values, but for simplicity, you'll work with an angle value and color stop values in this challenge.
  >
  > The angle value is the direction of the gradient. Color stops are like width values that mark where a transition takes place, and are given with a percentage or a number of pixels.
  >
  > In the example demonstrated in the code editor, the gradient starts with the color `yellow`at 0 pixels which blends into the second color `blue`at 40 pixels away from the start. Since the next color stop is also at 40 pixels, the gradient immediately changes to the third color `green`, which itself blends into the fourth color value `red`as that is 80 pixels away from the beginning of the gradient.
  >
  > For this example, it helps to think about the color stops as pairs where every two colors blend together.
  >
  > ```
  > 0px [yellow -- blend -- blue] 40px [green -- blend -- red] 80px
  > ```
  >
  > If every two color stop values are the same color, the blending isn't noticeable because it's between the same color, followed by a hard transition to the next color, so you end up with stripes.

### TEXT
#### text-transform 

> The `text-transform`property in CSS is used to change the appearance of text. It's a convenient way to make sure text on a webpage appears consistently, without having to change the text content of the actual HTML elements.
>
> The following table shows how the different `text-transform`values change the example text "Transform me".
>
> | Value        | Result                                                |
> | ------------ | ----------------------------------------------------- |
> | `lowercase`  | "transform me"                                        |
> | `uppercase`  | "TRANSFORM ME"                                        |
> | `capitalize` | "Transform Me"                                        |
> | `initial`    | Use the default value                                 |
> | `inherit`    | Use the `text-transform`value from the parent element |
> | `none`       | **Default:** Use the original text                    |

#### text-align 

+ `text-align: justify;`causes all lines of text except the last line to meet the left and right edges of the line box.

+ `text-align: center;`centers the text Another positioning technique is to center a block element horizontally. **One way to do this is to set its `margin`to a value of auto.**

+ `text-align: right;`right-aligns the text

+ And `text-align: left;`(the default) left-aligns the text.

#### Strong Underline Emphasize line-through

+ strong: To make text bold, you can use the strong tag. This is often used to draw attention to text and symbolize that it is important. With the strong tag, the browser applies the CSS of **font-weight: bold; to the element.** or **`strong`** or **font-weight: 800/600/200;**
+ Underline: To underline text, you can use the `u`tag. This is often used to signify that a section of text is important, or something to remember. With the `u`tag, the browser applies the CSS of **text-decoration: underline;`to the element.**
+ emphasize: To emphasize text, you can use the `em`tag. This displays text as italicized, as the browser applies the CSS of  **font-style: italic;** to the element.
+ line-through: To strikethrough text, which is when a horizontal line cuts across the characters, you can use the `s`tag. It shows that a section of text is no longer valid. With the `s`tag, the browser applies the CSS of **text-decoration: line-through**; to the element.
+ `hr`: You can use the `hr`tag to add a horizontal line across the width of its containing element. This can be used to define a change in topic or to visually separate groups of content.

#### line-height

> CSS offers the `line-height`property to change the height of each line in a block of text. As the name suggests, it changes the amount of vertical space that each line of text gets.

![1541426739396](D:/MarkDownPic/1541426739396.png)

![1541426782684](D:/MarkDownPic/1541426782684.png)

### position
+ relative: 
    > When the position of an element is set to `relative`, it allows you to specify how CSS should move it *relative* to its current position in the normal flow of the page. It pairs with the CSS offset properties of `left`or `right`, and `top`or `bottom`. These say how many pixels, percentages, or ems to move the item *away* from where it is normally positioned. 

    > The CSS offsets of `top`or `bottom`, and `left`or `right`tell the browser how far to offset an item relative to where it would sit in the normal flow of the document. You're offsetting an element away from a given spot, which moves the element away from the referenced side (effectively, the opposite direction). As you saw in the last challenge, using the top offset moved the `h2`downwards. Likewise, using a left offset moves an item to the right.
    >
    > 反向

+ absolute:

    > The next option for the CSS `position`property is `absolute`, which locks the element in place **relative to its parent container.** Unlike the `relative`position, this removes the element from the normal flow of the document, so surrounding items ignore it. The CSS offset properties (top or bottom and left or right) are used to adjust the position.
    >
    > One nuance with absolute positioning is that it will be locked relative to its closest *positioned* ancestor. If you forget to add a position **rule to the** **<u>parent item</u>, (this is typically done using `position: relative;`)**, the browser will keep looking up the chain and ultimately default to the body tag.

+ fixed

    > The next layout scheme that CSS offers is the `fixed`position, which is a type of absolute positioning that locks an element relative to the browser window. Similar to absolute positioning, it's used with the CSS offset properties and also removes the element from the normal flow of the document. Other items no longer "realize" where it is positioned, which may require some layout adjustments elsewhere.
    >
    > One key **difference** between the `fixed`and `absolute`positions is that an element with a fixed position won't move when the user scrolls.

+ float

    > The next positioning tool does not actually use `position`, but sets the `float`property of an element. Floating elements are removed from the normal flow of a document and pushed to either the `left`or `right`of their containing parent element. It's commonly used with the `width`property to specify how much horizontal space the floated element requires.
    >
    > The given markup would work well as a two-column layout, with the `section`and `aside`elements next to each other. Give the `#left`item a `float`of `left`and the `#right`item a `float`of `right`.

### z-index

> When elements are positioned to overlap, the element coming later in the HTML markup will, by default, appear on the top of the other elements. However, the `z-index`property can specify the order of how elements are stacked on top of one another. It must be an integer (i.e. a whole number and not a decimal), and higher values for the `z-index`property of an element move it higher in the stack than those with lower values.

**One way to do this is to set its `margin`to a value of auto.**

###  box-shadow (very cool)

> The `box-shadow`property takes values for `offset-x`(how far to push the shadow horizontally from the element), `offset-y`(how far to push the shadow vertically from the element), `blur-radius`, `spread-radius`and a color value, in that order. The `blur-radius`and `spread-radius`values are optional.
>
> ![1541426298273](D:/MarkDownPic/1541426298273.png)
>
> ![1541426326146](D:/MarkDownPic/1541426326146.png)

### scale()
Change the Size of an Element

To change the scale of an element, CSS has the `transform`property, along with its `scale()`function. The following code example doubles the size of all the paragraph elements on the page:

> p {
>   transform:scale(2);
> }

![1541431222074](D:/MarkDownPic/1541431222074.png)

