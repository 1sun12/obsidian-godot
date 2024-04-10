Within your game, I will assume you will have a lot of controls for it. Like clicking stuff, keyboard actions, etc. 

How you map these controls is inside your `Project > Project Settings... > Input Map`

![[Pasted image 20240410132659.png]]

For example, I'm going to add a `fireLaser` action, that happens when I left click.

![[Pasted image 20240410132816.png]]

Next, hit the `+` symbol located on the right of your newly created action, to bind it to a key.

![[Pasted image 20240410132930.png]]

To use your newly created input inside your code, you will use the `Input` class. This example below is a `boolean` statement. Can be used nicely with `if statements`

```python
Input.is_action_just_pressed("fireLaser")
```