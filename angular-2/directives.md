---
tags:
  - directives
  - angular2
  - ngFor
  - ngIf
---

# Directives

## Structural Directives

interact with current vi

### ngFor

Loop through list and repeat creating a tag that is attached

```html
<div>
    <ul>
        <li *ngFor="let value of values">{{ value }}</li>
    </ul>
</div>
```



