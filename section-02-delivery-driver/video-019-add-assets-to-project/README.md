# Video 19: Add Assets to Project

Drag the assets or folder of assets into the 'Assets' folder of your open Unity project. This will ensure the assets will be saved to disk with the Unity project.

## Sprites Are Made of Pixels

- Sprites are pixels.
- Sprites are an image (any image).
- Resolution refers to the number of pixels in an image.
- Higher resolution means more pixels.
- Pixel art typically involves a lower resolution.
  - Purposefully making the pixels obvious.
- Each pixel holds information - what colour it is.

## Unity Units

- 1 Unity Unit has no meaning.
  - Just whatever we want it to represent.
  - Could be metres, kilometres, miles, inches, etc. Whatever we want.
- 1 Unity Unit is represented by the side length of each box of the grid in a scene.

## Scaling the Assets

For this exercise, an easy way to scale things is to think of each Unity Unit to be a metre. So, the car would be around 4.5 metres in length and 1.5 metres in width. This means, in Unity units for this example, the car would be:

- 4.5 Unity units in length
- 1.5 Unity units in width

This means the house asset would need to be bigger than the car.

## Pixels Per Unit

- New assets default to 100 pixels per Unity unit when they're brought into the scene.
  - You can see this when you select an asset in the 'Project' panel, and then look in the 'Inspector' panel. Then, look under 'Sprite Mode' the 'Pixels Per Unit' value, which would be set at 100.
- This means if you want an image to appear bigger in a scene, you'd assign less pixels per unit.

To change the scale of the assets, click (or select multiple by holding down `CTRL` or `Command`), updating the 'Pixels Per Unit' value, then clicking 'Apply'.
