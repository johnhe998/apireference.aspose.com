---
title: OdtSaveOptions.IsStrictSchema11
second_title: Справочник по API Aspose.Words для .NET
description: OdtSaveOptions свойство. Указывает должен ли экспорт строго соответствовать спецификации ODT 1.1. OOo 3.0 правильно отображает файлы если они содержат элементы и атрибуты ODT 1.2. Используйте false для этой цели или true для строгого соответствия спецификации 1.1. Значение по умолчанию ЛОЖЬ .
type: docs
weight: 20
url: /ru/net/aspose.words.saving/odtsaveoptions/isstrictschema11/
---
## OdtSaveOptions.IsStrictSchema11 property

Указывает, должен ли экспорт строго соответствовать спецификации ODT 1.1. OOo 3.0 правильно отображает файлы, если они содержат элементы и атрибуты ODT 1.2. Используйте "false" для этой цели или "true" для строгого соответствия спецификации 1.1. Значение по умолчанию: **ЛОЖЬ** .

```csharp
public bool IsStrictSchema11 { get; set; }
```

### Примеры

Показывает, как привести сохраненный документ в соответствие со старой схемой ODT.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

OdtSaveOptions saveOptions = new OdtSaveOptions
{
    MeasureUnit = OdtSaveMeasureUnit.Centimeters,
    IsStrictSchema11 = exportToOdt11Specs
};

doc.Save(ArtifactsDir + "OdtSaveOptions.Odt11Schema.odt", saveOptions);
```

### Смотрите также

* class [OdtSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../odtsaveoptions/)
* сборка [Aspose.Words](../../../)


