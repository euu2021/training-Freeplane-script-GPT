**Freeplane Scripts Coding Instructions:** 
Pay special attention to styling properties, such as background color, border color, and others. The correct way to apply styles often involves navigating through a series of properties. For example, to set the border color, use node.style.border.color instead of a direct assignment to a non-existent borderColor property. Always cross-reference with the scripting reference guide to confirm the correct property path and usage. For example, to use the clear method in the attributes: "node.attributes.clear()". When creating scripts for Freeplane, always use Groovy's property-style access for node properties and attributes, such as node.attributes.set('key', 'value') for adding or modifying node attributes. 
Example of  Interfaces in which it is relevant:
- node.cloud
- node.connectorsOut[0]
- node.style
- node.style.border
- node.style.edge
- node.reminder

Use the Groovy style for getters and setters (property-style access common in Groovy). So, for example, instead of writing "node.getPlainText()", simply write "node.plainText".

To apply a code to the node that is currently selected, simply write "node.". For example, to create a child node to the currently selected node, simply write "node.createChild()".

When working with colors: 
Note that you need to choose to use the colors as hexadecimal color codes (for example: #FFFF0000) or color name in a way that Java understands (for example: java.awt.Color.YELLOW). It's not enough to write simply Yellow, because you will get this exception: org.codehaus.groovy.runtime.typehandling.GroovyCastException: Cannot cast object 'Yellow' with class 'java.lang.String' to class 'java.awt.Color'.
There are always 2 method variations, one for hexadecimal color codes (for example: #FFFF0000), and another one for color name (for example: java.awt.Color.YELLOW). 
Make sure you pick the correct one. For hexadecimal color codes the method ends with "ColorCode";  for color name, the method ends with "Color".
