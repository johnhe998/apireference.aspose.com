---
title: Document.HasMacros
second_title: Справочник по API Aspose.Words для .NET
description: Document свойство. Возвращает истинный если документ имеет проект VBA макросы.
type: docs
weight: 190
url: /ru/net/aspose.words/document/hasmacros/
---
## Document.HasMacros property

Возвращает **истинный** если документ имеет проект VBA (макросы).

```csharp
public bool HasMacros { get; }
```

### Примеры

Показывает, как использовать поля MACROBUTTON, чтобы позволить нам запускать макросы документа, щелкая.

```csharp
Document doc = new Document(MyDir + "Macro.docm");
DocumentBuilder builder = new DocumentBuilder(doc);

Assert.IsTrue(doc.HasMacros);

// Вставьте поле MACROBUTTON и укажите один из макросов документа по имени в свойстве MacroName.
FieldMacroButton field = (FieldMacroButton)builder.InsertField(FieldType.FieldMacroButton, true);
field.MacroName = "MyMacro";
field.DisplayText = "Double click to run macro: " + field.MacroName;

Assert.AreEqual(" MACROBUTTON  MyMacro Double click to run macro: MyMacro", field.GetFieldCode());

// Используйте это свойство для ссылки на "ViewZoom200", макрос, который поставляется с Microsoft Word.
// Все остальные макросы мы можем найти через Вид -> Макросы (раскрывающийся список) -> Просмотр макросов.
// В этом меню выберите «Команды Word» в раскрывающемся списке «Макросы в:».
// Если наш документ содержит пользовательский макрос с тем же именем, что и стандартный макрос,
// наш макрос будет тот, который запускает поле MACROBUTTON.
builder.InsertParagraph();
field = (FieldMacroButton)builder.InsertField(FieldType.FieldMacroButton, true);
field.MacroName = "ViewZoom200";
field.DisplayText = "Run " + field.MacroName;

Assert.AreEqual(" MACROBUTTON  ViewZoom200 Run ViewZoom200", field.GetFieldCode());

// Сохраняем документ как тип документа с поддержкой макросов.
doc.Save(ArtifactsDir + "Field.MACROBUTTON.docm");
```

### Смотрите также

* method [RemoveMacros](../removemacros/)
* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


