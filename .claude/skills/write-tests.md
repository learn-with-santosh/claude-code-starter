---
name: write-tests
description: Generate unit and integration tests for existing code. Triggers on "write tests", "add tests", "test this", "test coverage", "jest".
allowed-tools: Read, Write, Glob
---

# Write Tests Skill

## Process
1. Read the target file fully
2. Identify all exported functions, methods, or components
3. List edge cases: happy path, empty input, null, errors, boundaries
4. Write tests using Jest

## Angular Component Test Template
```typescript
import { ComponentFixture, TestBed } from '@angular/core/testing';
import { <ComponentName> } from './<component>.component';

describe('<ComponentName>', () => {
  let component: <ComponentName>;
  let fixture: ComponentFixture<<ComponentName>>;

  beforeEach(async () => {
    await TestBed.configureTestingModule({
      imports: [<ComponentName>]
    }).compileComponents();

    fixture = TestBed.createComponent(<ComponentName>);
    component = fixture.componentInstance;
    fixture.detectChanges();
  });

  it('should create', () => {
    expect(component).toBeTruthy();
  });

  // TODO: add feature-specific tests
});
```

## Node.js Service Test Template
```typescript
import { <ServiceName> } from './<service>';

describe('<ServiceName>', () => {
  let service: <ServiceName>;

  beforeEach(() => {
    service = new <ServiceName>();
  });

  describe('<methodName>', () => {
    it('should <expected behavior>', async () => {
      const result = await service.<method>(<input>);
      expect(result).toEqual(<expected>);
    });

    it('should throw when <edge case>', async () => {
      await expect(service.<method>(null)).rejects.toThrow();
    });
  });
});
```

## Coverage Target
- Aim for 80%+ coverage on services and utils
- Components: at least creation + key interactions tested
