# Topic 3: Value Binding

1. The component class and its template are connected by Angular platform object (created by the runtime).
2. In value binding, we are going to leverage this connection to achieve the data-binding between the component and the template.
3. Conventionally, the template is the representative of the DOM (Document Object Model, or the in-memory representation of the HTML in browser)
4. So, we can say, through value binding, we are creating a one-way data binding from component to the DOM
5. The procedure is to create a field (which is a data element) in the component and use double brace syntax in the template to bind to the field. In template, it looks like: `<h2>Title is: {{ field }}</h2>`
6. We can also declare a method in the class which returns say a string and in the value binding, we can call the method as `<h2>Title is: {{ foo() }}</h2>`
7. The double-brace syntax used here is conventionally called as string-interpolation operator
8. It can also be used to set HTML attributes as `<input type="text" value="{{ field }}" />`
9. We cannot place a literal value inside the string-interpolation operator such as `{{ This is my title }}`
10. The string-interpolation operator considers there is an expression inside. It will be evaluated before outputting. Therefore `{{ foo() }}` will actually call the method foo() and the return value will be output.
11. This can also be leveraged as `{{ 100 + 200 }}` or, `{{ boolField ? 'Yes' : 'No' }}`.
12. Assignment of anytime is not allowed inside the value-binding. Therefore `{{ value++ }}` or `{{ value = a + 1 }}`, or `{{ value = new Date() }}` are illegal.
13. If we really want to output a literal, it should be surrounded with quotes as `{{ 'This is my title' }}`
14. Using `new` operator is not allowed, but an object literal is allowed such as `{{ { name: 'Arun' } }}`. (This example cannot output the object's string representation, but merely outputs `[object Object]`. We ought to use proper pipes to get the required output. More on that later).
