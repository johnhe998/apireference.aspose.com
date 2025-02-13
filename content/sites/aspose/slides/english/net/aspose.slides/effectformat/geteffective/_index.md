---
title: GetEffective
second_title: Aspose.Sildes for .NET API Reference
description: Gets effective effect formatting data with the inheritance applied.
type: docs
weight: 250
url: /net/aspose.slides/effectformat/geteffective/
---
## EffectFormat.GetEffective method

Gets effective effect formatting data with the inheritance applied.

```csharp
public IEffectFormatEffectiveData GetEffective()
```

### Return Value

A [`IEffectFormatEffectiveData`](../../ieffectformateffectivedata).

### Examples

This example demonstrates getting some of shape's effective effect properties.

```csharp
[C#]
using (Presentation pres = new Presentation(@"MyPresentation.pptx"))
{
	IEffectFormatEffectiveData effectiveEffectFormat = pres.Slides[0].Shapes[0].EffectFormat.GetEffective();

	if (effectiveEffectFormat.IsNoEffects)
	{
		Console.WriteLine("The shape has not effects applied.");
	}
	else
	{
		if (effectiveEffectFormat.BlurEffect != null)
			Console.WriteLine("Blur effect radius: " + effectiveEffectFormat.BlurEffect.Radius);
		if (effectiveEffectFormat.FillOverlayEffect != null)
			Console.WriteLine("Fill overlay effect fill type: " + effectiveEffectFormat.FillOverlayEffect.FillFormat.FillType);
		if (effectiveEffectFormat.GlowEffect != null)
			Console.WriteLine("Glow effect color: " + effectiveEffectFormat.GlowEffect.Color);
		if (effectiveEffectFormat.InnerShadowEffect != null)
			Console.WriteLine("Inner shadow effect shadow color: " + effectiveEffectFormat.InnerShadowEffect.ShadowColor);
		if (effectiveEffectFormat.OuterShadowEffect != null)
			Console.WriteLine("Outer shadow effect shadow color: " + effectiveEffectFormat.OuterShadowEffect.ShadowColor);
		if (effectiveEffectFormat.PresetShadowEffect != null)
			Console.WriteLine("Preset shadow effect shadow color: " + effectiveEffectFormat.PresetShadowEffect.ShadowColor);
		if (effectiveEffectFormat.ReflectionEffect != null)
			Console.WriteLine("Reflection effect distance: " + effectiveEffectFormat.ReflectionEffect.Distance);
		if (effectiveEffectFormat.SoftEdgeEffect != null)
			Console.WriteLine("Soft edge effect radius: " + effectiveEffectFormat.SoftEdgeEffect.Radius);
	}
}
```

### See Also

* interface [IEffectFormatEffectiveData](../../ieffectformateffectivedata)
* class [EffectFormat](../../effectformat)
* namespace [Aspose.Slides](../../effectformat)
* assembly [Aspose.Slides](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
