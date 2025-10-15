# Breakout

W Kavanagh & N Merchant. Summer 2024 

## controls

A/D to move the paddle right and left.
P to pause.

## Powerups

big/small paddle (blue)
fast/slow ball (fancy yellow)
fire ball (green)

# Tasklist

## Suggested fixes

* Fix the compiler issues in the code

## Suggested tasks

* Implement mouse input for pad
* Improved VFX (ball trail, paddle hit response, brick particle destruction)
* Better UI (progress bar rather than timer for countdown).
* GameLoop
* Better ball physics (Box2D)
* Leaderboards
* More ball types (e.g., multiball, sticky ball [where you shoot the ball from the paddle every time], tiny ball, big ball, brick-tracking ball)
* Sounds with increasing tone between bounces.
* Implement commentary with calls to an LLM such as LLama

# Time Details and Changelist
<Add information to this section about the time you've taken for this task along with a professional changelist.>

## Complier issue fixed
Cause: derived powerup class (PowerUpFireBall) header file was included into the base class header causing a compiler loop
Time to fix: 9 mins

## Features added

### Brick fadeout vfx on collision with ball while fireball is active
Time to implement: 1hr 4m
Changes made:
- variables added to brick class to enable interpolation between 2 alpha values
- functions added to brick class that triggers this effect when appropriate flags are set
- modified brick class to enable queries on its destruction status (setters/getters)
- modified brick manager class to set flags on brick when fireball has collided with it
- modified brick manager to set flags, marking the destruction of a brick upon collision with ball
- modified brick manager to handle destruction of bricks in render cycle (removes from vector if marked for destruction)

### Rudimentary menu system
Time to implement: 27m

Changes made:
- States added to game manager to dictate various game states (Started, completed, paused, game over)
- Function added to display UI text when in certain states
- Menu UI is activated by: pausing game and completing or losing game
- Function added to close game windows when input key is activated (Q) while menu UI is active
- Function added to reset game when input key is activated (R) while menu UI is active
