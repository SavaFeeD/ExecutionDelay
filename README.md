# ExecutionDelay

Defer user input

## How use

```bash
npm i execution-delay
```

### Model

```js
/**
 * Create a delay for the function to fire until the user completes all actions with the task
 */
export declare class ExecutionDelay {
    private static tasks;
    /**
     * Creates a task if there was no task with the name {taskName} and adds a new subtask {action} to the task for which {delay}ms is given.
     * @param {String} taskName
     * @param {Function} action
     * @param {Number} delay (default 1500)
     */
    static add(taskName: string, action: Function, delay?: number): void;
    private static createNewTask;
    private static getQueueLastIndex;
    private static getLastActionFromQueue;
    private static clearTask;
}
```

### Example

```js
import ExecutionDelay from 'execution-delay';

const taskName = 'action';
const optionalDelayMs = 300;
function action() {
  ...
}

[1, 2, 3, 4, 5].forEach(() => {
  ExecutionDelay.add(taskName, action, optionalDelayMs);
  // out of five iterations, only the last action will be performed
});
```