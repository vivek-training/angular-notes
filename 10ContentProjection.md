# Topic 10: Content Projection

1. Parent can communicate with child by property binding to the input properties exposed by the chid
2. But parent cannot pass a strctured HTML content to the child via property binding
3. Therefore, the content projection mechanism is used
4. Parent will send the structured content inside the child selector as `<app-child><h2>Hi</h2></app-child>`
5. Child cannot modify this content, but can decide where to place this projected content (if at all it wants) by using a special psuedo selector provided by Angular called: `<ng-content></ng-content>`
6. Please refer to 00-content-projection branch of <https://github.com/vivekanandpv/angular-templates>
