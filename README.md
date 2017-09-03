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

The default mode. Draws a eight-point star that quickly grows and fades out. The bases of the triangles do not shrink.

### `THIN_SPARK_MODE`

Same as `SPARK_MODE` but the bases of the triangles will shrink, creating a more slim effect.

### `HOLLOW_SPARK_MODE`

Same as `SPARK_MODE`, but with a hole in the center.

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
var sparkCloud = new TriSparkCloud(10) // maximum of 10 simultaneous sparks
sparkCloud.addToScene(scene)
```

Then use the same methods as you would with a single instance:

```javascript
// Play three sparks at once in different places
sparkCloud.play(1, 1, 0)
sparkCloud.play(2, 1, 0)
sparkCloud.play(3, 1, 0)
```

In the example above, if an eleventh spark is requested to play while ten others are still playing, the first spark will be stopped and reused.

## Options

Options can be defined after any `TriSpark` or `TriSparkCloud` instance is created.

Default values are specified below.

```javascript
var spark = new TriSpark()
spark.color = '#FF00FF'
spark.opacity = 40    // 0 = transparent, 100 = opaque
spark.size = 1        // affects the triangle length
spark.gutter = 0      // the space between the center and the base of each triangle
spark.triangles = 8   // any even number greater than 2
```

## WIP

This is a work in progress.
