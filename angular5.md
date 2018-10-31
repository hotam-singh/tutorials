# Angular 5

## Angular components
The page you see is the application shell. The shell is controlled by an Angular component named AppComponent.

Components are the fundamental building blocks of Angular applications. They display data on the screen, listen for user input, and take action based on that input.

```typescript
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-users',
  templateUrl: './users.component.html',
  styleUrls: ['./users.component.css']
})
export class UsersComponent implements OnInit {

  constructor() { }

  ngOnInit() {
  }

}
```
You always import the `Component` symbol from the Angular core library.

`@Component` is a decorator function that specifies the Angular metadata for the component.

**Note: ** The CLI generated three metadata properties:

selector— the component's CSS element selector
templateUrl— the location of the component's template file.
styleUrls— the location of the component's private CSS styles.