# Topic 4: Pipes

1. Pipes allow us to format the output of a value bound expression. For example, `{{ title | uppercase }}` or `{{ today | date:'dd-MM-yyyy' }}` or `{{ amount | currency:'INR' }}`
2. Here, `uppercase`, `date`, `currency` are pipes
3. Pipes are declarable classes that need to implement PipeTransform interface. This interface has one method called `transform(value: any, ...args: any[]): any`
4. Here, value is the expression to which the pipe is applied. In the examples we say today becomes the value parameter for date pipe. If the pipe needs additional arguments, they are passed as comma separated string fragments after a colon. Take a look at the date and currency pipe examples. When we say ...args we make use of the JavaScript's rest parameter syntax (More info: <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters).>
5. If we want to pass multiple arguments, they have to be comma separated inside a string as `{{ value | pipe:'arg1, arg2, arg3'}}`. Only one string is allowed.
6. In order to create a custom pipe, we use `ng g p custom-pipe`. This scaffolds a pipe class and a test class. Pipes have @Pipe() decorator. We have name, which is the identifier for our pipe. Pipes do not have templates. This command automatically updates the declarations array of AppModule metadata.
7. Please refer to the angular-pipes repo <https://github.com/vivekanandpv/angular-pipes>. Please take a look at the implementation of the custom-pipe
8. The above project makes use of a custom pipe which can be applied to any value of any type. But it is generally recommended to make custom pipes type safe. We replace any with specific types in such cases. Then, if the pipe is applied to wrong value type, there will be an error.
9. Pipes can be chained, meaning, one pipe's output can become another's value parameter. For example: `{{ today | date:'long' | uppercase }}`. Be careful while chaining the pipes as some pipes are type-specific. Date cannot be applied to a string. Strangely, date pipe, if applied to any number will default to Jan 1, 1970!
10. Pipes are by default `pure`. This means the pipe's `transform()` method is called only if the value which applied this pipe undergoes a change. On the other hand, we can add `pure: false` property to `@Pipe()`, which makes it an impure pipe. An impure pipe is called during every change detection cycle on the component. Impure pipes are resource intensive and if used without the knowledge of the implications, they bring down the performance of the app. Thus the default is a pure pipe. One often used (somewhat justifiably) is the built-in `json` pipe (applied to objects to get their string representation). This is made impure because, pure pipe mechanism will not detect the object mutation. For more information, please read <https://angular.io/guide/pipes#pure-and-impure-pipes>