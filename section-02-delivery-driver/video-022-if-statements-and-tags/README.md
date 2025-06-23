# Video 22: If Statements and Tags

In this section, we're using if statements and tags.

- If the car drives over something tagged as a package, we print to the console a package has been picked up.
- If the car drives over something tagged as a customer, we print to the console a package has been delivered.

Rename the 'Square' game object to 'Package', and the 'Circle' game object to 'Customer'.

## Renaming a Script

1. In your open Unity project window, in the 'Project' panel and in the 'Assets' directory, select the `Collision` script and click F2. Rename it to `Delivery`, because now we're dealing with the delivery system in the game.
2. Open the `Delivery` script and rename the class from `Collision` to `Delivery`.

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Delivery : MonoBehaviour
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

3. In Unity Hub, click on the car game object and in the 'Inspector' panel, check the `Collision` component has changed to the `Delivery` component.

## Tags

Tags allow us to easily check in code if something belongs to a particular category of thing.

### Add a New `Package` Tag

1. Click on the 'Package' game object.
2. In the 'Inspector' panel, click on the dropdown menu of 'Tag', and select the 'Add Tag...' option.
3. Create a new tag called 'Package' by clicking on the '+' symbol by the 'List is Empty' textbox. Click 'Save'.
4. Click on the 'Package' game object again, and then assign the 'Package' tag in the 'Inspector' panel.

### Checking If Game Object is Tagged as a `Package`

The `other` parameter of `OnTriggerEnter2D()` gives us information of the object we've 'triggered'. In this case, we can see if the object is tagged as a `Package`.

```c#
void OnTriggerEnter2D()
{
  if (other.tag == "Package")
  {
    Debug.Log("Package secured".);
  }
}
```

## Create a Customer

1. Create a new circle game object called 'Customer'.
2. Give the 'Customer' game object a colour and position it in the world wherever you'd like.
3. Add a 'Circle Collider 2D' component to the 'Customer' game object, and make it a trigger.
4. Order the 'Customer' game object so that when the user drives over it, the 'Customer' object appears below the car sprite.
5. Create a 'Customer' tag and assign it to the 'Customer' game object.
6. Update the `Delivery` script so that when the car drives over the 'Customer' game object, a message is printed to the console saying the package has been delivered.

```c#
void OnTriggerEnter2D(Collider2D other)
{
    if (other.tag == "Package")
    {
        Debug.Log("Package secured.");
    }
    else if (other.tag == "Customer")
    {
        Debug.Log("Package delivered.");
    }
}
```
