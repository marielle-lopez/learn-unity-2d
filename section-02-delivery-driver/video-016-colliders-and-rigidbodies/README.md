# Video 16: Colliders and Rigidbodies

In this section, we are:

- Adding a second game object
- Playing around with colliders and rigid bodies
  - We can see how objects can bump into each other and use the Unity physics system to apply force to one another

At the moment, the two objects only have sprite renderer as a component, which essentially tells how the objects to look. One component needs to be added to both objects, another component needs to be added to one of the objects.

The two components we're talking about are colliders and rigidbodies.

## Adding Collider Component

1. Click on the capsule game object.
2. In the 'Inspector' panel on the right, click the 'Add Component' button.
3. Search for 'collider'.
   - You will notice there will be colliders suffixed with '2D', and others not. The ones not suffixed with '2D' are for when you're working with 3D objects.
4. Click on 'Capsule Collider 2D'.

Selecting your game object and unselecting the 'Sprite Renderer' component in the 'Inspector' panel will show a green border of your game object. The player doesn't see this, but Unity knows this is collision – an invisible force field that we can have things touch. When something touches the collision line, we can say what the behaviour will be.

- For example, they can bump off and go in a different direction or they can't pass through.

## Adding Rigidbody

### What's Rigidbody?

It's a way of saying something has substance. It's the thing that the Unity physics engine understands that it's going to move around and it's going to be able to bump into and collide and have physical interactions.

In this example, we'll add the 'Rigidbody 2D' component to the car.

- By doing this, we're saying the car can interact with things using the physics system in Unity.

When we play the scene though, you'll see the car will drop off the screen. This is because gravity is on.

- In the 'Rigidbody 2D' component, 'Gravity Scale' is set to 1. We need to set this to 0, so gravity won't be applied to it and the car won't fall off the screen.
  - We're designing a game with a bird's eye view of car, so there's no gravity we can see.
- You'd keep gravity on for things like side-scrolling platform games, or where you expect things to fall.

Now, if you drive the car into the circle, you'll see it'll fling off the circle. But, the car doesn't run over it, which is what we want.

We can then add the 'Rigidbody 2D' component to the circle as well, so that it moves when the player hits the car with it.

- Don't forget to set the 'Gravity Scale' setting to 0.

## Replacing Capsule Collider with Box Collider

Then, if you play the scene and move the car to collide with the circle, the circle is able to move when it's hit. However, you'll notice it's a bit difficult to continue hitting the circle as you accelerate. This is because of the shape of the collider, which is capsule. The rounded edges make the car 'slide off' the circle when colliding with it.

- Instead, you can get rid of the 'Capsule Collider 2D' component on the car object, and replace it with a 'Box Collider 2D' component.

When you test the car collision with the circle, you'll now notice the car doesn't easily slide off of the circle. This is because the collider component has corners.

## Code Snippets

```c#
// No changes in comparison to Section 2 Video 15

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
