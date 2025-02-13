---
title: Document.HasMacros
second_title: Aspose.Words for .NET API 参考
description: Document 财产. 返回 真的如果文档有 VBA 项目宏
type: docs
weight: 190
url: /zh/net/aspose.words/document/hasmacros/
---
## Document.HasMacros property

返回 **真的**如果文档有 VBA 项目（宏）。

```csharp
public bool HasMacros { get; }
```

### 例子

展示如何使用 MACROBUTTON 字段来允许我们通过单击来运行文档的宏。

```csharp
Document doc = new Document(MyDir + "Macro.docm");
DocumentBuilder builder = new DocumentBuilder(doc);

Assert.IsTrue(doc.HasMacros);

// 插入一个 MACROBUTTON 字段，并在 MacroName 属性中按名称引用文档的宏之一。
FieldMacroButton field = (FieldMacroButton)builder.InsertField(FieldType.FieldMacroButton, true);
field.MacroName = "MyMacro";
field.DisplayText = "Double click to run macro: " + field.MacroName;

Assert.AreEqual(" MACROBUTTON  MyMacro Double click to run macro: MyMacro", field.GetFieldCode());

// 使用该属性来引用 Microsoft Word 附带的宏“ViewZoom200”。
// 我们可以通过 View -> 找到所有其他宏宏（下拉）->查看宏。
// 在该菜单中，从“Macros in:”下拉菜单中选择“Word Commands”。
// 如果我们的文档包含与股票宏同名的自定义宏，
// 我们的宏将是 MACROBUTTON 字段运行的那个。
builder.InsertParagraph();
field = (FieldMacroButton)builder.InsertField(FieldType.FieldMacroButton, true);
field.MacroName = "ViewZoom200";
field.DisplayText = "Run " + field.MacroName;

Assert.AreEqual(" MACROBUTTON  ViewZoom200 Run ViewZoom200", field.GetFieldCode());

// 将文档保存为启用宏的文档类型。
doc.Save(ArtifactsDir + "Field.MACROBUTTON.docm");
```

### 也可以看看

* method [RemoveMacros](../removemacros/)
* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


