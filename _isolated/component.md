---
title: Component
position: 2
description: Test a component class
right_code: |
  ~~~ typescript
  import { Component, OnInit } from '@angular/core';
  
  @Component({
    selector: 'app-simple',
    template: '<h1>Hello {{subject}}!</h1>'
  })
  export class SimpleComponent implements OnInit {
    subject: string = 'world';
    constructor() { }
    ngOnInit() { }
  }
  ~~~
  {: title="Component" }

  ~~~ typescript
  import { SimpleComponent } from './simple.component';
  
  describe('SimpleComponent', () => {
    let component: SimpleComponent;
  
    beforeEach(() => component = new SimpleComponent());
  
    it('sets the `subject` class member', () => {
      expect(component.subject).toBe('world');
    });
  });
  ~~~
  {: title="Spec" }
---

Bacon ipsum dolor amet chuck short ribs t-bone tenderloin. Meatloaf rump alcatra swine filet mignon corned beef tongue leberkas tail salami shoulder venison strip steak shankle hamburger. Pork loin leberkas brisket, frankfurter pig corned beef tongue beef ribs swine jerky tenderloin. Andouille brisket swine, jowl cow jerky kevin sausage.
