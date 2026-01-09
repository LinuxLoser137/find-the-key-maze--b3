## Step 1

Create a variable to track if the player has the key
``||variables:set hasKey to false||``
```blocks
let hasKey = false
```
## Step 2

Set the background color
``||scene:setBackgroundColor(7)||``
```blocks
scene.setBackgroundColor(7)
```
## Step 3

Create a sprite and name it finder
``||sprites:create(assets.image`finder`, SpriteKind.Player)||``
```blocks
let player3 = sprites.create(assets.image`finder`, SpriteKind.Player)
```
## Step 4

Create movement for the sprite
``||controller:moveSprite(player3)||``
```blocks
controller.moveSprite(player3)
```
## Step 5

Keep the player on the screen
``||sprites:setFlag(SpriteFlag.StayInScreen, true)||``
```blocks
let hasKey = false
scene.setBackgroundColor(7)
let player3 = sprites.create(assets.image`finder`, SpriteKind.Player)
controller.moveSprite(player3)
player3.setStayInScreen(true)
```
## Step 6

Create a sprite called key
``||sprites:create(assets.image`key`, SpriteKind.Food)||``
```blocks
let hasKey = false
scene.setBackgroundColor(7)
let player3 = sprites.create(assets.image`finder`, SpriteKind.Player)
controller.moveSprite(player3)
player3.setStayInScreen(true)
let key = sprites.create(assets.image`key`, SpriteKind.Food)
```
## Step 7

Set the starting position for the key
``||sprites:setPosition(20, 60)||``
```blocks
let hasKey = false
scene.setBackgroundColor(7)
let player3 = sprites.create(assets.image`finder`, SpriteKind.Player)
controller.moveSprite(player3)
player3.setStayInScreen(true)
let key = sprites.create(assets.image`key`, SpriteKind.Food)
key.setPosition(20, 60)
```
## Step 8

Create a sprite called advice and set it as a projectile
``||sprites:create(assets.image`advice`, SpriteKind.Projectile)||``
```blocks
let door = sprites.create(assets.image`advice`, SpriteKind.Projectile)
```
## Step 9

Set the starting position for the door
``||sprites:setPosition(150, 60)||``
```blocks
door.setPosition(150, 60)
```
## Step 10

Create obstacles
``||sprites:create simple obstacle sprites||``
```blocks
let obstacle = sprites.create(assets.image`obstacle`, SpriteKind.Enemy)
```
## Step 11

Detect when the player collects the key
``||sprites:onOverlap(SpriteKind.Player, SpriteKind.Food)||``
```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (p, k) {
    hasKey = true
    k.destroy()
    game.splash("You got the key!")
})
```
## Step 12

Detect when the player touches the door
``||sprites:onOverlap(SpriteKind.Player, SpriteKind.Projectile)||``
```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Projectile, function (p, d) {
    if (hasKey) {
        d.destroy()
        game.over(true, effects.starField)
    } else {
        game.splash("You need the key!")
    }
})
```



