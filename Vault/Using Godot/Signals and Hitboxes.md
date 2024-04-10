Events or, `Signals` is what Godot calls them, are an event-like scenario where we might want certain things to happen in our game when those things are taking place.

This small section will also refer to hitboxes as they are one of those types of events I am talking about.

Inside the Godot editor in the top-right portion, you can click on `Node` and it will show you available `Signals` to choose from in a list. If the list is empty, that means this type of `Node` you have selected doesn't have an `Signals` to choose from. A good example of a `Node` with lots of `Signals` is a `Area2D` object.

![[Pasted image 20240410150944.png]]

For this example, I'll be showcasing how we can trigger events every time something collides with the Hitbox on this object.

At the top of this list, click `area_entered`

![[Pasted image 20240410151112.png]]

Next you'll be asked what to connect it too, will be connecting this event to itself.

![[Pasted image 20240410151144.png]]

It will generate this code block in your script:

![[Pasted image 20240410151213.png]]

The little green arrow means that this function block belongs to a `Signal` or event as we said. That event being, if anything enters the area or hitbox of this object.

We want to destroy this object when anything enters it's hitbox. Below is the following code for that:

```python
func _on_area_entered(area):
	self.queue_free()
```

`self.queue_free()` means, to deallocate in memory. Or call the destructor. This object being stored in memory will be freed, hence, no longer exist, and will be deleted completely.