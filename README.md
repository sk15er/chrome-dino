# Hack Google Chrome and Make your Dinosaur Immortal



The game can be hacked pretty easily, making your dinosaur not even flinch at the sight of a cactus.

To hack the game, first go the the error message page where your dinosaur is hanging out. 

Go ahead and press the space bar to start the  game. Once the game starts, right-click and select ``Inspect” to open up Chrome DevTools``, then select the ``Console`` tab. 

You can also do this by using the Ctrl+Shift+I shortcut, which takes you straight to the  Console tab of DevTools.



### Open Chrome Console

- Make sure you are on the No Internet Connection page.
- Right click anywhere on the page and select Inspect.
- Go to Console tab. This is where we will enter the commands to tweak the game.



#### Tweaking Speed

Type the following command in Console and press enter. You can use any other speed in place of 1000.

```js
Runner.instance_.setSpeed(1000)
```



#### Immortality

After every command press enter. All the commands are case-sensitive.

We store the original game over function in a variable:

```js
var original = Runner.prototype.gameOver
```

Then, we make the game over function empty:

```js
Runner.prototype.gameOver = function(){}
```

Stopping the game after using Immortality

When you want to stop the game, Revert back to the original game over function:

```js
Runner.prototype.gameOver = original
```



#### Setting the current score

Let’s set the score to 12345. You can set any other score less than 99999. The current score is reset on game over.

```js
Runner.instance_.distanceRan = 12345 / Runner.instance_.distanceMeter.config.COEFFICIENT
```



#### Dino jumping too high?

You can control how high the dino jumps by using the below function. Adjust the value as necessary.

```js
Runner.instance_.tRex.setJumpVelocity(10)
```
