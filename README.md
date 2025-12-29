# Find the Key Maze

## Beginner Game 3

## Step 1
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
```blocks
let key = Sprite = sprites.create(assets.image`key`, SpriteKind.Player)
```
## Step 5
```blocks
(uses sprites, simple obstacles)
```
## Step 6
```blocks
scene.setBackgroundColor(7)
```
## Step 7
```blocks
let player3 = sprites.create(assets.image`finder`, SpriteKind.Player)
```
## Step 8
```blocks
controller.moveSprite(player3)
```
## Step 9
```blocks
player3.setFlag(SpriteFlag.StayInScreen, true)
```
## Step 10
```blocks
let door = sprites.create(assets.image`advice`, SpriteKind.Projectile)
```
## Step 11
```blocks
door.setPosition(150, 60)
```
## Step 12
```blocks
key = sprites.create(assets.image`key`, SpriteKind.Food)
````
## Step 13
```blocks
key.setPosition(20, 60)
```



> Open this page at [https://linuxloser137.github.io/find-the-key-maze--b3/](https://linuxloser137.github.io/find-the-key-maze--b3/)

## Use as Extension

This repository can be added as an **extension** in MakeCode.

* open [https://arcade.makecode.com/](https://arcade.makecode.com/)
* click on **New Project**
* click on **Extensions** under the gearwheel menu
* search for **https://github.com/linuxloser137/find-the-key-maze--b3** and import

## Edit this project

To edit this repository in MakeCode.

* open [https://arcade.makecode.com/](https://arcade.makecode.com/)
* click on **Import** then click on **Import URL**
* paste **https://github.com/linuxloser137/find-the-key-maze--b3** and click import

#### Metadata (used for search, rendering)

* for PXT/arcade
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
