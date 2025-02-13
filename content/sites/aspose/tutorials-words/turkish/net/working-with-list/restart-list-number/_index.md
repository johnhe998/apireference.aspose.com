---
title: Liste Numarasını Yeniden Başlat
linktitle: Liste Numarasını Yeniden Başlat
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET ile bir Word belgesindeki liste numarasını nasıl sıfırlayacağınızı öğrenin.
type: docs
weight: 10
url: /tr/net/working-with-list/restart-list-number/
---
Bu adım adım öğreticide, Aspose.Words for .NET kullanarak bir Word belgesindeki liste numarasını nasıl sıfırlayacağınızı göstereceğiz. Sağlanan C# kaynak kodunu açıklayacağız ve bunu kendi projelerinize nasıl uygulayacağınızı göstereceğiz.

Başlamak için geliştirme ortamınızda Aspose.Words for .NET'in kurulu ve yapılandırılmış olduğundan emin olun. Henüz yapmadıysanız, kütüphaneyi resmi siteden indirip yükleyin.

## 1. Adım: Belge ve Belge Oluşturucuyu Oluşturma

İlk olarak, yeni bir belge ve ilişkili bir belge oluşturucu oluşturun:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. Adım: İlk Listeyi Oluşturma ve Özelleştirme

Ardından, mevcut bir şablonu temel alan bir liste oluşturun ve ardından düzeylerini özelleştirin:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## 3. Adım: İlk listeye öğe ekleme

İlk listeye öğe eklemek ve liste numaralarını kaldırmak için belge oluşturucuyu kullanın:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 4. Adım: İkinci Listeyi Oluşturma ve Özelleştirme

Numarayı sıfırlayarak ilk listeyi yeniden kullanmak için orijinal liste düzeninin bir kopyasını oluşturun:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Gerekirse ikinci listede ek değişiklikler de yapabilirsiniz.

## Adım 5: İkinci listeye öğe ekleme

İkinci listeye öğe eklemek ve liste numaralarını kaldırmak için belge oluşturucuyu tekrar kullanın:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 6. Adım: Değiştirilen belgeyi kaydedin

Son olarak, değiştirilen belgeyi kaydedin:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Bu yüzden ! Aspose.Words for .NET kullanarak bir Word belgesindeki liste numarasını başarıyla sıfırladınız.

### Liste Numarası Sıfırlama için Örnek Kaynak Kodu

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bir şablona dayalı bir liste oluşturun.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// İlk listeyi yeniden kullanmak için orijinal liste biçimlendirmesinin bir kopyasını oluşturarak numaralandırmayı yeniden başlatmamız gerekiyor.
List list2 = doc.Lists.AddCopy(list1);

//Yeni bir başlangıç numarası belirlemek dahil, yeni listeyi herhangi bir şekilde değiştirebiliriz.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### SSS

#### S: Aspose.Words'te bir listenin numaralandırmasını nasıl yeniden başlatabilirim?

 C: Aspose.Words'te bir listenin numaralandırmasını yeniden başlatmak için`ListRestartAtNumber` yöntemi`List` sınıf. Bu yöntem, listenin yeniden başlatılması gereken yeni bir arama değeri belirlemenizi sağlar. Örneğin, kullanabilirsiniz`list.ListRestartAtNumber(1)` 1'den numaralandırmayı yeniden başlatmak için.

#### S: Aspose.Words'te yeniden başlatılan liste numaralandırmasının ön ekini ve son ekini özelleştirmek mümkün mü?

 C: Evet, Aspose.Words'ta yeniden başlatılan liste numaralandırmasının ön ekini ve son ekini özelleştirebilirsiniz. bu`ListLevel` sınıf gibi özellikler sunar`ListLevel.NumberPrefix` Ve`ListLevel.NumberSuffix` listedeki her seviye için önek ve soneki belirtmenize izin verir. Ön eki ve son eki gerektiği gibi özelleştirmek için bu özellikleri kullanabilirsiniz.

#### S: Listenin yeniden başlatılması gereken belirli bir numaralandırma değerini nasıl belirleyebilirim?

 C: Listenin yeniden başlatılması gereken belirli bir sayı değeri belirtmek için`ListRestartAtNumber`İstenen değeri bağımsız değişken olarak ileten yöntem. Örneğin, numaralandırmayı 5'ten yeniden başlatmak için şunu kullanabilirsiniz:`list.ListRestartAtNumber(5)`.

#### S: Aspose.Words'te çok seviyeli liste numaralandırmayı yeniden başlatmak mümkün mü?

 C: Evet, Aspose.Words çoklu liste seviyelerinin yeniden numaralandırmasını destekler. uygulayabilirsiniz`ListRestartAtNumber` Numaralandırmayı ayrı ayrı yeniden başlatmak için her liste düzeyinde yöntem. Örneğin, kullanabilirsiniz`list.Levels[0].ListRestartAtNumber(1)` ilk liste düzeyini 1'den yeniden başlatmak için ve`list.Levels[1].ListRestartAtNumber(1)` 1'den başlayarak ikinci düzey listeyi yeniden başlatmak için vb.



