---
layout: docs
---

# Popups: Confirmation Window
Method `confirm()` shows new confirmation window.


## Syntax
```javascript
AWN.confirm([message,onOk,onCancel,options])
```
### Parameters
{% include param-desc.md optional=true name="message" desc="
  Defines message of the confirmation window. Can be any valid HTML or text string.
"%}
{% include param-desc.md optional=true name="onOk" desc="
  Defines `Function`, which will be executed on click to 'OK' button.
"%}
{% include param-desc.md optional=true name="onCancel" desc="
  Defines `Function`, which will be executed on click to 'Cancel' button.
"%}
{% include param-desc.md optional=true name="options" desc="
  [Instance of Options](/awesome-notifications/docs/customization/), which will override globals for this call
"%}

### Return value
A new [HTMLElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) instance

### Behaviour
Confirmation window can be closed only by clicking to one of two buttons.

## Examples

{% include awn-example.md js="new AWN().confirm()" label="Use defaults" %}
{% include awn-example.md js="
  let notifier = new AWN();
  let onOk = () => {notifier.info('You pressed OK')};
  let onCancel = () => {notifier.info('You pressed Cancel')};
  notifier.confirm(
    'Are you sure?',
    onOk,
    onCancel,
    {
      labels: {
        confirm: 'Dangerous action'
      }
    }
  )
" label="Use custom" %}