# TriSpark

A simple ThreeJS hit-spark system for games, based on a single triangle geometry.

__Currently under development.__

## Expected Usage

After adding the library to your page, `TriSpark` should be available as a global class.

Then, supposing you have a `scene`, to create a reusable spark:

```javascript
var spark = new TriSpark()
spark.addToScene(scene)
```

Then, you can play it as many times as you want:

```javascript
spark.play(1, 1, 0) // x, y, z - scene coordinates
```

## Modes

A single `TriSpark` instance can play different effects without need of new objects.

Pass the desired effect as the fourth parameter of the `play()` method.

```javascript
spark.play(1, 1, 0, SPARK_MODE)
```

### `SPARK_MODE`

The default mode. Draws a eight-point star that quickly grows and fades out.

### `HOLLOW_SPARK_MODE`

Same as the default mode, but with a hole in the center, and the width of the triangles do not change during animation.

### `ARC_SPARK_MODE`

Draws the triangles in an arc-like manner. The general direction the arc is pointing towards to can be defined as the fifth parameters in the `play()` method, as an integer representing the "NumPad" direction.

```javascript
// plays the spark on the ground, with the triangles pointing upwards
spark.play(0, 0, 0, ARC_SPARK_MODE, 8)
```

## Cloud Mode

Handles a group of reusable sparks that can be played simultaneously.

Setup it with:

```javascript
var sparkCloud = new TriSparkCloud(10) // maximum of 8 simultaneous sparks
sparkCloud.addToScene(scene)
```

Then use the same methods as you would with a single instance:

```javascript
// Play three sparks at once
sparkCloud.play(1, 1, 0)
sparkCloud.play(2, 1, 0)
sparkCloud.play(3, 1, 0)
```

In the example above, if an eleventh spark is requested to play while ten others are still playing, the first spark will be stopped, reset, and reused.

## WIP

This is a work in progress.
