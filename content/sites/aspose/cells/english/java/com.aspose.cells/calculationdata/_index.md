---
title: CalculationData
second_title: Aspose.Cells for Java API Reference
description: Represents the required data when calculating one function such as function name parameters ...etc.
type: docs
url: /java/com.aspose.cells/calculationdata/
---

**Inheritance:**
java.lang.Object
```
public class CalculationData
```

Represents the required data when calculating one function, such as function name, parameters, ...etc.

**Remarks**

All objects provided by this class are for "read" purpose only. User should not change any data in the Workbook during the formula calculation process, Otherwise unexpected result or Exception may be caused.
## Methods

| Method | Description |
| --- | --- |
| [equals(Object arg0)](#equals-java.lang.Object-) |  |
| [getCalculatedValue()](#getCalculatedValue--) | Gets the calculated value for this function. |
| [getCell()](#getCell--) | Gets the Cell object where the function is in. |
| [getCellColumn()](#getCellColumn--) | Gets the column index of the cell where the function is in. |
| [getCellRow()](#getCellRow--) | Gets the row index of the cell where the function is in. |
| [getClass()](#getClass--) |  |
| [getFunctionName()](#getFunctionName--) | Gets the function name to be calculated. |
| [getParamCount()](#getParamCount--) | Gets the count of parameters |
| [getParamText(int index)](#getParamText-int-) | Gets the literal text of the parameter at given index. |
| [getParamValue(int index)](#getParamValue-int-) | Gets the represented value object of the parameter at given index. |
| [getWorkbook()](#getWorkbook--) | Gets the Workbook object where the function is in. |
| [getWorksheet()](#getWorksheet--) | Gets the Worksheet object where the function is in. |
| [hashCode()](#hashCode--) |  |
| [notify()](#notify--) |  |
| [notifyAll()](#notifyAll--) |  |
| [setCalculatedValue(Object value)](#setCalculatedValue-java.lang.Object-) | Sets the calculated value for this function. |
| [toString()](#toString--) |  |
| [wait()](#wait--) |  |
| [wait(long arg0)](#wait-long-) |  |
| [wait(long arg0, int arg1)](#wait-long-int-) |  |
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
### getCalculatedValue() {#getCalculatedValue--}
```
public Object getCalculatedValue()
```


Gets the calculated value for this function.

**Remarks**

User should set this property in his custom calculation engine for those functions the engine supports, and the set value will be returned when getting this property later. The set value may be of possible types of [Cell.getValue()](../../com.aspose.cells/cell\#getValue--), or array of such kind of values, or a Range, Name, ReferredArea. Getting this property before setting value to it will make the function be calculated by the default calculation engine of Aspose.Cells and then the calculated value will be returned(generally it should be \#NAME? for user-defined functions).

**Returns:**
java.lang.Object
### getCell() {#getCell--}
```
public Cell getCell()
```


Gets the Cell object where the function is in.

**Remarks**

When calculating a formula without setting it to a cell, such as by [Worksheet.calculateFormula(String,CalculationOptions)](../../com.aspose.cells/worksheet\#calculateFormula-String-CalculationOptions-), the formula will be calculated just like it has been set to cell A1, so both [getCellRow()](../../com.aspose.cells/calculationdata\#getCellRow--) and [getCellColumn()](../../com.aspose.cells/calculationdata\#getCellColumn--) are 0. However, cell A1 in the worksheet may has not been instantiated. So for such kind of situation this property will be null.

**Returns:**
[Cell](../../com.aspose.cells/cell)
### getCellColumn() {#getCellColumn--}
```
public int getCellColumn()
```


Gets the column index of the cell where the function is in.

**Returns:**
int
### getCellRow() {#getCellRow--}
```
public int getCellRow()
```


Gets the row index of the cell where the function is in.

**Returns:**
int
### getClass() {#getClass--}
```
public final native Class<?> getClass()
```




**Returns:**
java.lang.Class<?>
### getFunctionName() {#getFunctionName--}
```
public String getFunctionName()
```


Gets the function name to be calculated.

**Returns:**
java.lang.String
### getParamCount() {#getParamCount--}
```
public int getParamCount()
```


Gets the count of parameters

**Returns:**
int
### getParamText(int index) {#getParamText-int-}
```
public String getParamText(int index)
```


Gets the literal text of the parameter at given index.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| index | int | index of the parameter(0 based) |

**Returns:**
java.lang.String - literal text of the parameter
### getParamValue(int index) {#getParamValue-int-}
```
public Object getParamValue(int index)
```


Gets the represented value object of the parameter at given index.

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| index | int | index of the parameter(0 based) |

**Returns:**
java.lang.Object - If the parameter is plain value, then returns the plain value. If the parameter is reference, then returns ReferredArea object. If the parameter references to multiple datasets, then returns array of objects.
### getWorkbook() {#getWorkbook--}
```
public Workbook getWorkbook()
```


Gets the Workbook object where the function is in.

**Returns:**
[Workbook](../../com.aspose.cells/workbook)
### getWorksheet() {#getWorksheet--}
```
public Worksheet getWorksheet()
```


Gets the Worksheet object where the function is in.

**Returns:**
[Worksheet](../../com.aspose.cells/worksheet)
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




### setCalculatedValue(Object value) {#setCalculatedValue-java.lang.Object-}
```
public void setCalculatedValue(Object value)
```


Sets the calculated value for this function.

**Remarks**

User should set this property in his custom calculation engine for those functions the engine supports, and the set value will be returned when getting this property later. The set value may be of possible types of [Cell.getValue()](../../com.aspose.cells/cell\#getValue--), or array of such kind of values, or a Range, Name, ReferredArea. Getting this property before setting value to it will make the function be calculated by the default calculation engine of Aspose.Cells and then the calculated value will be returned(generally it should be \#NAME? for user-defined functions).

**Parameters:**
| Parameter | Type | Description |
| --- | --- | --- |
| value | java.lang.Object |  |

### toString() {#toString--}
```
public String toString()
```




**Returns:**
java.lang.String
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

