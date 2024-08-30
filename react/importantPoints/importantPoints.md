# From react documentation

## Describing the UI
- Returnning null
- Do not place number in curly braces, wrong ``{arr.length && <h1>Raj</h1>}`` right ``{arr.length > 0 && <h1>Raj</h1>}``
- Variable can contain jsx
- Do not return large jsx conditionally, use variables instead
- Fragments disappear from the dom alowing to create flat list if element
- Index key may lead yon subtle and confusing bugs
- Using one foreach is better than two filters 
- Pure functions - same input same output, should not change obj variables that existed before rerendering

## Adding interactivity

- ```<button onClick={handleClick()}>``` it will cause function to run immediately when component renders beacuse we are calling it inside of curly braces
- in case of button name pass it as a children not as a props
- Events propagate upwards. Call ```e.stopPropagation()``` on the first argument to prevent that.
- do not define ```usestate``` using if else
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
