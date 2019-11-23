# Topic 11: Template References

1. An element in the template can be referred to by a template reference variable as `<p #tr>something</p>`
2. Here, we can use tr to refer this p tag inside the template
3. If we want to access this tr in component class, we can do so by using `@ViewChild('tr') referenceToP: ElementRef`
4. Please note the `'tr'` being passed to `@ViewChild()`. This is necessary. Also, notice the `ElementRef` type annotation applied. If template reference is applied to a component, we can use `ComponentRef`.
5. The interesting point is, `@VieChild` will not bind the template reference to the field when the component is rendered. So, if we try to use the referenceToP either in constructor or ngOnInit, we get undefined.
6. The reason is, template references can appear in any order inside the template. So the entire template must be first rendered to create a kind of virtual table of the template references used. This is done after the Angular finished rendering the view. When the rendering of the view is finished, Angular notifies the component by calling `ngAfterViewInit()` life-cycle method.
7. Thus, we have the order of component life-cycle as (so far): `constructor > ngOnChanges > ngOnInit > ngAfterViewInit`
8. `ElementRef` exposes the `nativeElement` property which is the handle for the actual DOM node. We can manipulate the node (set style etc) using this.
9. Please refer to different branches in <https://github.com/vivekanandpv/angular-templates>
