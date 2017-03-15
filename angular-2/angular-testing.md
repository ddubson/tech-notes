# Angular 2 Testing

## Component Testing Example

Before the test suite runs:

```
import {TestBed} from "@angular/core/testing";
import {BrowserDynamicTestingModule, platformBrowserDynamicTesting} from "@angular/platform-browser-dynamic/testing";

TestBed.initTestEnvironment( BrowserDynamicTestingModule, platformBrowserDynamicTesting() );
```

The following tests an Form input and submission, and mocks a service that triggers an action based on the submit:

```typescript
import {TestBed, ComponentFixture, ComponentFixtureAutoDetect} from "@angular/core/testing";
import {By} from "@angular/platform-browser";
import {Observable} from "rxjs";
import {ReactiveFormsModule} from "@angular/forms";

describe("Component: SomeForm", () => {
  let component: SomeForm;
  let fixture: ComponentFixture<SomeForm>;

  beforeEach(() => {
    let SomeServiceSpy = {
      addModel: jasmine.createSpy('createModel').and.returnValue(Observable.of(SomeService)),
    };

    TestBed.configureTestingModule({
      declarations: [SomeForm],
      providers: [
        { provide: SomeService, useValue: SomeServiceSpy},
        { provide: ComponentFixtureAutoDetect, useValue: true}
      ],
      imports: [
        ReactiveFormsModule,
      ],
    });

    fixture = TestBed.createComponent(SomeForm);
    component = fixture.componentInstance;
  });

  describe("create a model", () => {
    it("calls createModel in SomeService", () => {
      // In the 'input' text field, set it to 'Hello'
      const inputCtrl = fixture.debugElement.query(By.css("input")).nativeElement;
      inputCtrl.value= "Hello";
      
      // Dispatch the event for the 'input' text
      inputCtrl.dispatchEvent(new Event("input"));
      
      // Important! make sure Angular is aware of the form changes.
      fixture.detectChanges();

    
      fixture.debugElement.query(By.css("form")).triggerEventHandler("submit", null);
      fixture.detectChanges();

      const someServiceSpy = fixture.debugElement.injector.get(SomeService);
      expect(someServiceSpy.createModel).toHaveBeenCalledWith("Hello");
    });
  });
});
```



