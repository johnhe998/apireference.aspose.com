---
title: ShapeBase.IsTopLevel
second_title: Referencia de API de Aspose.Words para .NET
description: ShapeBase propiedad. Devuelve verdadero si esta forma no es hija de una forma de grupo.
type: docs
weight: 340
url: /es/net/aspose.words.drawing/shapebase/istoplevel/
---
## ShapeBase.IsTopLevel property

Devuelve verdadero si esta forma no es hija de una forma de grupo.

```csharp
public bool IsTopLevel { get; }
```

### Ejemplos

Muestra cómo saber si una forma es parte de una forma de grupo.

```csharp
Document doc = new Document();

Shape shape = new Shape(doc, ShapeType.Rectangle);
shape.Width = 200;
shape.Height = 200;
shape.WrapType = WrapType.None;

// Por defecto, una forma no forma parte de ninguna forma de grupo y, por lo tanto, tiene la propiedad "IsTopLevel" establecida en "true".
Assert.True(shape.IsTopLevel);

GroupShape group = new GroupShape(doc);
group.AppendChild(shape);

// Una vez que asimilamos una forma a una forma de grupo, la propiedad "IsTopLevel" cambia a "falso".
Assert.False(shape.IsTopLevel);
```

### Ver también

* class [ShapeBase](../)
* espacio de nombres [Aspose.Words.Drawing](../../shapebase/)
* asamblea [Aspose.Words](../../../)


