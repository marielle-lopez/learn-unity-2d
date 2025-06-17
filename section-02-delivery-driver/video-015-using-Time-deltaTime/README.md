# Video 15: Using `Time.deltaTime`

How quickly things happen in Unity depends on how fast your computer can process things. A higher-end computer will be able to process more frames per second than a slower computer, so when you have the same project on two different computers, the steering and acceleration of the car may be different.

To solve this, you need to use `Time.deltaTime` in Unity, which tells you how long each frame took to execute.

On a fast computer, it's going to take a short amount of time for each frame. In contrast, on a slower computer, it'll take a longer amount of time.

When we multiply a value by `Time.deltaTime`, it makes our game "frame rate independent".

- In other words, the game ends up behaving the same way on fast and slow devices.

|                     | Slow computer    | Fast computer      |
| ------------------- | ---------------- | ------------------ |
| Frames per second   | 10               | 100                |
| Duration of frame   | 0.1 s            | 0.01 s             |
| Distance per second | 1 x 10 x 0.1 = 1 | 1 x 100 x 0.01 = 1 |

## Code Snippets

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Driver : MonoBehaviour
{
    [SerializeField] float steerSpeed = 75f;
    [SerializeField] float moveSpeed = 3f;

    void Start()
    {
        Debug.Log("You don't make friends with salad!");
    }

    void Update()
    {
        float steerAmount = Input.GetAxis("Horizontal") * steerSpeed * Time.deltaTime;
        float moveAmount = Input.GetAxis("Vertical") * moveSpeed * Time.deltaTime;

        transform.Rotate(0, 0, -steerAmount);
        transform.Translate(0, moveAmount, 0);
    }
}
```
