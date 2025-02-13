---
title: Layer.DisplayName
second_title: Aspose.PSD for .NET API Reference
description: Layer property. Gets or sets the display name of the layer
type: docs
weight: 100
url: /net/aspose.psd.fileformats.psd.layers/layer/displayname/
---
{{< psd/tize >}}
## Layer.DisplayName property

Gets or sets the display name of the layer.

```csharp
public string DisplayName { get; set; }
```

### Property Value

The display name of the layer.

## Examples

The following example demonstrates ability to set the DisplayName value, in what the layer name display correct.

```csharp
[C#]

// make changes in layer names and save it
string sourceFileName = "layers with names.psd";
string output = "output.psd";

using (var image = (PsdImage)Image.Load(sourceFileName))
{
    for (int i = 0; i < image.Layers.Length; i++)
    {
        var layer = image.Layers[i];
        // set new value into DisplayName property
        layer.DisplayName += "_changed";
    }

    image.Save(output);
}
```

### See Also

* class [Layer](../)
* namespace [Aspose.PSD.FileFormats.Psd.Layers](../../../aspose.psd.fileformats.psd.layers/)
* assembly [Aspose.PSD](../../../)


