---
title: StructuredDocumentTag.IsTemporary
second_title: Aspose.Words for .NET API Referansı
description: StructuredDocumentTag mülk. Bunun olup olmadığını belirtir SDT content değiştirildiğinde WordProcessingML belgesinden kaldırılacaktır.
type: docs
weight: 160
url: /tr/net/aspose.words.markup/structureddocumenttag/istemporary/
---
## StructuredDocumentTag.IsTemporary property

Bunun olup olmadığını belirtir **SDT** content değiştirildiğinde WordProcessingML belgesinden kaldırılacaktır.

```csharp
public bool IsTemporary { get; set; }
```

### Örnekler

Tek kullanımlık kontrollerin nasıl yapıldığını gösterir.

```csharp
Document doc = new Document();

// Düz metin yapılandırılmış bir belge etiketi ekleyin,
// kullanıcının metin girebileceği bir düz metin biçimi olarak işlev görecektir.
StructuredDocumentTag tag = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Inline);

// Yapılandırılmış belge etiketinin kaybolmasını sağlamak için "IsTemporary" özelliğini "true" olarak ayarlayın ve
// kullanıcı Microsoft Word'de bir kez düzenledikten sonra içeriğini belgeye asimile edin.
// Kullanıcının içeriği düzenlemesine izin vermek için "IsTemporary" özelliğini "false" olarak ayarlayın
// yapılandırılmış belge etiketinin herhangi bir sayıda.
tag.IsTemporary = isTemporary;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Please enter text: ");
builder.InsertNode(tag);

// Onay kutusu biçiminde başka bir yapılandırılmış belge etiketi ekleyin ve varsayılan durumunu "işaretli" olarak ayarlayın.
tag = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
tag.Checked = true;

// Onay kutusunun bir sembol haline gelmesi için "IsTemporary" özelliğini "true" olarak ayarlayın
// kullanıcı Microsoft Word'de tıkladığında.
// Kullanıcının onay kutusunu herhangi bir sayıda tıklamasına izin vermek için "IsTemporary" özelliğini "false" olarak ayarlayın.
tag.IsTemporary = isTemporary;

builder.Write("\nPlease click the check box: ");
builder.InsertNode(tag);

doc.Save(ArtifactsDir + "StructuredDocumentTag.IsTemporary.docx");
```

### Ayrıca bakınız

* class [StructuredDocumentTag](../)
* ad alanı [Aspose.Words.Markup](../../structureddocumenttag/)
* toplantı [Aspose.Words](../../../)


