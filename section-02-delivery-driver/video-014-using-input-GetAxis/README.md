# Video 14: Using `input.GetAxis()`

In this part, we're going to allow the player to move the car forwards and backwards, rotate it left and right by using their keyboard arrow keys.

## Looking at the Input System

1. In your Unity project window, go to the window menubar at the top and click 'Edit', and then go to 'Project Settings'.
2. In the 'Project Settings' overlay window, click on 'Input Manager' in the left navigation bar.
3. You will see a dropdown menu for 'Axes'. Click this.
4. You'll then see two dropdown menus for 'Horizontal' and 'Vertical'.
   - In 'Horizontal' and 'Vertical', make sure the following key bindings are configured:

| Input               | Horizontal Value | Vertical Value |
| ------------------- | ---------------- | -------------- |
| Negative Button     | left             | down           |
| Positive Button     | right            | up             |
| Alt Negative Button | a                | s              |
| Alt Positive Button | d                | w              |

An important note is that the axes will go from -1 to +1.

As a quick note, if you scroll further, you find more dropdowns for 'Horiztonal' and 'Vertical'. These ones are for joysticks and a mouse. You can by opening the dropdowns and seeing 'Type' assigned to 'Joystick Axis'.

## Implement User Input into the Script

Just as a quick note, we have `steerSpeed` and `moveSpeed` as variables of the class. This is because we need these values as soon as the scene is run. We're going to declare `steerAmount` in `Update()` because its value is going to update over time.

### Steering the Car

The argument passed to `GetAxis()` is a string, which needs to be the exact name of the input we saw when looking at the input system. In this case, we'll pass `"Horizontal"`.

```c#
float steerAmount = Input.GetAxis("Horizontal");
```

`steerAmount` is essentially checking what the player is pushing from -1 to +1 on the left and right (or `A` or `D`) arrow keys.

- You'll notice when you test in your Unity project running, that the horizontal direction is flipped, so we can add `-` to `steerAmount` when we call it.

```c#
transform.Rotate(0, 0, -steerAmount);
```

Now, multiply the value of `steerAmount` by `steerSpeed`.

```c#
float steerAmount = Input.GetAxis("Horizontal") * steerSpeed;
```

### Accelerate and Deccelerate the Car

Create a new variable in `Update()` called `moveAmount` of type `float`. Use `Input.GetAxis()` and pass `"Vertical"` as the argument. Similar to the example above, multiple the value of `moveAmount` by `moveSpeed`, and then replace `moveSpeed` in `transform.Translate()` with `moveAmount`. This will allow you to use your keys to accelerate and deccelerate the car.

```c#
float moveAmount = Input.GetAxis("Vertical") * moveSpeed;
transform.Translate(0, moveAmount, 0);
```

## Notes

### Unity Input System

Over the years, Unity has used a few different input systems. For the Unity 2021 version we're using in this course, there's an 'old' system and a 'new' system.

In this course, we'll use the 'old' system as it's easier to understand. Later on, the 'new' system will be introduced.

#### Input System

An input system converts the player's physical actions (e.g., button press, key press, etc.) into information for the game.
