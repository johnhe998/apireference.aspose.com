---
title: Enum WebExtensionBindingType
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.WebExtensions.WebExtensionBindingType Sıralama. Bir web uzantısı ile belgedeki veriler arasındaki mevcut bağlama türlerini numaralandırır.
type: docs
weight: 6460
url: /tr/net/aspose.words.webextensions/webextensionbindingtype/
---
## WebExtensionBindingType enumeration

Bir web uzantısı ile belgedeki veriler arasındaki mevcut bağlama türlerini numaralandırır.

```csharp
public enum WebExtensionBindingType
```

### değerler

| İsim | Değer | Tanım |
| --- | --- | --- |
| Matrix | `0` | Başlık satırı olmayan tablo verileri. |
| Table | `1` | Başlık satırı içeren tablo verileri. |
| Text | `2` | Düz metin. |
| Default | `0` |  |

### Örnekler

Bir belgeye nasıl web uzantısı ekleneceğini gösterir.

```csharp
Document doc = new Document();

// Belgenin kullanacağı "MyScript" eklentisi ile görev bölmesi oluşturun,
// ardından varsayılan konumunu ayarlayın.
TaskPane myScriptTaskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(myScriptTaskPane);
myScriptTaskPane.DockState = TaskPaneDockState.Right;
myScriptTaskPane.IsVisible = true;
myScriptTaskPane.Width = 300;
myScriptTaskPane.IsLocked = true;

// Aynı yerleştirme konumunda birden fazla görev bölmesi varsa, bunları düzenlemek için bu dizini ayarlayabiliriz.
myScriptTaskPane.Row = 1;

// Görev bölmesinin içinde görüntüleneceği "MyScript Math Sample" adlı bir eklenti oluşturun.
WebExtension webExtension = myScriptTaskPane.WebExtension;

// Eklentimiz için ID gibi uygulama mağazası referans parametrelerini ayarlayın.
webExtension.Reference.Id = "WA104380646";
webExtension.Reference.Version = "1.0.0.0";
webExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
webExtension.Reference.Store = CultureInfo.CurrentCulture.Name;
webExtension.Properties.Add(new WebExtensionProperty("MyScript", "MyScript Math Sample"));
webExtension.Bindings.Add(new WebExtensionBinding("MyScript", WebExtensionBindingType.Text, "104380646"));

// Kullanıcının eklentiyle etkileşime girmesine izin ver.
webExtension.IsFrozen = false;

// Microsoft Word'deki web uzantısına Developer -> Eklentiler.
doc.Save(ArtifactsDir + "Document.WebExtension.docx");

// Tüm web uzantısı görev bölmelerini bu şekilde bir kerede kaldırın.
doc.WebExtensionTaskPanes.Clear();

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.WebExtensions](../../aspose.words.webextensions/)
* toplantı [Aspose.Words](../../)


