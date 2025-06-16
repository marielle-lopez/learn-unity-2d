# Video 13: How to Use `SerializeField`

Making your variables available in the 'Inspector' panel in your Unity project window will save you a lot of time.

- This is done by serialising fields.

Serialising fields is handy because you can update the value of the variables in the Unity project window whilst the scene is running, so you can see real-time changes as you edit the variable values.

It's important to note that when you edit the value of variables in the Unity project window, that will be the value used. This is because the new value has been written to disk, and isn't reflected within the script.

- This can make things confusing if you're comparing between your script and what's in the 'Inspector' panel of your Unity project window.

## How to Use `SerializeField`

Add the `SerializeField` attribute in front of the properties.

```c#
[SerializeField] float steerSpeed = 0.1f;
[SerializeField] float moveSpeed = 0.01f;
```

The square braces `[]`, when placed before a class, variable, or method, shows that we're adding an attribute to the thing that's following it.

## What's `SerializeField`?

It's an attribute that allows us to serialise. In other words, right to disk.

- In this example, we're writing the variables to disk. By doing this, we can access the variables in the 'Inspector' panel.
