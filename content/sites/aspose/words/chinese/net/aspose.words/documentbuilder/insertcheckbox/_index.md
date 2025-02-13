---
title: DocumentBuilder.InsertCheckBox
second_title: Aspose.Words for .NET API 参考
description: DocumentBuilder 方法. 在当前位置插入一个复选框表单域
type: docs
weight: 270
url: /zh/net/aspose.words/documentbuilder/insertcheckbox/
---
## InsertCheckBox(string, bool, int) {#insertcheckbox_1}

在当前位置插入一个复选框表单域。

```csharp
public FormField InsertCheckBox(string name, bool checkedValue, int size)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| name | String | 表单域的名称。可以是空字符串。超过 20 个字符的值将被截断。 |
| checkedValue | Boolean | 检查复选框表单字段的状态。 |
| size | Int32 | 以磅为单位指定复选框的大小。为 MS Word 指定 0 以自动计算复选框的大小。 |

### 返回值

刚刚插入的表单域节点。

### 评论

如果您为表单域指定名称，则会自动创建具有相同名称的书签。

### 例子

显示如何在文档中插入复选框。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入不同大小和默认选中状态的复选框。
builder.Write("Unchecked check box of a default size: ");
builder.InsertCheckBox(string.Empty, false, false, 0);
builder.InsertParagraph();

builder.Write("Large checked check box: ");
builder.InsertCheckBox("CheckBox_Default", true, true, 50);
builder.InsertParagraph();

// 表单字段的名称长度限制为 20 个字符。
builder.Write("Very large checked check box: ");
builder.InsertCheckBox("CheckBox_OnlyCheckedValue", true, 100);

Assert.AreEqual("CheckBox_OnlyChecked", doc.Range.FormFields[2].Name);

// 我们可以通过双击它们在 Microsoft Word 中与这些复选框进行交互。
doc.Save(ArtifactsDir + "DocumentBuilder.InsertCheckBox.docx");
```

### 也可以看看

* class [FormField](../../../aspose.words.fields/formfield/)
* class [DocumentBuilder](../)
* 命名空间 [Aspose.Words](../../documentbuilder/)
* 部件 [Aspose.Words](../../../)

---

## InsertCheckBox(string, bool, bool, int) {#insertcheckbox}

在当前位置插入一个复选框表单域。

```csharp
public FormField InsertCheckBox(string name, bool defaultValue, bool checkedValue, int size)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| name | String | 表单域的名称。可以是空字符串。超过 20 个字符的值将被截断。 |
| defaultValue | Boolean | 复选框表单字段的默认值。 |
| checkedValue | Boolean | 复选框表单字段的当前选中状态。 |
| size | Int32 | 以磅为单位指定复选框的大小。为 MS Word 指定 0 以自动计算复选框的大小。 |

### 返回值

刚刚插入的表单域节点。

### 评论

如果您为表单域指定名称，则会自动创建具有相同名称的书签。

### 例子

显示如何在文档中插入复选框。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入不同大小和默认选中状态的复选框。
builder.Write("Unchecked check box of a default size: ");
builder.InsertCheckBox(string.Empty, false, false, 0);
builder.InsertParagraph();

builder.Write("Large checked check box: ");
builder.InsertCheckBox("CheckBox_Default", true, true, 50);
builder.InsertParagraph();

// 表单字段的名称长度限制为 20 个字符。
builder.Write("Very large checked check box: ");
builder.InsertCheckBox("CheckBox_OnlyCheckedValue", true, 100);

Assert.AreEqual("CheckBox_OnlyChecked", doc.Range.FormFields[2].Name);

// 我们可以通过双击它们在 Microsoft Word 中与这些复选框进行交互。
doc.Save(ArtifactsDir + "DocumentBuilder.InsertCheckBox.docx");
```

### 也可以看看

* class [FormField](../../../aspose.words.fields/formfield/)
* class [DocumentBuilder](../)
* 命名空间 [Aspose.Words](../../documentbuilder/)
* 部件 [Aspose.Words](../../../)


