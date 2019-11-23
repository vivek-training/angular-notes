# Topic 6: Component Life-cycle Introduction

1. When Angular sees the components being referred to in the templates such as `<app-x></app-x>`, it will create the components out of the class we wrote. Components thus created in memory will go through several changes before they are destroyed. This process is called the **component life-cycle**.
2. Since we are not in control of component creation out of the class, Angular gives us timely notifications about what it is doing as far as the component is concerned.
3. This information is relayed to us by form of life-cycle methods or life-cycle hooks. Essentially, we provide standard methods for Angular and when something in the component's life-cycle happens, Angular will call these methods, sometimes with suitable arguments.
4. This way, we come to know what's happening with the component or in what stage it presently is. Based on this knowledge, we can take appropriate actions.
5. In this introduction, we are going to take a look at `constructor` and `ngOnInit()`.
6. Before anything, (well, after all the fields of the class are created) the constructor is called. Please note that it is not yet an Angular component, but a mere TS class. Constructor call will create a class object for Angular. Then, the decorator is read and template is connected.
7. After the connection, the template is read from top to bottom by Angular. All the value binding is done (fields are already kept ready in the object).
8. Once Angular finishes the rendering of the component, it will notify us by calling `ngOnInit()` life-cycle method. Conventionally it comes from OnInit interface.
9. It is considered a good practice to implement the `OnInit` interface, even though `ngOnInit` will work without it. Read here: <https://github.com/angular/angular/issues/5814>
10. So, we have `constructor` followed by `ngOnInit`
11. Please refer to on-init-life-cycle branch of : <https://github.com/vivekanandpv/angular-value-binding>
