# Video 5: Set Up Visual Studio Code

## Making Sure Unity is Looking at the Correct IDE

1. In your Unity project, click 'Edit' at the top.
2. Click on 'Preferences'.
3. In the left navigation bar, click on 'External Tools'.
4. Ensure 'External Script Editor' is set to 'Visual Studio Code'.

## Creating a Script

1. In the 'Project' panel at the bottom in your Unity project window, right-click on an empty space in the 'Assets' section.
2. Click on 'C# Script'.
3. Name your script.
   - For example, 'PrintToConsole'.
   - Don't click anywhere else until you've named your script, otherwise the name of the class will not match the name of the script file if you edit the file's name.
4. Press Enter.
5. Click on your new script.
   - The right panel will update with information about the script, as well as a preview of it. You can't edit the script in Unity, which is why an IDE is needed.

## Opening a Script from a Unity Project

1. In the 'Project' panel, double-click a script.
   - It should open up in VS Code.

## Editing a Script from a Unity Project

### What's `Start()`?

It's the method that's called when you click the 'Run' button in your Unity Project.

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PrintToConsole : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        Debug.Log("You don't make friends with salad!");
    }

    // Update is called once per frame
    void Update()
    {

    }
}

```

## Attaching a Script to a Game Object

This is required so that when you press the 'Run' button, the behaviour coded in the script runs for that particular game object.

1. In your Unity project window, select the game object you'd like to attach your script to.

2. In the 'Project' panel at the bottom, drag your script to the empty space below the 'Add Component' button.
   - This will add your script as a new component to your game object. By doing this, the script will run because it's now in the scene.

## Notes

## Script Naming Convention

- Camel case is the naming convention for scripts.
  - For example, `PrintToConsole`.

## VS Code Extensions to Add

- C# by Microsoft
- Unity Code Snippets by Kleber Silva
