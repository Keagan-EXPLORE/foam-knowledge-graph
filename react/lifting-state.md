---
title: lifting-state
type: react
date created: 15/07/2021
tags: state-management 
---
## Explanation
- Lifting state is how you state between two sibling components. 
- Find the lowest common parent shared between the two components and place the state management there, and then pass the state and a mechanism for updating that state down into the components that need it.
- This should only be done when state is shared between components. If there is only one component using the state, keep the state in the component as this will improve performance and allow for easier maintenance.
## Code example

In the code below, the `Name` component represents state only used by one component and therefore kept in it. The `FavoriteAnimal` and `Display` components both make use of the animal state, which is therefore lifted by keeping it in the lowest common parent shared between the two, which is the `App` component. 
```
function Name() {
  const [name, setName] = React.useState('')
  return (
    <div>
      <label htmlFor="name">Name: </label>
      <input
        id="name"
        value={name}
        onChange={event => setName(event.target.value)}
      />
    </div>
  )
}

function FavoriteAnimal({animal, onAnimalChange}) {
  return (
    <div>
      <label htmlFor="animal">Favorite Animal: </label>
      <input id="animal" value={animal} onChange={onAnimalChange} />
    </div>
  )
}

function Display({animal}) {
  return <div>{`Your favorite animal is: ${animal}!`}</div>
}

function App() {
  const [animal, setAnimal] = React.useState('')
  return (
    <form>
      <Name />
      <FavoriteAnimal
        animal={animal}
        onAnimalChange={event => setAnimal(event.target.value)}
      />
      <Display animal={animal} />
    </form>
  )
}

export default App

```

## Resources
- [Lifting state](https://reactjs.org/docs/lifting-state-up.html) 
- [State colocation](https://kentcdodds.com/blog/state-colocation-will-make-your-react-app-faster)