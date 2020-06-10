# 手动更新和移除

- order: 7

:::lang=en-us
# Manual to update destroy

- order: 7

First dialog
:::
---

```jsx
import { Dialog, Button } from '@alifd/next';

function countDown() {
  let secondsToGo = 5;
  const dialog = Dialog.confirm({
    title: 'This is a notification message',
    content: `This dialog will be destroyed after ${secondsToGo} second.`,
  });
  const timer = setInterval(() => {
    secondsToGo -= 1;
    dialog.update({
      content: `This dialog will be destroyed after ${secondsToGo} second.`,
    });
  }, 1000);
  setTimeout(() => {
    clearInterval(timer);
    dialog.hide();
  }, secondsToGo * 1000);
}

ReactDOM.render(<Button onClick={countDown}>Open dialog to close in 5s</Button>, mountNode);

```