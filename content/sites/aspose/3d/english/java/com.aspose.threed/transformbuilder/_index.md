---
title: TransformBuilder
second_title: Aspose.3D for Java API Reference
description: The  is used to build transform matrix by a chain of transformations.
type: docs
weight: 177
url: /java/com.aspose.threed/transformbuilder/
---

**Inheritance:**
java.lang.Object
```
public class TransformBuilder
```

The [TransformBuilder](../../com.aspose.threed/transformbuilder) is used to build transform matrix by a chain of transformations.
## Constructors

| Constructor | Description |
| --- | --- |
| [TransformBuilder(Matrix4 initial, ComposeOrder order)](#TransformBuilder-com.aspose.threed.Matrix4-com.aspose.threed.ComposeOrder-) | Construct a [TransformBuilder](../../com.aspose.threed/transformbuilder) with initial transform matrix and specified compose order |
| [TransformBuilder(ComposeOrder order)](#TransformBuilder-com.aspose.threed.ComposeOrder-) | Construct a [TransformBuilder](../../com.aspose.threed/transformbuilder) with initial identity transform matrix and specified compose order |
| [TransformBuilder()](#TransformBuilder--) | Construct a [TransformBuilder](../../com.aspose.threed/transformbuilder) with initial identity transform matrix and specified compose order |
## Methods

| Method | Description |
| --- | --- |
| [append(Matrix4 m)](#append-com.aspose.threed.Matrix4-) | Append the new transform matrix to the transform chain. |
| [compose(Matrix4 m)](#compose-com.aspose.threed.Matrix4-) | Append or prepend the argument to internal matrix. |
| [equals(Object arg0)](#equals-java.lang.Object-) |  |
| [getClass()](#getClass--) |  |
| [getComposeOrder()](#getComposeOrder--) | Gets the chain compose order. |
| [getMatrix()](#getMatrix--) | Gets the current matrix value |
| [hashCode()](#hashCode--) |  |
| [notify()](#notify--) |  |
| [notifyAll()](#notifyAll--) |  |
| [prepend(Matrix4 m)](#prepend-com.aspose.threed.Matrix4-) | Prepend the new transform matrix to the transform chain. |
| [rearrange(Axis newX, Axis newY, Axis newZ)](#rearrange-com.aspose.threed.Axis-com.aspose.threed.Axis-com.aspose.threed.Axis-) | Rearrange the layout of the axis. |
| [reset()](#reset--) | Reset the transform to identity matrix |
| [rotate(Quaternion q)](#rotate-com.aspose.threed.Quaternion-) | Chain a rotation by a quaternion |
| [rotateDegree(Vector3 rot, RotationOrder order)](#rotateDegree-com.aspose.threed.Vector3-com.aspose.threed.RotationOrder-) | Append rotation with specified order |
| [rotateDegree(double angle, Vector3 axis)](#rotateDegree-double-com.aspose.threed.Vector3-) | Chain a rotation transform in degree |
| [rotateEulerDegree(double degX, double degY, double degZ)](#rotateEulerDegree-double-double-double-) | Chain a rotation by Euler angles in degree |
| [rotateEulerRadian(Vector3 r)](#rotateEulerRadian-com.aspose.threed.Vector3-) | Chain a rotation by Euler angles in radian |
| [rotateEulerRadian(double x, double y, double z)](#rotateEulerRadian-double-double-double-) | Chain a rotation by Euler angles in radian |
| [rotateRadian(Vector3 rot, RotationOrder order)](#rotateRadian-com.aspose.threed.Vector3-com.aspose.threed.RotationOrder-) | Append rotation with specified order |
| [rotateRadian(double angle, Vector3 axis)](#rotateRadian-double-com.aspose.threed.Vector3-) | Chain a rotation transform in radian |
| [scale(Vector3 s)](#scale-com.aspose.threed.Vector3-) | Chain a scale transform |
| [scale(double s)](#scale-double-) | Chain a scaling transform matrix with a component scaled by s |
| [scale(double x, double y, double z)](#scale-double-double-double-) | Chain a scaling transform matrix |
| [setComposeOrder(ComposeOrder value)](#setComposeOrder-com.aspose.threed.ComposeOrder-) | Sets the chain compose order. |
| [setMatrix(Matrix4 value)](#setMatrix-com.aspose.threed.Matrix4-) | Sets the current matrix value |
| [toString()](#toString--) |  |
| [translate(Vector3 v)](#translate-com.aspose.threed.Vector3-) | Chain a translation transform |
| [translate(double tx, double ty, double tz)](#translate-double-double-double-) | Chain a translation transform |
| [wait()](#wait--) |  |
| [wait(long arg0)](#wait-long-) |  |
| [wait(long arg0, int arg1)](#wait-long-int-) |  |
### TransformBuilder(Matrix4 initial, ComposeOrder order) {#TransformBuilder-com.aspose.threed.Matrix4-com.aspose.threed.ComposeOrder-}
```
public TransformBuilder(Matrix4 initial, ComposeOrder order)
```


Construct a [TransformBuilder](../../com.aspose.threed/transformbuilder) with initial transform matrix and specified compose order

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| initial | [Matrix4](../../com.aspose.threed/matrix4) |  |
| order | [ComposeOrder](../../com.aspose.threed/composeorder) |  |

### TransformBuilder(ComposeOrder order) {#TransformBuilder-com.aspose.threed.ComposeOrder-}
```
public TransformBuilder(ComposeOrder order)
```


Construct a [TransformBuilder](../../com.aspose.threed/transformbuilder) with initial identity transform matrix and specified compose order

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| order | [ComposeOrder](../../com.aspose.threed/composeorder) |  |

### TransformBuilder() {#TransformBuilder--}
```
public TransformBuilder()
```


Construct a [TransformBuilder](../../com.aspose.threed/transformbuilder) with initial identity transform matrix and specified compose order

### append(Matrix4 m) {#append-com.aspose.threed.Matrix4-}
```
public TransformBuilder append(Matrix4 m)
```


Append the new transform matrix to the transform chain.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| m | [Matrix4](../../com.aspose.threed/matrix4) |  |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### compose(Matrix4 m) {#compose-com.aspose.threed.Matrix4-}
```
public void compose(Matrix4 m)
```


Append or prepend the argument to internal matrix.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| m | [Matrix4](../../com.aspose.threed/matrix4) |  |

### equals(Object arg0) {#equals-java.lang.Object-}
```
public boolean equals(Object arg0)
```




**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| arg0 | java.lang.Object |  |

**Returns:**
boolean
### getClass() {#getClass--}
```
public final native Class<?> getClass()
```




**Returns:**
java.lang.Class<?>
### getComposeOrder() {#getComposeOrder--}
```
public ComposeOrder getComposeOrder()
```


Gets the chain compose order.

**Returns:**
[ComposeOrder](../../com.aspose.threed/composeorder)
### getMatrix() {#getMatrix--}
```
public Matrix4 getMatrix()
```


Gets the current matrix value

**Returns:**
[Matrix4](../../com.aspose.threed/matrix4)
### hashCode() {#hashCode--}
```
public native int hashCode()
```




**Returns:**
int
### notify() {#notify--}
```
public final native void notify()
```




### notifyAll() {#notifyAll--}
```
public final native void notifyAll()
```




### prepend(Matrix4 m) {#prepend-com.aspose.threed.Matrix4-}
```
public TransformBuilder prepend(Matrix4 m)
```


Prepend the new transform matrix to the transform chain.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| m | [Matrix4](../../com.aspose.threed/matrix4) |  |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### rearrange(Axis newX, Axis newY, Axis newZ) {#rearrange-com.aspose.threed.Axis-com.aspose.threed.Axis-com.aspose.threed.Axis-}
```
public TransformBuilder rearrange(Axis newX, Axis newY, Axis newZ)
```


Rearrange the layout of the axis.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| newX | [Axis](../../com.aspose.threed/axis) | The new x component source |
| newY | [Axis](../../com.aspose.threed/axis) | The new y component source |
| newZ | [Axis](../../com.aspose.threed/axis) | The new z component source |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### reset() {#reset--}
```
public void reset()
```


Reset the transform to identity matrix

### rotate(Quaternion q) {#rotate-com.aspose.threed.Quaternion-}
```
public TransformBuilder rotate(Quaternion q)
```


Chain a rotation by a quaternion

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| q | [Quaternion](../../com.aspose.threed/quaternion) |  |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### rotateDegree(Vector3 rot, RotationOrder order) {#rotateDegree-com.aspose.threed.Vector3-com.aspose.threed.RotationOrder-}
```
public void rotateDegree(Vector3 rot, RotationOrder order)
```


Append rotation with specified order

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| rot | [Vector3](../../com.aspose.threed/vector3) | Rotation in degrees |
| order | [RotationOrder](../../com.aspose.threed/rotationorder) |  |

### rotateDegree(double angle, Vector3 axis) {#rotateDegree-double-com.aspose.threed.Vector3-}
```
public TransformBuilder rotateDegree(double angle, Vector3 axis)
```


Chain a rotation transform in degree

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| angle | double | The angle to rotate in degree |
| axis | [Vector3](../../com.aspose.threed/vector3) | The axis to rotate |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### rotateEulerDegree(double degX, double degY, double degZ) {#rotateEulerDegree-double-double-double-}
```
public TransformBuilder rotateEulerDegree(double degX, double degY, double degZ)
```


Chain a rotation by Euler angles in degree

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| degX | double |  |
| degY | double |  |
| degZ | double |  |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### rotateEulerRadian(Vector3 r) {#rotateEulerRadian-com.aspose.threed.Vector3-}
```
public TransformBuilder rotateEulerRadian(Vector3 r)
```


Chain a rotation by Euler angles in radian

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| r | [Vector3](../../com.aspose.threed/vector3) |  |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### rotateEulerRadian(double x, double y, double z) {#rotateEulerRadian-double-double-double-}
```
public TransformBuilder rotateEulerRadian(double x, double y, double z)
```


Chain a rotation by Euler angles in radian

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| x | double |  |
| y | double |  |
| z | double |  |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### rotateRadian(Vector3 rot, RotationOrder order) {#rotateRadian-com.aspose.threed.Vector3-com.aspose.threed.RotationOrder-}
```
public void rotateRadian(Vector3 rot, RotationOrder order)
```


Append rotation with specified order

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| rot | [Vector3](../../com.aspose.threed/vector3) | Rotation in radian |
| order | [RotationOrder](../../com.aspose.threed/rotationorder) |  |

### rotateRadian(double angle, Vector3 axis) {#rotateRadian-double-com.aspose.threed.Vector3-}
```
public TransformBuilder rotateRadian(double angle, Vector3 axis)
```


Chain a rotation transform in radian

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| angle | double | The angle to rotate in radian |
| axis | [Vector3](../../com.aspose.threed/vector3) | The axis to rotate |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### scale(Vector3 s) {#scale-com.aspose.threed.Vector3-}
```
public TransformBuilder scale(Vector3 s)
```


Chain a scale transform

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| s | [Vector3](../../com.aspose.threed/vector3) |  |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### scale(double s) {#scale-double-}
```
public TransformBuilder scale(double s)
```


Chain a scaling transform matrix with a component scaled by s

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| s | double |  |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### scale(double x, double y, double z) {#scale-double-double-double-}
```
public TransformBuilder scale(double x, double y, double z)
```


Chain a scaling transform matrix

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| x | double |  |
| y | double |  |
| z | double |  |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### setComposeOrder(ComposeOrder value) {#setComposeOrder-com.aspose.threed.ComposeOrder-}
```
public void setComposeOrder(ComposeOrder value)
```


Sets the chain compose order.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| value | [ComposeOrder](../../com.aspose.threed/composeorder) | New value |

### setMatrix(Matrix4 value) {#setMatrix-com.aspose.threed.Matrix4-}
```
public void setMatrix(Matrix4 value)
```


Sets the current matrix value

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| value | [Matrix4](../../com.aspose.threed/matrix4) | New value |

### toString() {#toString--}
```
public String toString()
```




**Returns:**
java.lang.String
### translate(Vector3 v) {#translate-com.aspose.threed.Vector3-}
```
public TransformBuilder translate(Vector3 v)
```


Chain a translation transform

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| v | [Vector3](../../com.aspose.threed/vector3) |  |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### translate(double tx, double ty, double tz) {#translate-double-double-double-}
```
public TransformBuilder translate(double tx, double ty, double tz)
```


Chain a translation transform

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| tx | double |  |
| ty | double |  |
| tz | double |  |

**Returns:**
[TransformBuilder](../../com.aspose.threed/transformbuilder)
### wait() {#wait--}
```
public final void wait()
```




### wait(long arg0) {#wait-long-}
```
public final native void wait(long arg0)
```




**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| arg0 | long |  |

### wait(long arg0, int arg1) {#wait-long-int-}
```
public final void wait(long arg0, int arg1)
```




**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| arg0 | long |  |
| arg1 | int |  |

