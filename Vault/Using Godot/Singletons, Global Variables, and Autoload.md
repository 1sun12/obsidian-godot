A `Singleton` is a [[What Are Nodes|Node]] that is global, and therefor accessible everywhere, or isn't really a child of anything at all. It's independently it's own thing. 

These are good for tracking information about your game, not relevant to just a single level or scene within your game. They also have the use-case of creating `global variables`.

Go to [[Project Settings]] `> Autoload` to create a `Singleton` [[What Are Nodes|Node]]. 

![[Pasted image 20240410161311.png]]

I already have one created called `GameState`, but anything located within this script is essentially global and accessible everywhere within my project.

If I write... inside my `Singleton` script
```python
var score = 0
```

I can now write this anywhere, in any script:

```python
# increase global variable score by 5
GameState.score += 5
```