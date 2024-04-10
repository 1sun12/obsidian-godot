A very important aspect of creating games is the re-use of already created assets and objects.  This is a little mini-tutorial of what that process looks like for Godot.

Here in my editor, I have a `Laser` object which I would like to re-use and spawn every time I left click with the mouse. 

![[Pasted image 20240410140240.png]]

First, we're going to export the laser as it's own entity. Saving it to our hard drive with all of it's settings just as they are with any scripts attached to it. We do this by `right-clicking on Laser > Save Branch as Scene`

![[Pasted image 20240410140409.png]]

Now that it is saved to our hard-drive as a Scene, inside our script of choice we are going to `@export` that data to the script. 

```python
@export var laserObj: PackedScene

# Example use of static typing in GDScript
var number: float = 100.0
```

The thing you should be focusing on is that first line, but the 2nd line is just another example of what this line actually *means...*

We are creating a variable, but instead of inferring the type, we are `statically typing` this variable of type `PackedScene`. Similar to how I am creating a `number` variable, but specifying that it is a `float` value. 

Now that we have exported the variable to the editor, from there, we can actually set it equal to the exported `Laser Scene` we created earlier:

![[Pasted image 20240410141346.png]]

Next, we can `instantiate` our object, which means to clone it into our world space.

```python
# _process(delta):
# ...
@export var laserObj: PackedScene

if Input.is_action_just_pressed("fireLaser"):
		# clone object into the world space
		var newLaser = laserObj.instantiate()
		# short hand for "get_parent().add_child(newLaser)"
		add_sibling(newLaser)
		# change the position of the laser after spawning
		newLaser.position = self.position
```


Left-clicking in our game will now create clones of the laser object.
