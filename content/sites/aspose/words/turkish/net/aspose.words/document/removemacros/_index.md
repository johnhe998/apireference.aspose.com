---
title: Document.RemoveMacros
second_title: Aspose.Words for .NET API Referansı
description: Document yöntem. Belgeden tüm makroları VBA projesi ve ayrıca araç çubuklarını ve komut özelleştirmelerini kaldırır.
type: docs
weight: 650
url: /tr/net/aspose.words/document/removemacros/
---
## Document.RemoveMacros method

Belgeden tüm makroları (VBA projesi) ve ayrıca araç çubuklarını ve komut özelleştirmelerini kaldırır.

```csharp
public void RemoveMacros()
```

### Notlar

Bir belgeden tüm makroları kaldırarak belgenin makro virüsü içermediğinden emin olabilirsiniz.

### Örnekler

Bir belgeden tüm makroların nasıl kaldırılacağını gösterir.

```csharp
Document doc = new Document(MyDir + "Macro.docm");

Assert.IsTrue(doc.HasMacros);
Assert.AreEqual("Project", doc.VbaProject.Name);

// Belgenin VBA projesini tüm makrolarıyla birlikte kaldırın.
doc.RemoveMacros();

Assert.IsFalse(doc.HasMacros);
Assert.Null(doc.VbaProject);
```

### Ayrıca bakınız

* class [Document](../)
* ad alanı [Aspose.Words](../../document/)
* toplantı [Aspose.Words](../../../)


