Certainly! Here's an updated version of the README with information about the `destroy` method:

# GestureHandler

GestureHandler is a JavaScript class that provides gesture event handling for swipe gestures on an HTML element. It allows you to attach event listeners for swipe up, swipe down, swipe left, and swipe right gestures and provides detailed information about the swipe data.

## Usage

Include the GestureHandler class in your project. You can then create a new instance of GestureHandler and attach event listeners to handle different swipe gestures.

```javascript
// Create a new GestureHandler instance for the target element
const gestureHandler = new GestureHandler(element);

// Attach event listeners for swipe gestures
gestureHandler
  .swipeUp((swipeData) => {
    // Handle swipe up gesture
  })
  .swipeDown((swipeData) => {
    // Handle swipe down gesture
  })
  .swipeLeft((swipeData) => {
    // Handle swipe left gesture
  })
  .swipeRight((swipeData) => {
    // Handle swipe right gesture
  });
```

### Swipe Data

The `swipeData` object passed to the callback function contains the following properties:

- `percentX`: The percentage of horizontal swipe distance relative to the element's width.
- `percentY`: The percentage of vertical swipe distance relative to the element's height.
- `regionX`: The percentage of horizontal position where the swipe ends, relative to the element's width.
- `regionY`: The percentage of vertical position where the swipe ends, relative to the element's height.

The `percentX` and `percentY` values represent the proportion of the swipe distance in relation to the element's dimensions. They are calculated by dividing the absolute value of the horizontal or vertical swipe distance by the corresponding dimension of the element and then multiplying by 100.

The `regionX` and `regionY` values represent the position of the swipe endpoint within the element's dimensions. They are calculated by dividing the horizontal or vertical position of the swipe endpoint by the corresponding dimension of the element and then multiplying by 100.

### Example

Here's an example demonstrating the usage of the GestureHandler class:

```javascript
// Create a new GestureHandler instance for an HTML element
const gestureHandler = new GestureHandler(document.getElementById("myElement"));

// Attach event listeners for swipe gestures
gestureHandler
  .swipeUp((swipeData) => {
    console.log("Swipe up gesture detected!");
    console.log("Swipe data:", swipeData);
  })
  .swipeDown((swipeData) => {
    console.log("Swipe down gesture detected!");
    console.log("Swipe data:", swipeData);
  })
  .swipeLeft((swipeData) => {
    console.log("Swipe left gesture detected!");
    console.log("Swipe data:", swipeData);
  })
  .swipeRight((swipeData) => {
    console.log("Swipe right gesture detected!");
    console.log("Swipe data:", swipeData);
  });
```

In this example, we create a new GestureHandler instance for an HTML element with the ID "myElement". We attach event listeners for each type of swipe gesture and log the swipe data to the console when a gesture is detected.

## API

### `constructor(element)`

Creates a new GestureHandler instance for the specified element.

- `element` (HTMLElement): The HTML element to attach the gesture event listeners to.

### `swipeUp(callback)`

Attaches an event listener for the swipe up gesture.

- `callback` (Function): The callback function to be called when the swipe up gesture is detected. The `swipeData` object will be passed as an argument to the callback.

Returns the GestureHandler

instance to allow method chaining.

### `swipeDown(callback)`

Attaches an event listener for the swipe down gesture.

- `callback` (Function): The callback function to be called when the swipe down gesture is detected. The `swipeData` object will be passed as an argument to the callback.

Returns the GestureHandler instance to allow method chaining.

### `swipeLeft(callback)`

Attaches an event listener for the swipe left gesture.

- `callback` (Function): The callback function to be called when the swipe left gesture is detected. The `swipeData` object will be passed as an argument to the callback.

Returns the GestureHandler instance to allow method chaining.

### `swipeRight(callback)`

Attaches an event listener for the swipe right gesture.

- `callback` (Function): The callback function to be called when the swipe right gesture is detected. The `swipeData` object will be passed as an argument to the callback.

Returns the GestureHandler instance to allow method chaining.

### `destroy(gestureType)`

Removes the event listener for the specified gesture type.

- `gestureType` (String): The type of gesture to remove the event listener for. Valid values are "swipeUp", "swipeDown", "swipeLeft", and "swipeRight". If not provided, all event listeners will be removed.

If no callback function is set for a specific gesture type or no gesture type is provided, the corresponding event listener will be removed.

If no callback functions are set for any of the gesture types or no gesture type is provided, all event listeners will be removed from the element.

If all gesture types are destroyed, the GestureHandler instance will still exist, but no event listeners will be attached to the element.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

```

```
