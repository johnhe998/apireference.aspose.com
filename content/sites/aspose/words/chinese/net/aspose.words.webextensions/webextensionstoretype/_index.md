---
title: Enum WebExtensionStoreType
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.WebExtensions.WebExtensionStoreType 枚举. 枚举网络扩展商店的可用类型
type: docs
weight: 6510
url: /zh/net/aspose.words.webextensions/webextensionstoretype/
---
## WebExtensionStoreType enumeration

枚举网络扩展商店的可用类型。

```csharp
public enum WebExtensionStoreType
```

### 价值观

| 姓名 | 价值 | 描述 |
| --- | --- | --- |
| SPCatalog | `0` | 指定商店类型是 SharePoint 公司目录。 |
| OMEX | `1` | 指定商店类型为 Office.com。 |
| SPApp | `2` | 指定商店类型是 SharePoint Web 应用程序。 |
| Exchange | `3` | 指定存储类型是 Exchange 服务器。 |
| FileSystem | `4` | 指定存储类型是文件系统共享。 |
| Registry | `5` | 指定存储类型是系统注册表。 |
| ExCatalog | `6` | 指定存储类型是通过 Exchange 集中部署。 |
| Default | `0` | 默认值。 |

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


