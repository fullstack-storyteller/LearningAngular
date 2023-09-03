# Order of Execution in Angular

- It starts from `src/main.ts`. Remember the `src/index.html` file is the one file which going to be shown to the end user and angular will dynamically update the DOM

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>MyFirstApp</title>
    <base href="/" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link rel="icon" type="image/x-icon" href="favicon.ico" />
  </head>
  <body>
    <app-root></app-root>
    <!--This app-root is the html like tag which will be programmatically update by the angular framework-->
  </body>
</html>
```

```TypeScript
//main.ts

import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

import { AppModule } from './app/app.module';


platformBrowserDynamic().bootstrapModule(AppModule)
  .catch(err => console.error(err)); //this is importan line
```

- When AppModule is bootstrapped, it calls the `src/app/app.module.ts`

```TypeScript
//src/app/app.module.ts

import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import {FormsModule} from '@angular/forms';

import { AppComponent } from './app.component'; //calling the actual app component

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

- When AppComponent is loaded, `src/app/app.component.ts` is called and in this file inself we define the styling and html template of this component.

```TypeScript
//src/app/app.component.ts


import { Component } from '@angular/core';

@Component({
  selector: 'app-root', //this will become the html tag which is used in src/index.html file to render the application
  templateUrl: './app.component.html', //html code for this component
  styleUrls: ['./app.component.css'] //styling for this component
})
export class AppComponent {
  title = `Manish's First App`;
  dynamicName = 'Manish'
}
```
