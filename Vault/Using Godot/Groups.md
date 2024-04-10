Let's say I throw a ball, but this magic ball can phase throw floors but not walls. Well how do I make this ball bounce of walls but go through floors? Using `Groups`. 

We can group our objects in our game making them more unique and specific. Like only phase through collision boxes that belong to floors, and not walls. 

To create groups in Godot, go to `Node > Groups`:

![[Pasted image 20240410164311.png]]

for my example, I'm gonna create a `player` and `enemy` group, pertaining to what I am working on currently:

![[Pasted image 20240410164348.png]]

You can click `Manage Groups` to add what entities are pertaining to that group, specifically. 

Next in some code, you'll write something like this using a [[Signals and Hitboxes|Signal]]:

```python
# a signal connected to the hitbox
func _on_area_entered(area):
	# if something collides with us, and it's an "enemy", destroy it
	if area.is_in_group("enemy"):
		self.queue_free()
```

