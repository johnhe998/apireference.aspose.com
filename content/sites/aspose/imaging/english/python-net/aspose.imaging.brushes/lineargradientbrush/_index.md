---
title: LinearGradientBrush Class
type: docs
weight: 20
url: /python-net/aspose.imaging.brushes/lineargradientbrush/
---

Encapsulates a [Brush](/imaging/python-net/aspose.imaging/brush/) with a linear gradient. This class cannot be inherited.

**Module:** [aspose.imaging.brushes](/imaging/python-net/aspose.imaging.brushes/)

**Full Name:** aspose.imaging.brushes.LinearGradientBrush

**Inheritance:** LinearGradientBrushBase

**Aspose.Imaging Version:** 23.6

The LinearGradientBrush type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [LinearGradientBrush()](#LinearGradientBrush__0) | Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class with default parameters.<br/>            The starting color is black, the ending color is white, the angle is 45 degrees and the rectangle is located in (0,0) with size (1,1). |
| [LinearGradientBrush(point1, point2, color1, color2)](#LinearGradientBrush_point1_point2_color1_color2_1) | Initializes a new instance of the LinearGradientBrush class |
| [LinearGradientBrush(point1, point2, color1, color2)](#LinearGradientBrush_point1_point2_color1_color2_2) | Initializes a new instance of the LinearGradientBrush class |
| [LinearGradientBrush(rect, color1, color2, angle)](#LinearGradientBrush_rect_color1_color2_angle_3) | Initializes a new instance of the LinearGradientBrush class |
| [LinearGradientBrush(rect, color1, color2, angle)](#LinearGradientBrush_rect_color1_color2_angle_4) | Initializes a new instance of the LinearGradientBrush class |
| [LinearGradientBrush(rect, color1, color2, angle, is_angle_scalable)](#LinearGradientBrush_rect_color1_color2_angle_is_angle_scalable_5) | Initializes a new instance of the LinearGradientBrush class |
| [LinearGradientBrush(rect, color1, color2, angle, is_angle_scalable)](#LinearGradientBrush_rect_color1_color2_angle_is_angle_scalable_6) | Initializes a new instance of the LinearGradientBrush class |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| disposed | bool | r | Gets a value indicating whether this instance is disposed. |
| opacity | float | r/w | Gets or sets the brush opacity. The value should be between 0 and 1. Value of 0 means that brush is fully visible, value of 1 means the brush is fully opaque. |
| wrap_mode | [WrapMode](/imaging/python-net/aspose.imaging/wrapmode) | r/w | Gets or sets a [WrapMode](/imaging/python-net/aspose.imaging/wrapmode/) enumeration that indicates the wrap mode for this [TransformBrush](/imaging/python-net/aspose.imaging.brushes/transformbrush/). |
| transform | [Matrix](/imaging/python-net/aspose.imaging/matrix) | r/w | Gets or sets a copy [Matrix](/imaging/python-net/aspose.imaging/matrix/) that defines a local geometric transform for this [TransformBrush](/imaging/python-net/aspose.imaging.brushes/transformbrush/). |
| is_transform_changed | bool | r | Gets a value indicating whether transformations were changed in some way. For example setting the transformation matrix or<br/>            calling any of the methods altering the transformation matrix. The property is introduced for backward compatibility with GDI+. |
| rectangle | [RectangleF](/imaging/python-net/aspose.imaging/rectanglef) | r/w | Gets or sets a rectangular region that defines the starting and ending points of the gradient. |
| angle | float | r/w | Gets or sets the gradient angle. |
| is_angle_scalable | bool | r/w | Gets or sets a value indicating whether [angle](/imaging/python-net/aspose.imaging.brushes/lineargradientbrushbase/) is changed during trasnformations with this [LinearGradientBrushBase](/imaging/python-net/aspose.imaging.brushes/lineargradientbrushbase/). |
| gamma_correction | bool | r/w | Gets or sets a value indicating whether gamma correction is enabled for this [LinearGradientBrushBase](/imaging/python-net/aspose.imaging.brushes/lineargradientbrushbase/). |
| interpolation_colors | [ColorBlend](/imaging/python-net/aspose.imaging/colorblend) | r/w | Gets or sets a [ColorBlend](/imaging/python-net/aspose.imaging/colorblend/) that defines a multicolor linear gradient. |
| linear_colors | [Color[]](/imaging/python-net/aspose.imaging/color) | r/w | Gets or sets the starting and ending colors of the gradient. |
| start_color | [Color](/imaging/python-net/aspose.imaging/color) | r/w | Gets or sets the starting gradient color. |
| end_color | [Color](/imaging/python-net/aspose.imaging/color) | r/w | Gets or sets the ending gradient color. |
| blend | [Blend](/imaging/python-net/aspose.imaging/blend) | r/w | Gets or sets a [Blend](/imaging/python-net/aspose.imaging/blend/) that specifies positions and factors that define a custom falloff for the gradient. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [multiply_transform(matrix)](#multiply_transform_matrix_7) | Multiplies the [Matrix](/imaging/python-net/aspose.imaging/matrix/) that represents the local geometric transform of this [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) by the specified [Matrix](/imaging/python-net/aspose.imaging/matrix/) by prepending the specified [Matrix](/imaging/python-net/aspose.imaging/matrix/). |
| [multiply_transform(matrix, order)](#multiply_transform_matrix_order_8) | Multiplies the [Matrix](/imaging/python-net/aspose.imaging/matrix/) that represents the local geometric transform of this [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) by the specified [Matrix](/imaging/python-net/aspose.imaging/matrix/) in the specified order. |
| [translate_transform(dx, dy)](#translate_transform_dx_dy_9) | Translates the local geometric transform by the specified dimensions. This method prepends the translation to the transform. |
| [translate_transform(dx, dy, order)](#translate_transform_dx_dy_order_10) | Translates the local geometric transform by the specified dimensions in the specified order. |
| [scale_transform(sx, sy)](#scale_transform_sx_sy_11) | Scales the local geometric transform by the specified amounts. This method prepends the scaling matrix to the transform. |
| [scale_transform(sx, sy, order)](#scale_transform_sx_sy_order_12) | Scales the local geometric transform by the specified amounts in the specified order. |
| [rotate_transform(angle)](#rotate_transform_angle_13) | Rotates the local geometric transform by the specified amount. This method prepends the rotation to the transform. |
| [rotate_transform(angle, order)](#rotate_transform_angle_order_14) | Rotates the local geometric transform by the specified amount in the specified order. |
| [set_sigma_bell_shape(focus)](#set_sigma_bell_shape_focus_15) | Creates a gradient falloff based on a bell-shaped curve. |
| [set_sigma_bell_shape(focus, scale)](#set_sigma_bell_shape_focus_scale_16) | Creates a gradient falloff based on a bell-shaped curve. |
| [set_blend_triangular_shape(focus)](#set_blend_triangular_shape_focus_17) | Creates a linear gradient with a center color and a linear falloff to a single color on both ends. |
| [set_blend_triangular_shape(focus, scale)](#set_blend_triangular_shape_focus_scale_18) | Creates a linear gradient with a center color and a linear falloff to a single color on both ends. |
| [deep_clone()](#deep_clone__19) | Creates a new deep clone of the current [Brush](/imaging/python-net/aspose.imaging/brush/). |
| reset_transform() | Resets the [transform](/imaging/python-net/aspose.imaging.brushes/transformbrush/) property to identity. |
| [create_with_points(point1, point2, color1, color2)](#create_with_points_point1_point2_color1_color2_20) | Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class with the specified points and colors. |
| [create_with_points_f(point1, point2, color1, color2)](#create_with_points_f_point1_point2_color1_color2_21) | Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class with the specified points and colors. |
| [create_with_rect_colors_angle(rect, color1, color2, angle)](#create_with_rect_colors_angle_rect_color1_color2_angle_22) | Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class based on a rectangle, starting and ending colors, and an orientation angle. |
| [create_with_rect_f_colors_angle(rect, color1, color2, angle)](#create_with_rect_f_colors_angle_rect_color1_color2_angle_23) | Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class based on a rectangle, starting and ending colors, and an orientation angle. |
| [create_with_rect_colors_angle_scalable(rect, color1, color2, angle, is_angle_scalable)](#create_with_rect_colors_angle_scalable_rect_color1_color2_angle_is_angle_scalable_24) | Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class based on a rectangle, starting and ending colors, and an orientation angle. |
| [create_with_rect_f_colors_angle_scalable(rect, color1, color2, angle, is_angle_scalable)](#create_with_rect_f_colors_angle_scalable_rect_color1_color2_angle_is_angle_scalable_25) | Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class based on a rectangle, starting and ending colors, and an orientation angle. |

### LinearGradientBrush() {#LinearGradientBrush__0}


```
 LinearGradientBrush() 
```

Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class with default parameters.<br/>            The starting color is black, the ending color is white, the angle is 45 degrees and the rectangle is located in (0,0) with size (1,1).

### LinearGradientBrush(point1, point2, color1, color2) {#LinearGradientBrush_point1_point2_color1_color2_1}


```
 LinearGradientBrush(point1, point2, color1, color2) 
```

Initializes a new instance of the LinearGradientBrush class

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| point1 | [Point](/imaging/python-net/aspose.imaging/point) |  |
| point2 | [Point](/imaging/python-net/aspose.imaging/point) |  |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) |  |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) |  |

### LinearGradientBrush(point1, point2, color1, color2) {#LinearGradientBrush_point1_point2_color1_color2_2}


```
 LinearGradientBrush(point1, point2, color1, color2) 
```

Initializes a new instance of the LinearGradientBrush class

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| point1 | [PointF](/imaging/python-net/aspose.imaging/pointf) |  |
| point2 | [PointF](/imaging/python-net/aspose.imaging/pointf) |  |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) |  |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) |  |

### LinearGradientBrush(rect, color1, color2, angle) {#LinearGradientBrush_rect_color1_color2_angle_3}


```
 LinearGradientBrush(rect, color1, color2, angle) 
```

Initializes a new instance of the LinearGradientBrush class

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rect | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) |  |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) |  |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) |  |
| angle | float |  |

### LinearGradientBrush(rect, color1, color2, angle) {#LinearGradientBrush_rect_color1_color2_angle_4}


```
 LinearGradientBrush(rect, color1, color2, angle) 
```

Initializes a new instance of the LinearGradientBrush class

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rect | [RectangleF](/imaging/python-net/aspose.imaging/rectanglef) |  |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) |  |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) |  |
| angle | float |  |

### LinearGradientBrush(rect, color1, color2, angle, is_angle_scalable) {#LinearGradientBrush_rect_color1_color2_angle_is_angle_scalable_5}


```
 LinearGradientBrush(rect, color1, color2, angle, is_angle_scalable) 
```

Initializes a new instance of the LinearGradientBrush class

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rect | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) |  |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) |  |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) |  |
| angle | float |  |
| is_angle_scalable | bool |  |

### LinearGradientBrush(rect, color1, color2, angle, is_angle_scalable) {#LinearGradientBrush_rect_color1_color2_angle_is_angle_scalable_6}


```
 LinearGradientBrush(rect, color1, color2, angle, is_angle_scalable) 
```

Initializes a new instance of the LinearGradientBrush class

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rect | [RectangleF](/imaging/python-net/aspose.imaging/rectanglef) |  |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) |  |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) |  |
| angle | float |  |
| is_angle_scalable | bool |  |

### multiply_transform(matrix) {#multiply_transform_matrix_7}


```
 multiply_transform(matrix) 
```

Multiplies the [Matrix](/imaging/python-net/aspose.imaging/matrix/) that represents the local geometric transform of this [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) by the specified [Matrix](/imaging/python-net/aspose.imaging/matrix/) by prepending the specified [Matrix](/imaging/python-net/aspose.imaging/matrix/).

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| matrix | [Matrix](/imaging/python-net/aspose.imaging/matrix) | The [Matrix](/imaging/python-net/aspose.imaging/matrix/) by which to multiply the geometric transform. |

### multiply_transform(matrix, order) {#multiply_transform_matrix_order_8}


```
 multiply_transform(matrix, order) 
```

Multiplies the [Matrix](/imaging/python-net/aspose.imaging/matrix/) that represents the local geometric transform of this [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) by the specified [Matrix](/imaging/python-net/aspose.imaging/matrix/) in the specified order.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| matrix | [Matrix](/imaging/python-net/aspose.imaging/matrix) | The [Matrix](/imaging/python-net/aspose.imaging/matrix/) by which to multiply the geometric transform. |
| order | [MatrixOrder](/imaging/python-net/aspose.imaging/matrixorder) | A [MatrixOrder](/imaging/python-net/aspose.imaging/matrixorder/) that specifies in which order to multiply the two matrices. |

### translate_transform(dx, dy) {#translate_transform_dx_dy_9}


```
 translate_transform(dx, dy) 
```

Translates the local geometric transform by the specified dimensions. This method prepends the translation to the transform.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| dx | float | The value of the translation in x. |
| dy | float | The value of the translation in y. |

### translate_transform(dx, dy, order) {#translate_transform_dx_dy_order_10}


```
 translate_transform(dx, dy, order) 
```

Translates the local geometric transform by the specified dimensions in the specified order.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| dx | float | The value of the translation in x. |
| dy | float | The value of the translation in y. |
| order | [MatrixOrder](/imaging/python-net/aspose.imaging/matrixorder) | The order (prepend or append) in which to apply the translation. |

### scale_transform(sx, sy) {#scale_transform_sx_sy_11}


```
 scale_transform(sx, sy) 
```

Scales the local geometric transform by the specified amounts. This method prepends the scaling matrix to the transform.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| sx | float | The amount by which to scale the transform in the x-axis direction. |
| sy | float | The amount by which to scale the transform in the y-axis direction. |

### scale_transform(sx, sy, order) {#scale_transform_sx_sy_order_12}


```
 scale_transform(sx, sy, order) 
```

Scales the local geometric transform by the specified amounts in the specified order.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| sx | float | The amount by which to scale the transform in the x-axis direction. |
| sy | float | The amount by which to scale the transform in the y-axis direction. |
| order | [MatrixOrder](/imaging/python-net/aspose.imaging/matrixorder) | A [MatrixOrder](/imaging/python-net/aspose.imaging/matrixorder/) that specifies whether to append or prepend the scaling matrix. |

### rotate_transform(angle) {#rotate_transform_angle_13}


```
 rotate_transform(angle) 
```

Rotates the local geometric transform by the specified amount. This method prepends the rotation to the transform.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| angle | float | The angle of rotation. |

### rotate_transform(angle, order) {#rotate_transform_angle_order_14}


```
 rotate_transform(angle, order) 
```

Rotates the local geometric transform by the specified amount in the specified order.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| angle | float | The angle of rotation. |
| order | [MatrixOrder](/imaging/python-net/aspose.imaging/matrixorder) | A [MatrixOrder](/imaging/python-net/aspose.imaging/matrixorder/) that specifies whether to append or prepend the rotation matrix. |

### set_sigma_bell_shape(focus) {#set_sigma_bell_shape_focus_15}


```
 set_sigma_bell_shape(focus) 
```

Creates a gradient falloff based on a bell-shaped curve.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| focus | float | A value from 0 through 1 that specifies the center of the gradient (the point where the starting color and ending color are blended equally). |

### set_sigma_bell_shape(focus, scale) {#set_sigma_bell_shape_focus_scale_16}


```
 set_sigma_bell_shape(focus, scale) 
```

Creates a gradient falloff based on a bell-shaped curve.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| focus | float | A value from 0 through 1 that specifies the center of the gradient (the point where the gradient is composed of only the ending color). |
| scale | float | A value from 0 through 1 that specifies how fast the colors falloff from the <paramref name="focus" />. |

### set_blend_triangular_shape(focus) {#set_blend_triangular_shape_focus_17}


```
 set_blend_triangular_shape(focus) 
```

Creates a linear gradient with a center color and a linear falloff to a single color on both ends.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| focus | float | A value from 0 through 1 that specifies the center of the gradient (the point where the gradient is composed of only the ending color). |

### set_blend_triangular_shape(focus, scale) {#set_blend_triangular_shape_focus_scale_18}


```
 set_blend_triangular_shape(focus, scale) 
```

Creates a linear gradient with a center color and a linear falloff to a single color on both ends.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| focus | float | A value from 0 through 1 that specifies the center of the gradient (the point where the gradient is composed of only the ending color). |
| scale | float | A value from 0 through1 that specifies how fast the colors falloff from the starting color to <paramref name="focus" /> (ending color) |

### deep_clone() {#deep_clone__19}


```
 deep_clone() 
```

Creates a new deep clone of the current [Brush](/imaging/python-net/aspose.imaging/brush/).

**Returns**

| Type | Description |
| :- | :- |
| [Brush](/imaging/python-net/aspose.imaging/brush) | A new [Brush](/imaging/python-net/aspose.imaging/brush/) which is the deep clone of this [Brush](/imaging/python-net/aspose.imaging/brush/) instance. |


### create_with_points(point1, point2, color1, color2)  [static] {#create_with_points_point1_point2_color1_color2_20}


```
 create_with_points(point1, point2, color1, color2) 
```

Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class with the specified points and colors.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| point1 | [Point](/imaging/python-net/aspose.imaging/point) | A [Point](/imaging/python-net/aspose.imaging/point/) structure that represents the starting point of the linear gradient. |
| point2 | [Point](/imaging/python-net/aspose.imaging/point) | A [Point](/imaging/python-net/aspose.imaging/point/) structure that represents the endpoint of the linear gradient. |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the starting color of the linear gradient. |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the ending color of the linear gradient. |

**Returns**

| Type | Description |
| :- | :- |
| [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush) |  |


### create_with_points_f(point1, point2, color1, color2)  [static] {#create_with_points_f_point1_point2_color1_color2_21}


```
 create_with_points_f(point1, point2, color1, color2) 
```

Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class with the specified points and colors.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| point1 | [PointF](/imaging/python-net/aspose.imaging/pointf) | A [PointF](/imaging/python-net/aspose.imaging/pointf/) structure that represents the starting point of the linear gradient. |
| point2 | [PointF](/imaging/python-net/aspose.imaging/pointf) | A [PointF](/imaging/python-net/aspose.imaging/pointf/) structure that represents the endpoint of the linear gradient. |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the starting color of the linear gradient. |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the ending color of the linear gradient. |

**Returns**

| Type | Description |
| :- | :- |
| [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush) |  |


### create_with_rect_colors_angle(rect, color1, color2, angle)  [static] {#create_with_rect_colors_angle_rect_color1_color2_angle_22}


```
 create_with_rect_colors_angle(rect, color1, color2, angle) 
```

Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class based on a rectangle, starting and ending colors, and an orientation angle.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rect | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | A [RectangleF](/imaging/python-net/aspose.imaging/rectanglef/) structure that specifies the bounds of the linear gradient. |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the starting color for the gradient. |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the ending color for the gradient. |
| angle | float | The angle, measured in degrees clockwise from the x-axis, of the gradient's orientation line. |

**Returns**

| Type | Description |
| :- | :- |
| [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush) |  |


### create_with_rect_f_colors_angle(rect, color1, color2, angle)  [static] {#create_with_rect_f_colors_angle_rect_color1_color2_angle_23}


```
 create_with_rect_f_colors_angle(rect, color1, color2, angle) 
```

Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class based on a rectangle, starting and ending colors, and an orientation angle.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rect | [RectangleF](/imaging/python-net/aspose.imaging/rectanglef) | A [RectangleF](/imaging/python-net/aspose.imaging/rectanglef/) structure that specifies the bounds of the linear gradient. |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the starting color for the gradient. |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the ending color for the gradient. |
| angle | float | The angle, measured in degrees clockwise from the x-axis, of the gradient's orientation line. |

**Returns**

| Type | Description |
| :- | :- |
| [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush) |  |


### create_with_rect_colors_angle_scalable(rect, color1, color2, angle, is_angle_scalable)  [static] {#create_with_rect_colors_angle_scalable_rect_color1_color2_angle_is_angle_scalable_24}


```
 create_with_rect_colors_angle_scalable(rect, color1, color2, angle, is_angle_scalable) 
```

Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class based on a rectangle, starting and ending colors, and an orientation angle.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rect | [Rectangle](/imaging/python-net/aspose.imaging/rectangle) | A [RectangleF](/imaging/python-net/aspose.imaging/rectanglef/) structure that specifies the bounds of the linear gradient. |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the starting color for the gradient. |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the ending color for the gradient. |
| angle | float | The angle, measured in degrees clockwise from the x-axis, of the gradient's orientation line. |
| is_angle_scalable | bool | if set to <c>true</c> the angle is changed during transformations with this [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/). |

**Returns**

| Type | Description |
| :- | :- |
| [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush) |  |


### create_with_rect_f_colors_angle_scalable(rect, color1, color2, angle, is_angle_scalable)  [static] {#create_with_rect_f_colors_angle_scalable_rect_color1_color2_angle_is_angle_scalable_25}


```
 create_with_rect_f_colors_angle_scalable(rect, color1, color2, angle, is_angle_scalable) 
```

Initializes a new instance of the [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/) class based on a rectangle, starting and ending colors, and an orientation angle.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| rect | [RectangleF](/imaging/python-net/aspose.imaging/rectanglef) | A [RectangleF](/imaging/python-net/aspose.imaging/rectanglef/) structure that specifies the bounds of the linear gradient. |
| color1 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the starting color for the gradient. |
| color2 | [Color](/imaging/python-net/aspose.imaging/color) | A [Color](/imaging/python-net/aspose.imaging/color/) structure that represents the ending color for the gradient. |
| angle | float | The angle, measured in degrees clockwise from the x-axis, of the gradient's orientation line. |
| is_angle_scalable | bool | if set to <c>true</c> the angle is changed during transformations with this [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush/). |

**Returns**

| Type | Description |
| :- | :- |
| [LinearGradientBrush](/imaging/python-net/aspose.imaging.brushes/lineargradientbrush) |  |


