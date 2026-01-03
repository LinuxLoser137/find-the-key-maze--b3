
# Find the Key Maze

## Beginner Game 3

## Step 1
Set the 
```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (p, k) {
    k.destroy()
    hasKey = true
    game.splash("You got the key!")
    hasKey = false
    key = sprites.create(assets.image`key`, SpriteKind.Food)
    key.setPosition(Math.randomRange(10, 150), Math.randomRange(10, 110))
})
```

## Step 2
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
## Step 3
```blocks
let hasKey = false
```
## Step 4
Create a sprite called key ``||Sprite:create(assets.image`key`, SpriteKind.Player)||``
```blocks
let key = Sprite = sprites.create(assets.image`key`, SpriteKind.Player)
```
## Step 5
Create obstacles ``||(uses sprites, simple obstacles)||``
```blocks
(uses sprites, simple obstacles)
```
## Step 6
Set backround ``||Scene:setBackgroundColor(7)||``
```blocks
scene.setBackgroundColor(7)
```
## Step 7
Create a sprite and name it finder ``||Sprites:create(assets.image`finder`, SpriteKind.Player)||``
```blocks
let player3 = sprites.create(assets.image`finder`, SpriteKind.Player)
```
## Step 8
Create movement for the sprite ``||Controller:moveSprite(player3)||``
```blocks
controller.moveSprite(player3)
```
## Step 9
Set a boundary for the sprite to stay on the screen ``||Sprites:setFlag(SpriteFlag.StayInScreen, true)||``
```blocks
player3.setFlag(SpriteFlag.StayInScreen, true)
```
## Step 10
Create a sprite called adivice and set it as a projectilem ``||create(assets.image`advice`, SpriteKind.Projectile)||``
```blocks
let door = sprites.create(assets.image`advice`, SpriteKind.Projectile)
```
## Step 11
Create a position for the sprite to start in ``||setPosition(150, 60)||``
```blocks
door.setPosition(150, 60)
```
## Step 12
Create a sprite called key ``||create(assets.image`key`, SpriteKind.Food)||``
```blocks
key = sprites.create(assets.image`key`, SpriteKind.Food)
````
## Step 13
Set the position for the key ``||setPosition(20, 60)||``
```blocks
key.setPosition(20, 60)
```
