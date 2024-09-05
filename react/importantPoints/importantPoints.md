# From react documentation

## Describing the UI

- Returnning null
- Do not place number in curly braces, wrong `{arr.length && <h1>Raj</h1>}` right `{arr.length > 0 && <h1>Raj</h1>}`
- Variable can contain jsx
- Do not return large jsx conditionally, use variables instead
- Fragments disappear from the dom alowing to create flat list if element
- Index key may lead yon subtle and confusing bugs
- Using one foreach is better than two filters
- Pure functions - same input same output, should not change obj variables that existed before rerendering

## Adding interactivity

- `<button onClick={handleClick()}>` it will cause function to run immediately when component renders beacuse we are calling it inside of curly braces
- in case of button name pass it as a children not as a props
- Events propagate upwards. Call `e.stopPropagation()` on the first argument to prevent that.
- do not define `usestate` using if else
- render && commit
- React processes state updates after event handlers have finished running. This is called batching.
- To update some state multiple times in one event, you can use setNumber(n => n + 1) updater function.
- Using a single event handler for multiple fields

```import { useState } from 'react';

export default function Form() {
  const [person, setPerson] = useState({
    firstName: 'Barbara',
    lastName: 'Hepworth',
    email: 'bhepworth@sculpture.com'
  });

  function handleChange(e) {
    setPerson({
      ...person,
      [e.target.name]: e.target.value
    });
  }

  return (
    <>
      <label>
        First name:
        <input
          name="firstName"
          value={person.firstName}
          onChange={handleChange}
        />
      </label>
      <label>
        Last name:
        <input
          name="lastName"
          value={person.lastName}
          onChange={handleChange}
        />
      </label>
      <label>
        Email:
        <input
          name="email"
          value={person.email}
          onChange={handleChange}
        />
      </label>
      <p>
        {person.firstName}{' '}
        {person.lastName}{' '}
        ({person.email})
      </p>
    </>
  );
}
```

- how to change nested obj's

```setPerson({
  ...person, // Copy other fields
  artwork: { // but replace the artwork
    ...person.artwork, // with the same one
    city: 'New Delhi' // but in New Delhi!
  }
});
```

- understand use emmer

```
import { useImmer } from 'use-immer';
import Background from './Background.js';
import Box from './Box.js';

const initialPosition = {
  x: 0,
  y: 0
};

export default function Canvas() {
  const [shape, updateShape] = useImmer({
    color: 'orange',
    position: initialPosition
  });

  function handleMove(dx, dy) {
    updateShape(draft => {
      draft.position.x += dx;
      draft.position.y += dy;
    });
  }

  function handleColorChange(e) {
    updateShape(draft => {
      draft.color = e.target.value;
    });
  }

  return (
    <>
      <select
        value={shape.color}
        onChange={handleColorChange}
      >
        <option value="orange">orange</option>
        <option value="lightpink">lightpink</option>
        <option value="aliceblue">aliceblue</option>
      </select>
      <Background
        position={initialPosition}
      />
      <Box
        color={shape.color}
        position={shape.position}
        onMove={handleMove}
      >
        Drag me!
      </Box>
    </>
  );
}

```

- how to perform shift in array

```
setArtists([
      ...artists // Put old items at the start
  { id: nextId++, name: name },
]);
```

- in order to replace item in array use map

```
import { useState } from 'react';

let initialCounters = [
  0, 0, 0
];

export default function CounterList() {
  const [counters, setCounters] = useState(
    initialCounters
  );

  function handleIncrementClick(index) {
    const nextCounters = counters.map((c, i) => {
      if (i === index) {
        // Increment the clicked counter
        return c + 1;
      } else {
        // The rest haven't changed
        return c;
      }
    });
    setCounters(nextCounters);
  }

  return (
    <ul>
      {counters.map((counter, i) => (
        <li key={i}>
          {counter}
          <button onClick={() => {
            handleIncrementClick(i);
          }}>+1</button>
        </li>
      ))}
    </ul>
  );
}

```

- how to insert in array

```
import { useState } from 'react';

let nextId = 3;
const initialArtists = [
  { id: 0, name: 'Marta Colvin Andrade' },
  { id: 1, name: 'Lamidi Olonade Fakeye'},
  { id: 2, name: 'Louise Nevelson'},
];

export default function List() {
  const [name, setName] = useState('');
  const [artists, setArtists] = useState(
    initialArtists
  );

  function handleClick() {
    const insertAt = 1; // Could be any index
    const nextArtists = [
      // Items before the insertion point:
      ...artists.slice(0, insertAt),
      // New item:
      { id: nextId++, name: name },
      // Items after the insertion point:
      ...artists.slice(insertAt)
    ];
    setArtists(nextArtists);
    setName('');
  }

  return (
    <>
      <h1>Inspiring sculptors:</h1>
      <input
        value={name}
        onChange={e => setName(e.target.value)}
      />
      <button onClick={handleClick}>
        Insert
      </button>
      <ul>
        {artists.map(artist => (
          <li key={artist.id}>{artist.name}</li>
        ))}
      </ul>
    </>
  );
}

```

- but in case of reverse and sort copy the array first the call setter function with the copied element

- arrays of object does not containe actual objects they contains reference of object veriables, 

```
const myNextList = [...myList];
const artwork = myNextList.find(a => a.id === artworkId);
artwork.seen = nextSeen; // Problem: mutates an existing item
setMyList(myNextList);
instead use this
```
```
setMyList(myList.map(artwork => {
  if (artwork.id === artworkId) {
    // Create a *new* object with changes
    return { ...artwork, seen: nextSeen };
  } else {
    // No changes
    return artwork;
  }
}));
```

- check use immer again

- useReducer

Here's a comparison table between `useState` and `useReducer` hooks in React:

| Feature                      | `useState`                                     | `useReducer`                                    |
|-------------------------------|-----------------------------------------------|-------------------------------------------------|
| **Basic Use Case**            | Manages simple state values (e.g., strings, numbers, booleans) | Manages more complex state or state transitions |
| **Signature**                 | `const [state, setState] = useState(initialState);` | `const [state, dispatch] = useReducer(reducer, initialState);` |
| **State Update Trigger**      | Function (`setState`)                         | Dispatch action (`dispatch({type, payload})`)   |
| **When to Use**               | Simple state updates, independent state changes | Complex state logic, interdependent state changes, or multiple sub-values of state |
| **State Structure**           | Typically one state value                    | Can handle a complex object or multiple state values |
| **Reducer Function**          | Not required                                  | Requires a reducer function to handle state transitions based on actions |
| **Action Dispatching**        | Not applicable                                | Requires dispatching actions to update state    |
| **Performance Optimization**  | Better suited for simpler and less frequent state updates | Suited for complex state logic, can avoid unnecessary re-renders with careful management |
| **Debugging**                 | Easy to trace state changes through direct state updates | Requires understanding of action types and reducer logic |
| **Third-party Libraries**     | Not typically necessary                       | Often used with libraries like Redux for complex state management |
| **Example Use Case**          | Toggling a boolean, form input management     | Managing a shopping cart, complex form with multiple fields |



