---
title: useEffect-hook
type: react
date created: 14/07/2021
tags: react-hooks
---

## Explanation
- Used to run custom code after a react component renders or re-renders
- Requires 2 arguments: First, the code to run on re-rendering, second, an array of variables to watch so that the hook is only executed if one of those dependencies change. 

## Code example

```
React.useEffect(() => {
    window.localStorage.setItem('name', name) 
  }, [name, state])

  return [state, setState]
}
```

## tags
[[react-hooks]]