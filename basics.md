**Freeplane Scripts Coding Instructions:** 

Use the Groovy style for getters and setters (property-style access common in Groovy). So, for example, instead of writing "node.getPlainText()", simply write "node.plainText".

## How to access the node to which the script is applied

Freeplane always has at least one node selected. To apply a code to the node that is currently selected, there are some options.

One option is to simply start the line with `node.`. For example, to create a child node to the currently selected node, write `node.createChild()`.

Another option is to start the line with `c.selected.`.

Things that I've seem the GPT trying, but are wrong and don't work:
```
// Access the current (selected) node
def node = c.node
```

## Property-style access for node properties and attributes
Pay special attention to styling properties, such as background color, border color, and others. The correct way to apply styles often involves navigating through a series of properties. For example, to set the border color, use node.style.border.color instead of a direct assignment to a non-existent borderColor property. Always cross-reference with the scripting reference guide to confirm the correct property path and usage. For example, to use the clear method in the attributes: "node.attributes.clear()". When creating scripts for Freeplane, always use Groovy's property-style access for node properties and attributes, such as node.attributes.set('key', 'value') for adding or modifying node attributes.
Example of  Interfaces in which it is relevant:
- node.cloud
- node.style.edge
- node.reminder


## Working with colors: 
Take special care about how to use Colors. You can't simply use a color name as a string in a method.

Note that you need to choose to use the colors as hexadecimal color codes (for example: #FFFF0000) or color name in a way that Java understands (for example: java.awt.Color.YELLOW). 

If you choose to use color name, then you need to append "java.awt.Color." before the name of the color. It's not enough to write simply YELLOW, because you will get this exception: org.codehaus.groovy.runtime.typehandling.GroovyCastException: Cannot cast object 'Yellow' with class 'java.lang.String' to class 'java.awt.Color'. 
For example, to set the border of the node as YELLOW, do it like this: `node.style.border.color = java.awt.Color.YELLOW`. Or, if you used the color as a string before, than you can use reflection:
```
import java.awt.Color
color1 = "Yellow"
node.style.border.color = Color.class.getField(color1.toUpperCase()).get(null)
```

There are always 2 method variations, one for hexadecimal color codes (for example: #FFFF0000), and another one for color name (for example: java.awt.Color.YELLOW). Make sure you pick the correct one. 
- For hexadecimal color codes the method ends with "ColorCode". For example: `node.style.border.colorCode = "#ffff00ff"`
- for color name, the method ends with "Color". For example: `node.style.border.color = java.awt.Color.YELLOW`
