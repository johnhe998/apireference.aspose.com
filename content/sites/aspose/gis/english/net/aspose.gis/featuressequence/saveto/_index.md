---
title: FeaturesSequence.SaveTo
second_title: Aspose.GIS for .NET API Reference
description: FeaturesSequence method. Saves features sequence to layer.
type: docs
weight: 50
url: /net/aspose.gis/featuressequence/saveto/
---
## SaveTo(string, FileDriver) {#saveto_2}

Saves features sequence to layer.

```csharp
public void SaveTo(string destinationPath, FileDriver destinationDriver)
```

| Parameter | Type | Description |
| --- | --- | --- |
| destinationPath | String | Path to the output layer. |
| destinationDriver | FileDriver | The format driver for the output layer. |

### Exceptions

| exception | condition |
| --- | --- |
| ArgumentNullException | Any argument is `null`. |
| [GisException](../../gisexception/) | Error reading or writing the feature to/from the file. |
| IOException | An I/O error occurred. |
| [TransformationException](../../../aspose.gis.spatialreferencing/transformationexception/) | Transformation of features geometry from source spatial reference system to target spatial reference system failed. |

### See Also

* class [FileDriver](../../filedriver/)
* class [FeaturesSequence](../)
* namespace [Aspose.Gis](../../featuressequence/)
* assembly [Aspose.GIS](../../../)

---

## SaveTo(AbstractPath, FileDriver) {#saveto}

Saves features sequence to layer.

```csharp
public void SaveTo(AbstractPath destinationPath, FileDriver destinationDriver)
```

| Parameter | Type | Description |
| --- | --- | --- |
| destinationPath | AbstractPath | Path to the output layer. |
| destinationDriver | FileDriver | The format driver for the output layer. |

### Exceptions

| exception | condition |
| --- | --- |
| [GisException](../../gisexception/) | Error reading or writing the feature to/from the file. |
| IOException | An I/O error occurred. |
| [TransformationException](../../../aspose.gis.spatialreferencing/transformationexception/) | Transformation of features geometry from source spatial reference system to target spatial reference system failed. |

### See Also

* class [AbstractPath](../../abstractpath/)
* class [FileDriver](../../filedriver/)
* class [FeaturesSequence](../)
* namespace [Aspose.Gis](../../featuressequence/)
* assembly [Aspose.GIS](../../../)

---

## SaveTo(string, FileDriver, SavingOptions) {#saveto_3}

Saves features sequence to layer.

```csharp
public void SaveTo(string destinationPath, FileDriver destinationDriver, SavingOptions options)
```

| Parameter | Type | Description |
| --- | --- | --- |
| destinationPath | String | Path to the output layer. |
| destinationDriver | FileDriver | The format driver for the output layer. |
| options | SavingOptions | Options for the saving procedure. |

### Exceptions

| exception | condition |
| --- | --- |
| [GisException](../../gisexception/) | Error reading or writing the feature to/from the file. |
| IOException | An I/O error occurred. |
| [TransformationException](../../../aspose.gis.spatialreferencing/transformationexception/) | Transformation of features geometry from source spatial reference system to target spatial reference system failed. |
| NotSupportedException | Spatial reference system specified in *options* is not supported by *destinationDriver*. |

### See Also

* class [FileDriver](../../filedriver/)
* class [SavingOptions](../../savingoptions/)
* class [FeaturesSequence](../)
* namespace [Aspose.Gis](../../featuressequence/)
* assembly [Aspose.GIS](../../../)

---

## SaveTo(AbstractPath, FileDriver, SavingOptions) {#saveto_1}

Saves features sequence to layer.

```csharp
public void SaveTo(AbstractPath destinationPath, FileDriver destinationDriver, 
    SavingOptions options)
```

| Parameter | Type | Description |
| --- | --- | --- |
| destinationPath | AbstractPath | Path to the output layer. |
| destinationDriver | FileDriver | The format driver for the output layer. |
| options | SavingOptions | Options for the saving procedure. |

### Exceptions

| exception | condition |
| --- | --- |
| [GisException](../../gisexception/) | Error reading or writing the feature to/from the file. |
| IOException | An I/O error occurred. |
| [TransformationException](../../../aspose.gis.spatialreferencing/transformationexception/) | Transformation of features geometry from source spatial reference system to target spatial reference system failed. |
| NotSupportedException | Spatial reference system specified in *options* is not supported by *destinationDriver*. |

### See Also

* class [AbstractPath](../../abstractpath/)
* class [FileDriver](../../filedriver/)
* class [SavingOptions](../../savingoptions/)
* class [FeaturesSequence](../)
* namespace [Aspose.Gis](../../featuressequence/)
* assembly [Aspose.GIS](../../../)


