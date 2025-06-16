# Video 11: `transform.Translate()`

- Previously, we used `transform.Rotate()` to rotate the car
- Now, we'll use `transform.Translate()` to move the car
  - This will involve needing to give the `x`, `y` and `z` amounts we want to move
    - In other words, passing arguments

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

        // transform.Translate(5, 0, 0); // Move right, increase x position
        // transform.Translate(0, 5, 0); // Move up, increase y position
        // transform.Translate(5, 5, 0); // Move diagonally, increase both x and y positions
    }

    void Update()
    {
        transform.Rotate(0, 0, 0.1f);
        transform.Translate(0, 0.01f, 0); // Move up continuously, increasing y position over time

        // transform.Translate(0.01f, 0, 0); // Move right continuously, increasing x position over time
        // transform.Translate(0.1f, 0.01f, 0); // Move diagonally continuously, increasing both x and y positions over time
    }
}

```
