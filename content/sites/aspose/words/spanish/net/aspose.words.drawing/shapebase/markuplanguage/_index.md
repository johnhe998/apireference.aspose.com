---
title: ShapeBase.MarkupLanguage
second_title: Referencia de API de Aspose.Words para .NET
description: ShapeBase propiedad. Obtiene MarkupLanguage utilizado para este objeto gráfico.
type: docs
weight: 370
url: /es/net/aspose.words.drawing/shapebase/markuplanguage/
---
## ShapeBase.MarkupLanguage property

Obtiene MarkupLanguage utilizado para este objeto gráfico.

```csharp
public ShapeMarkupLanguage MarkupLanguage { get; }
```

### Ejemplos

Muestra cómo verificar el tamaño de una forma y el lenguaje de marcas.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.InsertImage(ImageDir + "Transparent background logo.png");

Assert.AreEqual(ShapeMarkupLanguage.Dml, shape.MarkupLanguage);
Assert.AreEqual(new SizeF(300, 300), shape.SizeInPoints);
```

### Ver también

* enum [ShapeMarkupLanguage](../../shapemarkuplanguage/)
* class [ShapeBase](../)
* espacio de nombres [Aspose.Words.Drawing](../../shapebase/)
* asamblea [Aspose.Words](../../../)


