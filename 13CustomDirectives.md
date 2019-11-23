# Topic 13: Custom Directives

1. We use `ng g d custom-directive` to create a new directive. As it stands, it could be both an attribute and a structural directive. Let's start by understanding the attribute directives
2. Directives are components without the template, they say. They have `@Directive` decorator. They also have a selector, which usually starts with app. It is not recommended to change the selector.
3. Directives can declare Input properties and Output events just like components.
4. Property binding to directive's property is exactly as it happens with components as in `[prop]="expression"`
5. In addition, a directive can declare an input property with the same name as its selector. In such case, the property binding and attribute application is done in one step as in `[appCustom]="expression"`
6. An element or a component that applies a directive is called as the host for that directive
7. Directive can bind to host's properties by `@HostBinding('property') field`
8. Directive can bind to host's events by `@HostListener('event') handler() {...}`
9. There are as many directive instances as it is applied. So each application has its own instance.
10. Directive instance is created after the host element or component is created. Therefore, this host is available for dependency injection in directive's constructor.
11. Structural directive actually rewrites the host using `ng-template`. But `ng-template` is a pseudo element, meaning it cannot be rendered unless explicitly instructed. Inside the structural directive's constructor, we take a `TemplateRef<any>` (reference to the `ng-template`) and `ViewContainerRef` (reference to the whole component's template). Then, we call `createEmbeddedView` on `ViewContainerRef` passing the `TemplateRef`.
12. Please refer to different branches of <https://github.com/vivekanandpv/angular-custom-directives>
