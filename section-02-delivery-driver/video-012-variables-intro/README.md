# Video 12: Introducing Variables

The problem right now is that the car is going at a fixed amount of speed and rotation. What if we want to accelerate, deccelerate, turn left or right?

## What's a Variable?

- They help us store, manipulate, and refer to information
- Each variable:
  - Has a name
  - Contains data
  - Is of a particular type

### Naming Convention

The convention for naming variables is pascal case.

- For example, `hitPoints`.

## Common Data Types of Variables

| Variable Data Type | Description                                  |
| ------------------ | -------------------------------------------- |
| `int`              | Whole numbers                                |
| `float`            | Fractional numbers (up to 6 decimal places)  |
| `double`           | Fractional numbers (up to 15 decimal places) |
| `bool`             | True or false                                |
| `string`           | Sequence of characters                       |

## Declaring Variables

```c#
float speed = 3.8f;
bool isAlive = true;
string dragonQueen = "Daenerys Targaryen";
```

## Code Snippets

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Driver : MonoBehaviour
{
    float steerSpeed = 1f;
    float moveSpeed = 0.01f;

    void Start()
    {
        Debug.Log("You don't make friends with salad!");
    }

    void Update()
    {
        transform.Rotate(0, 0, steerSpeed);
        transform.Translate(0, moveSpeed, 0);
    }
}

```
