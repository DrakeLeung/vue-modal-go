## Options
| Prop                          | Type     | Default | Description                              | 
| -----                         | -----    | ------- | -----------                              |     
| `is-open`                       | Boolean  | `false`   | show/close modal                         |
| `close-timeout-ms`              | Number   | `-1000`   | auto close modal in specified milesecond |
| `should-close-on-overlay-click` | Boolean  | `false`   | click the overlay, and close modal       |
| `on-request-close`              | Function |         | call functions when closing modal         |
| `custom-style`                  | Object   |  ?      | customize some default sytle             |

### custom-style
```javascript
{
  backgroundColor: '#fff',
  padding: '20px',
  borderRadius: '2px',
  overlayBackgroundColor: 'rgba(0, 0, 0, 0.3)',
}
```

### close-timeout-ms
if value is `<= 0`, it won't close the modal.