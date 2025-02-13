---
title: Document.Print
second_title: Справочник по API Aspose.Words для .NET
description: Document метод. Печать всего документа на принтере по умолчанию.
type: docs
weight: 620
url: /ru/net/aspose.words/document/print/
---
## Print() {#print}

Печать всего документа на принтере по умолчанию.

```csharp
public void Print()
```

### Примеры

Показывает, как распечатать документ на принтере по умолчанию.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Ниже приведены два способа печати нашего документа.
// 1 - Печать на принтере по умолчанию:
doc.Print();

// 2 - Указываем принтер, на котором мы хотим распечатать документ, по имени:
string myPrinter = PrinterSettings.InstalledPrinters[4];

Assert.AreEqual("HPDAAB96 (HP ENVY 5000 series)", myPrinter);

doc.Print(myPrinter);
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)

---

## Print(string) {#print_3}

Печать всего документа на указанном принтере, с использованием стандартного (без пользовательского интерфейса) контроллера печати.

```csharp
public void Print(string printerName)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| printerName | String | Имя принтера. |

### Примеры

Показывает, как распечатать документ на принтере по умолчанию.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// Ниже приведены два способа печати нашего документа.
// 1 - Печать на принтере по умолчанию:
doc.Print();

// 2 - Указываем принтер, на котором мы хотим распечатать документ, по имени:
string myPrinter = PrinterSettings.InstalledPrinters[4];

Assert.AreEqual("HPDAAB96 (HP ENVY 5000 series)", myPrinter);

doc.Print(myPrinter);
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)

---

## Print(PrinterSettings) {#print_1}

Печать документа в соответствии с заданными настройками принтера, с использованием стандартного (без пользовательского интерфейса) контроллера печати.

```csharp
public void Print(PrinterSettings printerSettings)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| printerSettings | PrinterSettings | Используемые настройки принтера. |

### Примечания

PrinterSettings Объект позволяет указать принтер для печати, диапазон страниц для печати и другие параметры.

### Примеры

Показывает, как распечатать диапазон страниц.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Создайте объект PrinterSettings, чтобы изменить способ печати документа.
PrinterSettings printerSettings = new PrinterSettings();

// Установите для свойства "PrintRange" значение "PrintRange.SomePages", чтобы
// сообщить принтеру, что мы намерены напечатать только некоторые страницы документа.
printerSettings.PrintRange = System.Drawing.Printing.PrintRange.SomePages;

// Установите для свойства "FromPage" значение "1", а для свойства "ToPage" значение "3", чтобы печатать страницы с 1 по 3.
// Индексация страницы начинается с 1.
printerSettings.FromPage = 1;
printerSettings.ToPage = 3;

// Ниже приведены два способа печати нашего документа.
// 1 - Печать с применением наших настроек печати:
doc.Print(printerSettings);

// 2 - Печать с применением наших настроек печати, а также
// присвоение документу пользовательского имени, которое мы можем распознать в очереди печати:
doc.Print(printerSettings, "My rendered document");
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)

---

## Print(PrinterSettings, string) {#print_2}

Печать документа в соответствии с указанными настройками принтера, с использованием стандартного (без пользовательского интерфейса) контроллера печати и имени документа.

```csharp
public void Print(PrinterSettings printerSettings, string documentName)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| printerSettings | PrinterSettings | Используемые настройки принтера. |
| documentName | String | Имя документа, которое будет отображаться (например, в окне состояния печати dialog или в очереди печати) при печати документа. |

### Примечания

PrinterSettings Объект позволяет указать принтер для печати, диапазон страниц для печати и другие параметры.

### Примеры

Показывает, как распечатать диапазон страниц.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

// Создайте объект PrinterSettings, чтобы изменить способ печати документа.
PrinterSettings printerSettings = new PrinterSettings();

// Установите для свойства "PrintRange" значение "PrintRange.SomePages", чтобы
// сообщить принтеру, что мы намерены напечатать только некоторые страницы документа.
printerSettings.PrintRange = System.Drawing.Printing.PrintRange.SomePages;

// Установите для свойства "FromPage" значение "1", а для свойства "ToPage" значение "3", чтобы печатать страницы с 1 по 3.
// Индексация страницы начинается с 1.
printerSettings.FromPage = 1;
printerSettings.ToPage = 3;

// Ниже приведены два способа печати нашего документа.
// 1 - Печать с применением наших настроек печати:
doc.Print(printerSettings);

// 2 - Печать с применением наших настроек печати, а также
// присвоение документу пользовательского имени, которое мы можем распознать в очереди печати:
doc.Print(printerSettings, "My rendered document");
```

### Смотрите также

* class [Document](../)
* пространство имен [Aspose.Words](../../document/)
* сборка [Aspose.Words](../../../)


