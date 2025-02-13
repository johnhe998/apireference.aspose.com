---
title: PageSetup.SuppressEndnotes
second_title: Referencia de API de Aspose.Words para .NET
description: PageSetup propiedad. Verdadero si las notas al final se imprimen al final de la siguiente sección que no suprime las notas al final. Las notas al final suprimidas se imprimen antes que las notas al final en esa sección.
type: docs
weight: 400
url: /es/net/aspose.words/pagesetup/suppressendnotes/
---
## PageSetup.SuppressEndnotes property

**Verdadero** si las notas al final se imprimen al final de la siguiente sección que no suprime las notas al final. Las notas al final suprimidas se imprimen antes que las notas al final en esa sección.

```csharp
public bool SuppressEndnotes { get; set; }
```

### Ejemplos

Muestra cómo almacenar notas finales al final de cada sección y modificar sus posiciones.

```csharp
{
    Document doc = new Document();
    doc.RemoveAllChildren();

      // De forma predeterminada, un documento compila todas las notas finales al final.
    Assert.AreEqual(EndnotePosition.EndOfDocument, doc.EndnoteOptions.Position);

    // Usamos la propiedad "Posición" del objeto "EndnoteOptions" del documento
     // para recopilar notas finales al final de cada sección en su lugar.
    doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

    InsertSectionWithEndnote(doc, "Section 1", "Endnote 1, will stay in section 1");
    InsertSectionWithEndnote(doc, "Section 2", "Endnote 2, will be pushed down to section 3");
    InsertSectionWithEndnote(doc, "Section 3", "Endnote 3, will stay in section 3");

    // Al hacer que las secciones muestren sus respectivas notas al final, podemos configurar el indicador "SuppressEndnotes"
    // del objeto "PageSetup" de una sección a "true" para volver al comportamiento predeterminado y pasar sus notas finales
    // a la siguiente sección.
    PageSetup pageSetup = doc.Sections[1].PageSetup;
    pageSetup.SuppressEndnotes = true;

    doc.Save(ArtifactsDir + "PageSetup.SuppressEndnotes.docx");

/// <summary>
/// Agrega una sección con texto y una nota al final de un documento.
/// </summary>
private static void InsertSectionWithEndnote(Document doc, string sectionBodyText, string endnoteText)
{
    Section section = new Section(doc);

    doc.AppendChild(section);

    Body body = new Body(doc);
    section.AppendChild(body);

    Assert.AreEqual(section, body.ParentNode);

    Paragraph para = new Paragraph(doc);
    body.AppendChild(para);

    Assert.AreEqual(body, para.ParentNode);

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.MoveTo(para);
    builder.Write(sectionBodyText);
    builder.InsertFootnote(FootnoteType.Endnote, endnoteText);
}
```

### Ver también

* class [PageSetup](../)
* espacio de nombres [Aspose.Words](../../pagesetup/)
* asamblea [Aspose.Words](../../../)


