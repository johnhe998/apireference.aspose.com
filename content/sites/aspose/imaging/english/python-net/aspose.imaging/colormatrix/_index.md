---
title: ColorMatrix Class
type: docs
weight: 1160
url: /python-net/aspose.imaging/colormatrix/
---

Defines a 5 x 5 matrix that contains the coordinates for the RGBA space. Several methods of the [ImageAttributes](/imaging/python-net/aspose.imaging/imageattributes/) class adjust image colors by using a color matrix. This class cannot be inherited.

**Module:** [aspose.imaging](/imaging/python-net/aspose.imaging/)

**Full Name:** aspose.imaging.ColorMatrix

**Aspose.Imaging Version:** 23.6

The ColorMatrix type exposes the following members:
## **Constructors**
|**Name**|**Description**|
| :- | :- |
| [ColorMatrix()](#ColorMatrix__0) | Initializes a new instance of the [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/) class. |
| [ColorMatrix(new_color_matrix)](#ColorMatrix_new_color_matrix_1) | Initializes a new instance of the [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/) class using the elements in the specified matrix <paramref name="newColorMatrix" />. |
## **Properties**
|**Name**|**Type**|**Access**|**Description**|
| :- | :- | :- |
| matrix00 | float | r/w | Gets or sets the element at the 0 (zero) row and 0 column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix01 | float | r/w | Gets or sets the element at the 0 (zero) row and first column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix02 | float | r/w | Gets or sets the element at the 0 (zero) row and second column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix03 | float | r/w | Gets or sets the element at the 0 (zero) row and third column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix04 | float | r/w | Gets or sets the element at the 0 (zero) row and fourth column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix10 | float | r/w | Gets or sets the element at the first row and 0 (zero) column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix11 | float | r/w | Gets or sets the element at the first row and first column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix12 | float | r/w | Gets or sets the element at the first row and second column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix13 | float | r/w | Gets or sets the element at the first row and third column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix14 | float | r/w | Gets or sets the element at the first row and fourth column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix20 | float | r/w | Gets or sets the element at the second row and 0 (zero) column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix21 | float | r/w | Gets or sets the element at the second row and first column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix22 | float | r/w | Gets or sets the element at the second row and second column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix23 | float | r/w | Gets or sets the element at the second row and third column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix24 | float | r/w | Gets or sets the element at the second row and fourth column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix30 | float | r/w | Gets or sets the element at the third row and 0 (zero) column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix31 | float | r/w | Gets or sets the element at the third row and first column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix32 | float | r/w | Gets or sets the element at the third row and second column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix33 | float | r/w | Gets or sets the element at the third row and third column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix34 | float | r/w | Gets or sets the element at the third row and fourth column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix40 | float | r/w | Gets or sets the element at the fourth row and 0 (zero) column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix41 | float | r/w | Gets or sets the element at the fourth row and first column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix42 | float | r/w | Gets or sets the element at the fourth row and second column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix43 | float | r/w | Gets or sets the element at the fourth row and third column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| matrix44 | float | r/w | Gets or sets the element at the fourth row and fourth column of this [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| MATRIX_DIMENSION_ELEMENTS_COUNT [static] | int | r | The number of elements in matrix dimension. |
| MATRIX_DIMENSIONS_COUNT [static] | int | r | The number of matrix dimensions. |
| MATRIX_TOTAL_ELEMENTS_COUNT [static] | int | r | The total number of elements in the matrix. |
## **Methods**
| **Name** | **Description** |
| :- | :- |
| [get_matrix()](#get_matrix__2) | Gets the matrix values. |
| [get_elem(row, column)](#get_elem_row_column_3) | Gets the element at the specified row and column in the [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |
| [set_elem(row, column, value)](#set_elem_row_column_value_4) | Sets the element at the specified row and column in the [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |

### ColorMatrix() {#ColorMatrix__0}


```
 ColorMatrix() 
```

Initializes a new instance of the [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/) class.

### ColorMatrix(new_color_matrix) {#ColorMatrix_new_color_matrix_1}


```
 ColorMatrix(new_color_matrix) 
```

Initializes a new instance of the [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/) class using the elements in the specified matrix <paramref name="newColorMatrix" />.

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| new_color_matrix | float[] | The values of the elements for the new [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/). |

### get_matrix() {#get_matrix__2}


```
 get_matrix() 
```

Gets the matrix values.

**Returns**

| Type | Description |
| :- | :- |
| float[] | The matrix values array. |


### get_elem(row, column) {#get_elem_row_column_3}


```
 get_elem(row, column) 
```

Gets the element at the specified row and column in the [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/).

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| row | int | The row number. |
| column | int | The column number. |

**Returns**

| Type | Description |
| :- | :- |
| float | The element at the specified row and column. |


### set_elem(row, column, value) {#set_elem_row_column_value_4}


```
 set_elem(row, column, value) 
```

Sets the element at the specified row and column in the [ColorMatrix](/imaging/python-net/aspose.imaging/colormatrix/).

**Parameters:**

| Parameter | Type | Description |
| :- | :- | :- |
| row | int | The row number. |
| column | int | The column number. |
| value | float | The element at the specified row and column. |

