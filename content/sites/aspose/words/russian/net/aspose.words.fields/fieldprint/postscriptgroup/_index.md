---
title: FieldPrint.PostScriptGroup
second_title: Справочник по API Aspose.Words для .NET
description: FieldPrint свойство. Получает или задает прямоугольник рисования с которым работают инструкции PostScript.
type: docs
weight: 20
url: /ru/net/aspose.words.fields/fieldprint/postscriptgroup/
---
## FieldPrint.PostScriptGroup property

Получает или задает прямоугольник рисования, с которым работают инструкции PostScript.

```csharp
public string PostScriptGroup { get; set; }
```

### Примеры

Показывает, чтобы вставить поле PRINT.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("My paragraph");

// Поле PRINT может отправлять инструкции на принтер.
FieldPrint field = (FieldPrint)builder.InsertField(FieldType.FieldPrint, true);

// Установите область, в которой принтер будет выполнять инструкции.
// В данном случае это будет абзац, содержащий наше поле PRINT.
field.PostScriptGroup = "para";

// Когда мы используем принтер, поддерживающий PostScript, для печати нашего документа,
// эта команда сделает всю область, которую мы указали в "field.PostScriptGroup", белой.
field.PrinterInstructions = "erasepage";

Assert.AreEqual(" PRINT  erasepage \\p para", field.GetFieldCode());

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.PRINT.docx");
```

### Смотрите также

* class [FieldPrint](../)
* пространство имен [Aspose.Words.Fields](../../fieldprint/)
* сборка [Aspose.Words](../../../)


