There's a lot of ways to create and manipulate different UI elements in Godot, but will start with a very basic `Label` and edit it with code. 

First, we're going to create a [[What Are Nodes|Node]] of type `Label`:

![[Pasted image 20240410162005.png]]

You can adjust what the label says inside it's properties on the right-hand side of the editor, and other settings about this basic text object.

On the right hand side, you're also going to find where it says `Label Settings` and create `New Label Settings`:

![[Pasted image 20240410162139.png]]

Then, physically click on `LabelSettings` once created to get this pop-up:

![[Pasted image 20240410162226.png]]

This will give you more advanced options for your text box.

You can edit the text written with some code that looks like this:

```python
# set the text every tick to some text + the increasing game score

extends Label

func _process(delta):
	self.text = "Score: " + str(GameState.score)
```