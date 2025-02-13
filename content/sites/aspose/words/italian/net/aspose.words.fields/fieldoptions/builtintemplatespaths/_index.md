---
title: FieldOptions.BuiltInTemplatesPaths
second_title: Aspose.Words per .NET API Reference
description: FieldOptions proprietà. Ottiene o imposta i percorsi dei modelli integrati di MS Word.
type: docs
weight: 20
url: /it/net/aspose.words.fields/fieldoptions/builtintemplatespaths/
---
## FieldOptions.BuiltInTemplatesPaths property

Ottiene o imposta i percorsi dei modelli integrati di MS Word.

```csharp
public string[] BuiltInTemplatesPaths { get; set; }
```

### Osservazioni

Questa proprietà è utilizzata dal[`FieldAutoText`](../../fieldautotext/) e[`FieldGlossary`](../../fieldglossary/) campi, se l'immissione di testo automatico di riferimento non si trova nei[`AttachedTemplate`](../../../aspose.words/document/attachedtemplate/) modello.

Per impostazione predefinita, MS Word archivia i modelli integrati in c:\Utenti\&lt;nome utente&gt;\AppData\Roaming\Microsoft\Document Building Blocks\1033\16\Built-In Building Blocks.dotx e C:\Utenti\&lt;nome utente&gt;\ File AppData\Roaming\Microsoft\Modelli\Normal.dotm.

### Esempi

Mostra come visualizzare un building block con i campi AUTOTEXT e GLOSSARY.

```csharp
Document doc = new Document();

// Crea un documento di glossario e aggiungi un blocco predefinito di glossario.
doc.GlossaryDocument = new GlossaryDocument();
BuildingBlock buildingBlock = new BuildingBlock(doc.GlossaryDocument);
buildingBlock.Name = "MyBlock";
buildingBlock.Gallery = BuildingBlockGallery.AutoText;
buildingBlock.Category = "General";
buildingBlock.Description = "MyBlock description";
buildingBlock.Behavior = BuildingBlockBehavior.Paragraph;
doc.GlossaryDocument.AppendChild(buildingBlock);

// Crea una fonte e aggiungila come testo al nostro blocco di costruzione.
Document buildingBlockSource = new Document();
DocumentBuilder buildingBlockSourceBuilder = new DocumentBuilder(buildingBlockSource);
buildingBlockSourceBuilder.Writeln("Hello World!");

Node buildingBlockContent = doc.GlossaryDocument.ImportNode(buildingBlockSource.FirstSection, true);
buildingBlock.AppendChild(buildingBlockContent);

// Imposta un file che contenga parti che il nostro documento o il modello allegato potrebbero non contenere.
doc.FieldOptions.BuiltInTemplatesPaths = new[] { MyDir + "Busniess brochure.dotx" };

DocumentBuilder builder = new DocumentBuilder(doc);

// Di seguito sono riportati due modi per utilizzare i campi per visualizzare il contenuto del nostro blocco predefinito.
// 1 - Utilizzo di un campo AUTOTEXT:
FieldAutoText fieldAutoText = (FieldAutoText)builder.InsertField(FieldType.FieldAutoText, true);
fieldAutoText.EntryName = "MyBlock";

Assert.AreEqual(" AUTOTEXT  MyBlock", fieldAutoText.GetFieldCode());

// 2 - Utilizzo di un campo GLOSSARIO:
FieldGlossary fieldGlossary = (FieldGlossary)builder.InsertField(FieldType.FieldGlossary, true);
fieldGlossary.EntryName = "MyBlock";

Assert.AreEqual(" GLOSSARY  MyBlock", fieldGlossary.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.AUTOTEXT.GLOSSARY.dotx");
```

### Guarda anche

* class [FieldOptions](../)
* spazio dei nomi [Aspose.Words.Fields](../../fieldoptions/)
* assemblea [Aspose.Words](../../../)


