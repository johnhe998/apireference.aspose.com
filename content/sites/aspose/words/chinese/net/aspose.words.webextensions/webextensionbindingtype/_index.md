---
title: Enum WebExtensionBindingType
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.WebExtensions.WebExtensionBindingType 枚举. 枚举 Web 扩展和文档中数据之间可用的绑定类型
type: docs
weight: 6460
url: /zh/net/aspose.words.webextensions/webextensionbindingtype/
---
## WebExtensionBindingType enumeration

枚举 Web 扩展和文档中数据之间可用的绑定类型。

```csharp
public enum WebExtensionBindingType
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| Matrix | `0` | 没有标题行的表格数据。 |
| Table | `1` | 带有标题行的表格数据。 |
| Text | `2` | 纯文本。 |
| Default | `0` |  |

### 例子

展示如何向文档添加 Web 扩展。

```csharp
Document doc = new Document();

// 使用“MyScript”插件创建任务窗格，文档将使用该插件，
// 然后设置它的默认位置。
TaskPane myScriptTaskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(myScriptTaskPane);
myScriptTaskPane.DockState = TaskPaneDockState.Right;
myScriptTaskPane.IsVisible = true;
myScriptTaskPane.Width = 300;
myScriptTaskPane.IsLocked = true;

// 如果同一个停靠位置有多个任务窗格，我们可以设置这个索引来排列它们。
myScriptTaskPane.Row = 1;

// 创建一个名为“MyScript Math Sample”的加载项，任务窗格将在其中显示。
WebExtension webExtension = myScriptTaskPane.WebExtension;

// 为我们的加载项设置应用商店引用参数，例如 ID。
webExtension.Reference.Id = "WA104380646";
webExtension.Reference.Version = "1.0.0.0";
webExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
webExtension.Reference.Store = CultureInfo.CurrentCulture.Name;
webExtension.Properties.Add(new WebExtensionProperty("MyScript", "MyScript Math Sample"));
webExtension.Bindings.Add(new WebExtensionBinding("MyScript", WebExtensionBindingType.Text, "104380646"));

// 允许用户与加载项交互。
webExtension.IsFrozen = false;

// 我们可以通过 Developer 访问 Microsoft Word 中的 Web 扩展 ->加载项。
doc.Save(ArtifactsDir + "Document.WebExtension.docx");

// 像这样一次删除所有 Web 扩展任务窗格。
doc.WebExtensionTaskPanes.Clear();

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### 也可以看看

* 命名空间 [Aspose.Words.WebExtensions](../../aspose.words.webextensions/)
* 部件 [Aspose.Words](../../)


