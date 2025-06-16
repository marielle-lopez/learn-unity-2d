# Video 10: Introduction Methods

Goal in this video is to make a capsule object rotate using the `transform.Rotate()` method.

## Start Your Project

1. Start a new 2D project in Unity
2. Add a capsule sprite
   - This will be the car
3. Create a C# script called `Driver`
4. Add the `Driver` script to your capsule sprite
5. Rename the capsule sprite.

## Rotate Your Car Using Code

Because we're rotating the capsule sprite, we're doing something in relation to the 'Transform' component.

In scripts, you can type the name of the component you'd like to interact with in the project, and you will be able to call available methods as part of that component (in the script, the component is a class).

You need to pass in arguments to tell the capsule sprite how much to rotate.

- In this case, you need to pass integers or floats.

```c#
// transform.Rotate(x, y, z);
transform.Rotate(0, 0, 45);
transform.Rotate(0, 0, 0.1f);
```

## Notes

### What Are Methods?

- Also called functions
- Execute blocks of code that makes our game do things
- We can:
  - Use the methods already available in Unity
  - Create our own methods
- Methods are called so what the code inside of them can be executed

### Creating Methods

- When you create a method, you're giving it a name and also saying what it should do

### Namespaces

- Things Unity has given to us, which we can use in our scripts
- We can use namespaces by stating `using`, followed by the name of the namespace
- Namespaces contain things we can use in our script

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
```

### Classes

- Classes are a way for us to group similar things together
- They contain methods which we can call

## `void Start()` and `void Update()`

These are methods. In particular, they're callbacks.

### `void Start()`

- Will be called when you press the 'Run' button in your Unity project
- So, any scripts in the scene when the 'Run' button is clicked, they will call their `Start()` method

### `void Update()`

- Called for every single frame that the game is running

### Comments

You can write comments in C# code using `//`, followed by what you want to write as a comment.

```c#
// You don't make friends with salad! *dance*
```

## Code Snippets

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Driver : MonoBehaviour
{
    void Start()
    {
        Debug.Log("You don't make friends with salad!");
    }

    void Update()
    {
        transform.Rotate(0, 0, 0.1f);
    }
}

```
