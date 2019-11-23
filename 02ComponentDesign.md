# Topic 2: Components Primer

1. To create a component, `ng g c my-comp` or `ng generate component my-comp`.
2. This creates by default a component directory (my-comp) under the app directory. All the component files (class, template, style, and test) are put into this directory.
3. This component has a selector app-my-comp, template called my-app.component.html, style called my-app.component.css, and test called my-app.component.spec.ts
4. As discussed earlier, do not change the selector.
5. By default there is `<p>my-comp works!</p>` in the template
6. Next, we are going to make use of this component in out root component (AppComponent)
7. Inside the template of app.component.html, remove everything and place `<app-my-comp></app-my-comp>`
8. This is the idea of component composition. We now say the App component composes of MyComp (when we say ng g c my-comp, the class is created by the name MyComp, thus PascalCasing the component class).
9. This way, the App becomes the parent of the MyComp. Or MyComp is the child of App. Hierarchy thus set can go very deep.
10. The parent is in full control of the child because it is the one that's rendering the child in its own template. But the child doesn't know its parent. It is like any class hierarchy in object-oriented design (Java or C#).
11. Down the line, a component can become child of multiple parent components. This is the reason we need to pay attention to make the components as reusable as possible.
12. Also, we should know that down the line, not all components are in parent-child relationship. If AppComponent has two children say Navbar and PageHolder, these two components in turn have no parent-child relationship. They are peer components. Knowing these different kinds of component relationships is criticcal when it comes to state-management (the way data flows to and from the components). More on this will be discussed later.
