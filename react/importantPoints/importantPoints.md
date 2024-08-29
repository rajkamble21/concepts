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

