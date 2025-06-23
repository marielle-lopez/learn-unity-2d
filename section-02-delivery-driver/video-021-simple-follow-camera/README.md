# Video 21: Simple Follow Camera

In this section, we're setting up a follow camera, which will allow the user to drive and see the rest of the world.

You'll notice that when you select the 'Main Camera' in the scene and drag it around, the view in the game changes. What we want is for the 'Main Camera' to position itself wherever the car is in the world, which essentially looks like the camera is following the car.

## Creating a New Script

1. In the 'Project' panel in the 'Assets' directory, create a new C# script called `FollowCamera`. Open this new script.
2. Apply the `FollowCamera` script as a component of the 'Main Camera' object.
3. In `FollowCamera`, you can remove the `Start()` method as we don't need any functionality for this when the scene initially runs.
4. Now, we need to update the 'Transform' position values of the 'Main Camera', which we need to assign the value of the 'Transform' values of the car. This means we also need to reference the car. We can reference the car in many ways.
   - One of the ways to reference the car is by creating a `SerializeField` which we can point to in the 'Inspector'. This will be of type `GameObject`. When you save the `FollowCamera` script, you will see in the 'Inspector' panel of the 'Follow Camera' component that you can select an object to reference (i.e., 'Lightning McQueen') under the 'Scene' tab.

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class FollowCamera : MonoBehaviour
{
    // This script makes the camera follow a target object (i.e., the car)
    [SerializeField] GameObject target; // The target object to follow

    void Update()
    {

    }
}
```

5. We can now reference the target object we want the camera to follow.
   - If you run the scene in your open Unity project window, you'll just see the game showing the green background of your 'Main Camera' object. If you click the '2D' button at the top to toggle off 2D view, you'll see the 'Main Camera' object right above the car. You need to provide an offset for the camera, which you can provide by updating the value of the 'Transform' Z position.

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class FollowCamera : MonoBehaviour
{
    // This script makes the camera follow a target object (i.e., the car)
    [SerializeField] GameObject target; // The target object to follow

    void Update()
    {
        transform.position = target.transform.position;
    }
}
```

6. Offset the 'Main Camera' object on the Z-axis.
   - We use `new Vector3` because that's the type of `*.transform.position`.

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class FollowCamera : MonoBehaviour
{
    // This script makes the camera follow a target object (i.e., the car)
    [SerializeField] GameObject target; // The target object to follow

    void Update()
    {
        transform.position = target.transform.position + new Vector3(0, 0, -10);
    }
}
```

## Jittery Camera

This happens in relation to the Unity execution order.

We haven't yet specified when the camera should move to the car's location, or vice versa, so updating the positions can confuse the engine.

Unity's execution order is all of the things Unity does when we push the 'Play' button. On every single frame of our game is running, there's a lot going on, which is a lot we don't need to know about. There's a phase called 'Physics', which is being calculated at a different rate to a lot of the other things in our game, such as game logic.

Physics is fixed and the reason it is, is so that there can be predictability with physics. If physics was calculated too much, it might be too intensive for the game.

- Physics often requires a lot of calculations.
- Within Unity, physics runs with its own loop and update can be a little different sometimes.

There's another 'phase' in the Unity execution order called 'Game logic', which has a step called 'Update', which is called every frame.

- There are more frames on a faster computer, and less frames on a slower computer, but it's still running through 'Update'.

There's another step in the 'Game logic' 'phase' of the Unity execution order, called 'LateUpdate'. This is called as the last step of the 'Game logic' phase.

- We can use this to our advantage, and update the `Update` method of the `FollowCamera` script to be `LateUpdate`. This way, we guarantee the camera will absolutely follow the care smoothly, as it won't be fighting with the car in terms of what positioning.

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class FollowCamera : MonoBehaviour
{
    // This script makes the camera follow a target object (i.e., the car)
    [SerializeField] GameObject target; // The target object to follow

    void LateUpdate()
    {
        transform.position = target.transform.position + new Vector3(0, 0, -10);
    }
}
```

## Code Snippets

```c#
// FollowCamera.cs

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class FollowCamera : MonoBehaviour
{
    // This script makes the camera follow a target object (i.e., the car)
    [SerializeField] GameObject target; // The target object to follow

    void LateUpdate()
    {
        transform.position = target.transform.position + new Vector3(0, 0, -10);
    }
}
```
