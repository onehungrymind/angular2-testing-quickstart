---
title: Simple Component 
position: 1.1
description: Test a component with Angular's testing utilities
video_id: 1j5bqrhc65
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
  {: title="Component"}
  
  ~~~ typescript
  import { ComponentFixture, TestBed } from '@angular/core/testing';
  import { By } from '@angular/platform-browser';
  import { DebugElement } from '@angular/core';
  
  import { SimpleComponent } from './simple.component';
  
  describe('SimpleComponent', () => {
    let component: SimpleComponent;
    let fixture: ComponentFixture<SimpleComponent>;
    let de: DebugElement;
  
    beforeEach(() => {
      fixture = TestBed.configureTestingModule({
        declarations: [ SimpleComponent ]
      })
      .createComponent(SimpleComponent);
  
      component = fixture.componentInstance;
      de = fixture.debugElement;
      fixture.detectChanges();
    });
  
    it('sets `subject` to `world` by default', () => {
      expect(component.subject).toBe('world');
    });
  
    it('greets the subject', () => {
      const h1 = de.query(By.css('h1'));
      expect(h1.nativeElement.innerText).toBe('Hello world!');
    });
  
    it('updates the subject', () => {
      component.subject = 'developer';
      fixture.detectChanges();
      const h1 = de.query(By.css('h1'));
      expect(h1.nativeElement.innerText).toBe('Hello developer!');
    });
  });
  ~~~
  {: title="Spec"}
---

Bacon ipsum dolor amet chuck short ribs t-bone tenderloin. Meatloaf rump alcatra swine filet mignon corned beef tongue leberkas tail salami shoulder venison strip steak shankle hamburger. Pork loin leberkas brisket, frankfurter pig corned beef tongue beef ribs swine jerky tenderloin. Andouille brisket swine, jowl cow jerky kevin sausage.
