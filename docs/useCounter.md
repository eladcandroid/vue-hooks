# useCounter

Vue hook that tracks a numeric value.

## Usage

```jsx {6,17}
import { createComponent } from 'vue-function-api';
import { useCounter } from '@u3u/vue-hooks';

const Demo = createComponent({
  setup() {
    const [count, { inc, dec, set, reset }] = useCounter();
    return {
      count,
      inc,
      dec,
      set,
      reset,
    };
  },

  render() {
    const { count, inc, dec, set, reset } = this;
    return (
      <div>
        <div>count: {count}</div>
        <button onClick={() => inc()}>Increment</button>
        <button onClick={() => dec()}>Decrement</button>
        <button onClick={() => inc(5)}>Increment (+5)</button>
        <button onClick={() => dec(5)}>Decrement (-5)</button>
        <button onClick={() => set(100)}>Set (100)</button>
        <button onClick={() => reset()}>Reset</button>
        <button onClick={() => reset(25)}>Reset (25)</button>
      </div>
    );
  },
});
```

## Reference

```typescript {6-10}
function useCounter(
  initialValue?: number,
): [
  Wrapper<number>,
  {
    inc: (delta?: number) => number;
    dec: (delta?: number) => number;
    get: () => number;
    set: (val: number) => number;
    reset: (val?: number) => number;
  },
];
```

### `Arguments`

- `initialValue`

  Initial value of the counter.

  - Type: `number`
  - Default: `0`

### `ReturnValue`

0. [`Wrapper<number>`](https://github.com/vuejs/vue-function-api/blob/1d532fe684e2343973ae46fc3ef93e497e6514b1/src/wrappers/index.ts#L5-L7)
1. `Actions`