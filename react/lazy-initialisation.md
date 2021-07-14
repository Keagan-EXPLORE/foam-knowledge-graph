---
title: lazy-initialisation
type: react
date created: 14/07/2021
---
## Explanation
- Instead of simply passing a value to the [[useState-hook]], lazy initialisation means that you pass a function that returns the initial value. 
- Why? If the initial value is computationally expensive e.g. fetching it from local storage, lazy initialisation is a good option. If the value is just passed, it is called on every single render. With lazy initialisation, the function is only executed when needed. Since the **useState hook only needs the initial value at the first render**, the function won't be called again. 

## Code example
```
// Instead of just passing in the initial value from local storage, a function is passed. 
const [state, setState] = React.useState(() => window.localStorage.getItem(key)
```

## Further reading
[useState lazy initialization and function updates](https://kentcdodds.com/blog/use-state-lazy-initialization-and-function-updates) by [[Kent C. Dodds]]
