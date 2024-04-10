---

---
---
Not really organized in some logical way, I just discovered each of these topics in the sequential order they are in. 

1. [`func _process(delta):`](#`func _process(delta):`)
2. [`position`](#`position`)
3. [`@export`](#`@export`)
4. a
5. a

### `func _process(delta):`

Think of how Minecraft has `Ticks`, a measurement of time within the game. The `_process` function is a `Godot std library` function that executes a piece of code for every single `Tick` in your game. 

Example: print "hello world!" for every single tick in my game

```python
func _process(delta):
	print("Hello World!")
```


### `position`

This is the X,Y,Z coordinate property on almost every single `Node` in Godot. 

Example: Change the Y coordinate of an object every second

```python
func _process(delta):
	self.position.y += 500 * delta
```

### `@export`

This is the Godot equivalent of making a variable public or global to the editor. It can now be changed not just from within inside the script, but as a property on the right-hand-side of the editor.

Example: export a speed variable that controls how fast are object moves

```python
@export var speed = 500
```