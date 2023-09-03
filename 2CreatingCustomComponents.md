# creating custom components

- Follow the naming convention similar to app component
  - component file name should ne like componentname.component.ts or componentname.component.html
  - in the .ts file, make sure to name the class to be exported as ComponentnameComponent

```typescript
import { Component } from "@angular/core";

@Component({
  //decorate the class with @Component and supply the below values
  selector: "app-server", //this becouse the custom component tag which can be used in src/app/app.component.html file.
  templateUrl: "./server.component.html",
})
export class ServerComponent {}
```

- Register the custom component in src/app.module.ts file

```typeScript
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import {FormsModule} from '@angular/forms';

import { AppComponent } from './app.component';
import {ServerComponent} from './server/server.component';//new custom component where ServerComponent is the class from src/app/server/server.component

@NgModule({
  declarations: [
    AppComponent,
    ServerComponent //register newly created component here.

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
