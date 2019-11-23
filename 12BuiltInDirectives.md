# Topic 12: Angular Built-in Directives

1. In Angular a directive is a command to accomplish something in the template. It could be to change the style, set the behavior, etc.
2. In Angular, the directives are of two types: **attribute directives** and **structural directives**. Angular has a rich set of built-in directives (both types).
3. In HTML, an element has attributes and DOM properties. Attribute sets the initial property. But during the life-time of the element, its property keeps changing. In this regard, an attribute can be considered as the command to instruct the DOM about an element's state (property).
4. Usually, there is a one-to-one mapping of attributes and properties in DOM. But not always.
5. Angular directives are special in the sense that they let us manipulate the underlying state of the element in the DOM. Threfore, we can control the elements in the run-time.
6. Let's consider the `[ngClass]` directive, which takes an expression to set the css class of the element. This expression could be a string, an array of strings, or a config object (key is the css class and value is the boolean). If the expression is changed during the runtime, Angular changes the actual DOM properties thus creating the direct access tunnel.
7. Structural directive lets us add DOM nodes based on some expression. Structural directives are prefixed with \*
8. Consider the conditional rendering by `*ngIf="expression"` or list rendering by `*ngFor="expression"`
9. Also, consider how `[ngSwitch]="expression"` directive works with `*ngSwitchCase` and `*ngSwitchDefault` structural directives.
10. Please note the use of `<ng-container>` pseudo selector and how it could be used instead of a real selector such as a `<div>`
11. Refer to different branches of <https://github.com/vivekanandpv/angular-built-in-directives>
