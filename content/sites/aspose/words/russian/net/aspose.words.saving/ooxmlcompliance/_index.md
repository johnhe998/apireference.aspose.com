---
title: Enum OoxmlCompliance
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Saving.OoxmlCompliance перечисление. Позволяет указать какая спецификация OOXML будет использоваться при сохранении в формате DOCX.
type: docs
weight: 5060
url: /ru/net/aspose.words.saving/ooxmlcompliance/
---
## OoxmlCompliance enumeration

Позволяет указать, какая спецификация OOXML будет использоваться при сохранении в формате DOCX.

```csharp
public enum OoxmlCompliance
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Ecma376_2006 | `0` | ECMA-376 1-е издание, 2006 г. |
| Iso29500_2008_Transitional | `1` | ISO/IEC 29500:2008 Переходный уровень соответствия. |
| Iso29500_2008_Strict | `2` | Уровень строгого соответствия ISO/IEC 29500:2008. |

### Примеры

Показывает, как вставлять фигуры DML в документ.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Ниже приведены два типа обтекания, которые могут иметь фигуры.
// 1 - Плавающая:
builder.InsertShape(ShapeType.TopCornersRounded, RelativeHorizontalPosition.Page, 100, 
        RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// 2 - Встроенный:
builder.InsertShape(ShapeType.DiagonalCornersRounded, 50, 50);

// Если вам нужно создать "не примитивные" формы, такие как SingleCornerSnipped, TopCornersSnipped, DiagonalCornersSnipped,
// TopCornersOneRoundedOneSnipped, SingleCornerRounded, TopCornersRounded или DiagonalCornersRounded,
// затем сохраните документ с соблюдением "Строгого" или "Переходного", что позволяет сохранять форму как DML.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx);
saveOptions.Compliance = OoxmlCompliance.Iso29500_2008_Transitional;

doc.Save(ArtifactsDir + "Shape.ShapeInsertion.docx", saveOptions);
```

Показывает, как настроить список для перезапуска нумерации в каждом разделе.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Lists.Add(ListTemplate.NumberDefault);

Aspose.Words.Lists.List list = doc.Lists[0];
list.IsRestartAtEachSection = restartListAtEachSection;

// Свойство "IsRestartAtEachSection" будет применяться только тогда, когда
// уровень соответствия документа OOXML соответствует более новому стандарту, чем "OoxmlComplianceCore.Ecma376".
OoxmlSaveOptions options = new OoxmlSaveOptions
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};

builder.ListFormat.List = list;

builder.Writeln("List item 1");
builder.Writeln("List item 2");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Writeln("List item 3");
builder.Writeln("List item 4");

doc.Save(ArtifactsDir + "OoxmlSaveOptions.RestartingDocumentList.docx", options);

doc = new Document(ArtifactsDir + "OoxmlSaveOptions.RestartingDocumentList.docx");

Assert.AreEqual(restartListAtEachSection, doc.Lists[0].IsRestartAtEachSection);
```

Показывает, как установить спецификацию соответствия OOXML для сохраненного документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Если мы настроим параметры совместимости для соответствия Microsoft Word 2003,
// вставка изображения определит его форму с помощью VML.
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2003);
builder.InsertImage(ImageDir + "Transparent background logo.png");

Assert.AreEqual(ShapeMarkupLanguage.Vml, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).MarkupLanguage);

// Стандарт OOXML "ISO/IEC 29500:2008" не поддерживает формы VML.
// Если мы установим для свойства "Соответствие" объекта SaveOptions значение "OoxmlCompliance.Iso29500_2008_Strict",
 // любой документ, который мы сохраняем при передаче этого объекта, должен соответствовать этому стандарту.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions
{
    Compliance = OoxmlCompliance.Iso29500_2008_Strict,
    SaveFormat = SaveFormat.Docx
};

doc.Save(ArtifactsDir + "OoxmlSaveOptions.Iso29500Strict.docx", saveOptions);

// Наш сохраненный документ определяет форму с помощью DML, чтобы соответствовать стандарту OOXML "ISO/IEC 29500:2008".
doc = new Document(ArtifactsDir + "OoxmlSaveOptions.Iso29500Strict.docx");

Assert.AreEqual(ShapeMarkupLanguage.Dml, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).MarkupLanguage);
```

### Смотрите также

* пространство имен [Aspose.Words.Saving](../../aspose.words.saving/)
* сборка [Aspose.Words](../../)


