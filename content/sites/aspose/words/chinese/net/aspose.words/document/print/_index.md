---
title: Document.Print
second_title: Aspose.Words for .NET API 参考
description: Document 方法. 将整个文档打印到默认打印机
type: docs
weight: 620
url: /zh/net/aspose.words/document/print/
---
## Print() {#print}

将整个文档打印到默认打印机。

```csharp
public void Print()
```

### 例子

显示如何使用默认打印机打印文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// 下面是打印文档的两种方式。
// 1 - 使用默认打印机打印：
doc.Print();

// 2 - 按名称指定我们希望打印文档的打印机：
string myPrinter = PrinterSettings.InstalledPrinters[4];

Assert.AreEqual("HPDAAB96 (HP ENVY 5000 series)", myPrinter);

doc.Print(myPrinter);
```

### 也可以看看

* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)

---

## Print(string) {#print_3}

将整个文档打印到指定的打印机， 使用标准（无用户界面）打印控制器。

```csharp
public void Print(string printerName)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| printerName | String | 打印机的名称。 |

### 例子

显示如何使用默认打印机打印文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// 下面是打印文档的两种方式。
// 1 - 使用默认打印机打印：
doc.Print();

// 2 - 按名称指定我们希望打印文档的打印机：
string myPrinter = PrinterSettings.InstalledPrinters[4];

Assert.AreEqual("HPDAAB96 (HP ENVY 5000 series)", myPrinter);

doc.Print(myPrinter);
```

### 也可以看看

* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)

---

## Print(PrinterSettings) {#print_1}

根据指定的打印机设置打印文档， 使用标准（无用户界面）打印控制器。

```csharp
public void Print(PrinterSettings printerSettings)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| printerSettings | PrinterSettings | 要使用的打印机设置。 |

### 评论

这PrinterSettings 对象允许您指定要打印的打印机、要打印的页面范围和其他选项。

### 例子

显示如何打印一系列页面。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// 创建一个“PrinterSettings”对象来修改我们打印文档的方式。
PrinterSettings printerSettings = new PrinterSettings();

// 将“PrintRange”属性设置为“PrintRange.SomePages”以
// 告诉打印机我们打算只打印一些文档页面。
printerSettings.PrintRange = System.Drawing.Printing.PrintRange.SomePages;

// 将“FromPage”属性设置为“1”，将“ToPage”属性设置为“3”以打印第 1 页到第 3 页。
// 页面索引是从 1 开始的。
printerSettings.FromPage = 1;
printerSettings.ToPage = 3;

// 下面是打印文档的两种方式。
// 1 - 在应用我们的打印设置时打印：
doc.Print(printerSettings);

// 2 - 在应用我们的打印设置时打印，同时也打印
// 给文档一个我们可以在打印机队列中识别的自定义名称：
doc.Print(printerSettings, "My rendered document");
```

### 也可以看看

* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)

---

## Print(PrinterSettings, string) {#print_2}

根据指定的打印机设置打印文档， 使用标准（无用户界面）打印控制器和文档名称。

```csharp
public void Print(PrinterSettings printerSettings, string documentName)
```

| 范围 | 类型 | 描述 |
| --- | --- | --- |
| printerSettings | PrinterSettings | 要使用的打印机设置。 |
| documentName | String | 打印文档时要显示的文档名称（例如，在打印状态 dialog 框或打印机队列中）。 |

### 评论

这PrinterSettings 对象允许您指定要打印的打印机、要打印的页面范围和其他选项。

### 例子

显示如何打印一系列页面。

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// 创建一个“PrinterSettings”对象来修改我们打印文档的方式。
PrinterSettings printerSettings = new PrinterSettings();

// 将“PrintRange”属性设置为“PrintRange.SomePages”以
// 告诉打印机我们打算只打印一些文档页面。
printerSettings.PrintRange = System.Drawing.Printing.PrintRange.SomePages;

// 将“FromPage”属性设置为“1”，将“ToPage”属性设置为“3”以打印第 1 页到第 3 页。
// 页面索引是从 1 开始的。
printerSettings.FromPage = 1;
printerSettings.ToPage = 3;

// 下面是打印文档的两种方式。
// 1 - 在应用我们的打印设置时打印：
doc.Print(printerSettings);

// 2 - 在应用我们的打印设置时打印，同时也打印
// 给文档一个我们可以在打印机队列中识别的自定义名称：
doc.Print(printerSettings, "My rendered document");
```

### 也可以看看

* class [Document](../)
* 命名空间 [Aspose.Words](../../document/)
* 部件 [Aspose.Words](../../../)


