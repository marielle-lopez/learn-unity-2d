# Video 18: Using `OnTriggerEnter2D()`

In this section, we're looking at triggers and how to use `OnTriggerEnter2D()` so that when the player first crosses over a 'trigger volume', it will print something to the console.

First, create a new object in your scene which the car will drive over and trigger a message to be printed to the console.

- It can be a box, for example.
- Then, add a 'Box Collider 2D' component to it so we add the invisible force field around it.
  - We won't be able to push it with the car because we haven't added the 'Rigidbody 2D' component to the square object.

## Enabling 'Is Trigger'

For the box object, we can then toggle 'Is Trigger' to be on in the 'Box Collider 2D' component.

- This will allow you to drive over the box, but also allow you to invoke some sort of functionality when the box is driven over.

## Layer Ordering

You'll notice that when you drive over the square object, that the box object appear above the car. This is because you need to update the value of 'Order in Layer' (in the 'Sprite Renderer' component) to be higher that the value set for the box object.

## Print to Console When Trigger is Set Off

In `Collision.cs`, you can now add a private method called `OnTriggerEnter2D()`, which is another in-built Unity method.

## `OnTriggerExit2D()`

This is another method which you can use when you want to add functionality when an object exits a trigger zone.

This is different to `OnTriggerEnter2D()`, which will be invoked when a game object first passes the collision boundary of an object with a collision component that's acting as a trigger.

## Code Snippets

```c#
// Collision.cs

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Collision : MonoBehaviour
{
    void OnCollisionEnter2D(Collision2D other)
    {
        Debug.Log("Mmm... forbidden donut.");
    }

    void OnTriggerEnter2D(Collider2D other)
    {
        Debug.Log("Don't have a cow, man!");
    }
}
```
