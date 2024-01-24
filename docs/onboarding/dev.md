Here you will learn how to add a working button to your scene. You'll also learn how to use collision as a trigger between your two sprites.


The feature you'll be implementing is restricting the player's movement when it comes into contact with the other sprite. Then, you'll allow the player to move again by clicking a button.

_This "flavor" of onboarding will be more code heavy. Experience of any programming language is crucial(basically, have you taken SoftDes). I'll explain a little bit about coding with C#, but that's it. If you have no experience and still want to try to follow along, go ahead! If you need help, I'll gadly help in my free time._

### C# Intro

But first! Let's learn some C#. Let's look at `FallingBook.cs` as an example. This script is supposed to trigger an animation and stop the player's movement upon impact.

    using System.Collections;
    using System.Collections.Generic;
    using UnityEngine;

    public class FallingBook : Collidable
    {
        public player player; 
        bool firstHit; 
        Animator animator;
    
        protected void Start(){
            base.Start();
            animator = GetComponent<Animator>(); 
            firstHit = true;
        }
        protected override void OnCollide(Collider2D coll)
        {
            if (firstHit == true){
                animator.SetTrigger("hit"); 
                player.moveFlag = false;
                firstHit = false;
            }

        }

At this point, I'm too lazy to explain this code, but here are some important things to point out.

- C# requires `{}` for classes, loops, and functions. It also nees `;` after each line. Despite this! It's still good practice to properly indent your lines within brackets for code readability. 


     _Please or I'll be sad :(._

- ` public class FallingBook : Collidable{}` creates the object(in this case a class) that unity can interact with. `Collidable`is the class that this one extends from(i.e is based on/can use function from)
        
    _The `override` keyword means this class alters the base class' function. `base.start()` means that it copied the base class' function and adds to it._

- There are some built in functions `void Start(){}` and `void Update(){}`. 

    - `Start` runs once at the very beginning. This is used for setting inital variables, or getting game objects for later use. 

    - `Update()` runs once every x frames(I think ten). Use it for things like that need constant updates like moving the charcter.

        _This programs omits `Update()`. This is because it's already defined in the Collidable class._

- You must declare variables before anything else.

- `animator = GetComponent<Animator>();` is how you assign a component from the same game object to a variable.

    _There a way to get values and components from other game objects. See documentation for [bookFallFinish](../scripts/bookFallFinish.md) for a explanation._

That's basically it! Let's get coding.

### Adding Collision Detection

Before we start, make sure to add a Box Collider 2D to your second sprite. 

1. Create a new script in the stationary sprite(Add Component > New Script). Name it "StopMove"

2. Replace `MonoBehavior` with `Collidable`. We're going to leverage a prewritten class.

3.  First we need to declare our variables. 

        public player player;
    
    This is actually getting the values from the player class in our movable sprite. The player class is setup so that all it's values are public. Don't do this unless necessary. Things can go very very wrong.
    
    Normally, we would also have to declare the box colliders, but the Collidable class does it for us.

4.  Remove `void Start()`. It's already defined for us in the Collider class.

5. Get rid of `void Update()` replace it with 

        protected override void OnCollide(Collider2D coll) 

    The `protected` means it can only be accsessed within its class and children classes.

6. Now just add 
    
        player.moveFlag = false;
    
    This is a boolean created within the player class that controls movement.

Alrighty! Now just run the game and see if it works.

### Adding a Button

This is pretty simple, and we're not gonna do anything fancy with it.

1.  Create a button game object(Game Object > UI > Button). It should show up under the Canvas game object.

2. Open the button in the Inspector. Scroll down to "On Click()." Click the "+".

3. For the target (circle with a dot in it), click the "scene" tab and select the moveable sprite.

4. Click the "No Function" drop down and click player>changeMovement. Check the box.

    - This is a function within player that activates/deactivates movement. If no value is given, it defaults to being true. To be able to control things with a button, a **function is required**. You can't just change variables at will.

5. Run it and see if it works. Does it? Nope! Remeber `void Update()`. It's always running. Since the sprites are constantly colliding, `OnCollide()` is constantly stopping the movement.

6. We can stop this two ways, either by making it run only the first time we collide, or by moving either sprite outside of the collision zone. Try to implement a solution to this. Have fun!


Well... That's it. If you've finished the last part, congrats! That's all of onboarding. It's goodbye for now, but feel free to reference this site whenever you have questions. Or even help me write and update it! Tata for now <3





