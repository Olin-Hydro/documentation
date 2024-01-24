Here you will learn how to create custom pixel art and import it into unity.

For this part of onboarding, you'll be creating a custom backdrop for your scene.

## Creating Custom Pixel Art

We will be using photoshop to create our pixel art. This is pretty self explanatory, but there are some things to keep in mind.

- Characters are 14x28 pixels
- Scenes are 128x96 pixels
- When making a new document make sure its units in pixels
- Use the pencil tool to draw artwork
    - Right click on the brush(B) and switch to the pencil
- You don't need to create a new photoshop file for each art piece, you can create them in one file and separate them in unity(this is called a spite sheet).
    - If you're making a sprite sheet, make sure each new sprite is on a separate layer. It just makes it easier in the future to edit.
- When you're done save the file as  .psd file and **NOTHING ELSE**. Unity can read .psd files and it makes it so much easier to edit after the fact.

With that done, try and make a background to replace the blank background of your current scene.

## Importing Assets

Now let's import the background you made.

1. Drag and drop your .psd files into the artwork folder. You can also do this through the project manager.

_Bing! Bam! Boom! You're done! Not yet..._

2. Select the artwork and view it in the inspector. Change "Filter Mode" from "Bilinear" to "Point(No Filter)." Change "Compression" to "None." Both of these setting warp the appearance of the artwork. Switching them mantains its appearance.

3. Select the "Sprite Editor" button. In the pop up that appears, at the bottom right, change "Pivot" to "Bottom Left."

    All our assets are this way, so it just keeps things uniform.

4. Ok! Now your artwork can be used. If you made a sprite sheet, there are a few more step.

5.  Change the "Sprite Mode" setting from "Single" to "Multiple". Guess what this does?

6. Reopen the Sprite Editor. In the top left, click the "Slice" drop down. Change the pivot to "Bottom Left." Click Slice.

    _This will slice all the sprites for you. If you don't like automatic, change the type to grid, to specify how the sprites should be sliced._

Alright! You're done! You're now a fully fledged amateur game designer!!!