# TriSpark

A simple ThreeJS hit-spark system for games, based on a single triangle geometry.

__Currently under development.__

## Expected Usage

After adding the library to your page, `TriSpark` should be available as a global class.

Then, supposing you have a `scene`, to create a spark and play it once:

```javascript
var spark = TriSpark.new()
spark.addToScene(scene)
spark.play(1, 1, 0) // x, y, z
```

You can reuse the same spark as many times as you want. Just `play()` it whenever you need.

## WIP

This is a work in progress.
