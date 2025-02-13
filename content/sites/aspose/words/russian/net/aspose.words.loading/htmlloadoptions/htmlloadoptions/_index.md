---
title: HtmlLoadOptions.HtmlLoadOptions
second_title: Справочник по API Aspose.Words для .NET
description: HtmlLoadOptions строитель. Инициализирует новый экземпляр этого класса со значениями по умолчанию.
type: docs
weight: 10
url: /ru/net/aspose.words.loading/htmlloadoptions/htmlloadoptions/
---
## HtmlLoadOptions() {#constructor}

Инициализирует новый экземпляр этого класса со значениями по умолчанию.

```csharp
public HtmlLoadOptions()
```

### Примеры

Показывает, как поддерживать условные комментарии при загрузке HTML-документа.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions();

// Если значение истинно, то мы учитываем код VML при синтаксическом анализе загруженного документа.
loadOptions.SupportVml = supportVml;

// Этот документ содержит изображение JPEG внутри "<!--[if gte vml 1]>" теги,
// и другое изображение PNG внутри "<![if !vml]>" теги.
// Если мы установим флаг "SupportVml" в "true", то Aspose.Words загрузит JPEG.
// Если мы установим для этого флага значение "false", то Aspose.Words будет загружать только PNG.
Document doc = new Document(MyDir + "VML conditional.htm", loadOptions);

if (supportVml)
    Assert.AreEqual(ImageType.Jpeg, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
else
    Assert.AreEqual(ImageType.Png, ((Shape)doc.GetChild(NodeType.Shape, 0, true)).ImageData.ImageType);
```

### Смотрите также

* class [HtmlLoadOptions](../)
* пространство имен [Aspose.Words.Loading](../../htmlloadoptions/)
* сборка [Aspose.Words](../../../)

---

## HtmlLoadOptions(string) {#constructor_2}

Ярлык для инициализации нового экземпляра этого класса с указанным паролем для загрузки зашифрованного документа.

```csharp
public HtmlLoadOptions(string password)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| password | String | Пароль для открытия зашифрованного документа. Может быть нулевой или пустой строкой. |

### Примеры

Показывает, как зашифровать HTML-документ, а затем открыть его с помощью пароля.

```csharp
// Создать и подписать зашифрованный HTML-документ из зашифрованного .docx.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

SignOptions signOptions = new SignOptions
{
    Comments = "Comment",
    SignTime = DateTime.Now,
    DecryptionPassword = "docPassword"
};

string inputFileName = MyDir + "Encrypted.docx";
string outputFileName = ArtifactsDir + "HtmlLoadOptions.EncryptedHtml.html";
DigitalSignatureUtil.Sign(inputFileName, outputFileName, certificateHolder, signOptions);

// Чтобы загрузить и прочитать этот документ, нам нужно будет пройти его расшифровку
// пароль с использованием объекта HtmlLoadOptions.
HtmlLoadOptions loadOptions = new HtmlLoadOptions("docPassword");

Assert.AreEqual(signOptions.DecryptionPassword, loadOptions.Password);

Document doc = new Document(outputFileName, loadOptions);

Assert.AreEqual("Test encrypted document.", doc.GetText().Trim());
```

### Смотрите также

* class [HtmlLoadOptions](../)
* пространство имен [Aspose.Words.Loading](../../htmlloadoptions/)
* сборка [Aspose.Words](../../../)

---

## HtmlLoadOptions(LoadFormat, string, string) {#constructor_1}

Ярлык для инициализации нового экземпляра этого класса со свойствами, установленными на указанные значения.

```csharp
public HtmlLoadOptions(LoadFormat loadFormat, string password, string baseUri)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| loadFormat | LoadFormat | Формат загружаемого документа. |
| password | String | Пароль для открытия зашифрованного документа. Может быть нулевой или пустой строкой. |
| baseUri | String | Строка, которая будет использоваться для преобразования относительных URI в абсолютные. Может быть нулевой или пустой строкой. |

### Примеры

Показывает, как указать базовый URI при открытии html-документа.

```csharp
// Предположим, мы хотим загрузить документ .html, содержащий изображение, связанное относительным URI
// пока изображение находится в другом месте. В этом случае нам нужно будет преобразовать относительный URI в абсолютный.
 // Мы можем предоставить базовый URI, используя объект HtmlLoadOptions.
HtmlLoadOptions loadOptions = new HtmlLoadOptions(LoadFormat.Html, "", ImageDir);

Assert.AreEqual(LoadFormat.Html, loadOptions.LoadFormat);

Document doc = new Document(MyDir + "Missing image.html", loadOptions);

// Хотя изображение во входном .html было повреждено, наш собственный базовый URI помог нам восстановить ссылку.
Shape imageShape = (Shape)doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(imageShape.IsImage);

// Этот выходной документ будет отображать отсутствующее изображение.
doc.Save(ArtifactsDir + "HtmlLoadOptions.BaseUri.docx");
```

### Смотрите также

* enum [LoadFormat](../../../aspose.words/loadformat/)
* class [HtmlLoadOptions](../)
* пространство имен [Aspose.Words.Loading](../../htmlloadoptions/)
* сборка [Aspose.Words](../../../)


