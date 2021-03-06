---
id: code-splitting
title: Code-Splitting
hide_title: true
sidebar_label: Code-Splitting
---
 
# Code-Splitting
Reducers and epics are part of your React components. You can use [React.lazy()](https://reactjs.org/docs/code-splitting.html) to implement code-splitting.  
Check [Code-Splitting](/introduction/examples#code-splitting) for full working example.

#### Example


```tsx
// src/features/foo/module.tsx

import { useModule } from './interface'

export default function FooModule() {
  useModule();

  return <FooView />;
}

// components/MyComponent.tsx
const Foo = React.lazy(() => import('src/features/foo/module'));

export function MyComponent() {
  const { showFoo } = useMappedState(state => state.showFoo);

  if (showFoo) {
    return <Foo />;
  }
  return <div>Foo hidden</div>;
}
```

