# Video 20: Basic Level Layout

- Laying out the map using the assets.
- Replacing the capsule sprite with the car asset.

## Replace the Capsule Sprite with an Asset

1. Click on the capsule object.
2. In the 'Inspector' panel in the 'Sprite Renderer' component, look at 'Sprite'. Click on the double circle icon, and select the car asset you wish to choose. This will be the asset used.
3. Remove the 'Capsule Collider 2D' component if it still exists.
4. Look at the 'Box Collider 2D' component and click on the 'Edit Collider' button. This will shown handles on the outlines of the collider, so you can resize the boundaries.

## Resize Camera Zoom

1. Click on the 'Main Camera' object in the scene.
2. In the 'Inspector' panel under the 'Camera' component, change the value of 'Size'. You can adjust it however you like, depending on how zoomed in you'd like your view.

## Organise Objects

This can be done by using empty game objects.

1. Right-click on an empty space in the 'Hierarchy' panel in the 'SampleScene'.
2. Select the 'Create Empty' object.
3. Give the empty object a name (i.e., 'World Objects').
4. Following good practice, right-click on the 'Transform' component in the 'Inspector' panel, and then click 'Reset'.
5. Select all of the world objects such as the trees, rocks, houses, and roads, and drag them on top of the empty game object. This will make these objects children of the empty object, effectively containerising them.

## Adding Box Colliders to the World Objects

1. You can select multiple objects in the scene, in this case, houses, and then in the 'Inspector' panel, click the 'Add Component' button at the bottom. Search for 'Box Collider 2D'. This will add a box collider around the house assets.
2. Edit the boundaries of the collider components by clicking the 'Edit Collider' button, and then use the handles to re-shape it.

Add any differently-shaped colliders to different assets to ensure your world objects cannot be moved if the player bumps into them.

## Snap Objects to the Grid

Optionally, you can make objects snap to the grid by clicking the 'Global' button at the top and then the symbol with the magnet and grid.

## Change Camera Colour

At the moment, the background of the game is blue. This is set by the 'Main Camera' object. Select it and in the 'Inspector' panel, you'll see the 'Background' option. Choose whatever colour you wish to replace the blue if you'd like.
