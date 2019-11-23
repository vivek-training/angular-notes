# Topic 7: Property Binding

1. In a parent-child component hierarchy, the child receives the data from the parent via **property binding** (aka input property binding)
2. First, the child would expose the fields that it wishes to receive from the parent by decorating the field by `@Input()`
3. Then, the parent can pass the data by `<app-child [prop]="parentField"></app-child>`
4. Please note that `[prop]="..."` takes an expression
5. If you want to pass a literal value, make sure you surround them with quotes as `[prop]=" '... '"` or drop the square-brackets for the property as `prop="literal value from parent"`
6. When the parent passed the values to the child, Angular will invoke `ngOnChanges()` life-cycle hook. This takes an argument of `SimpleChanges`. The order is `constructor > ngOnChanges > ngOnInit`.
7. Also, we can expose a setter via `@Input()` instead of a field
8. Please refer to different branches of <https://github.com/vivekanandpv/angular-property-binding>
