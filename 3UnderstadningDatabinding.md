# Understanding Databinding

- Typescript code ----------(Output Data)-----------> Template (HTML)

  - string interpolation ( `{{ data }}`). Remeber that the string interpolation expression has to resolve to a string at the end.
  - property binding (`[property]="data"`)

- Typescript code <---------(React to User Events)----------- Template (HTML)

  - Event Binding ( `(event)="expression"` )

- Combining both: Two way binding ( `[(ngModel)]="data"` )
