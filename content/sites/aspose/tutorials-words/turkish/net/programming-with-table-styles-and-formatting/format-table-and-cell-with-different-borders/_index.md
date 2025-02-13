---
title: Tabloyu ve Hücreyi Farklı Kenarlıklarla Biçimlendirme
linktitle: Tabloyu ve Hücreyi Farklı Kenarlıklarla Biçimlendirme
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak tablo ve hücreyi farklı kenarlıklarla biçimlendirmek için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir tabloyu ve hücreyi farklı kenarlıklarla biçimlendirme sürecini adım adım anlatacağız. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, Aspose.Words for .NET kullanarak Word belgelerinizdeki belirli tablo ve hücrelere nasıl özel kenarlıklar uygulayacağınızı öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, düzenlenmiş Word belgenizi kaydetmek istediğiniz konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Yeni bir belge ve belge oluşturucu oluşturun
 Ardından, yeni bir örneğini oluşturmanız gerekir.`Document` sınıf ve bu belge için bir belge oluşturucu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. Adım: Yeni bir tablo başlatın ve hücreleri ekleyin
Tabloyu oluşturmaya başlamak için,`StartTable()` Belge oluşturucunun yöntemini kullanarak tabloya hücreler ekleriz.`InsertCell()` yöntemini kullanarak hücrelerin içeriğini yazıyoruz.`Writeln()` yöntem.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Tüm tablo için kenarlıklar belirleyin.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Bu hücre için dolguyu ayarlayın.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// İkinci hücre için farklı bir hücre dolgusu belirtin.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Önceki işlemlerden hücre biçimlendirmesini temizleyin.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Bu satırdaki ilk hücre için daha kalın kenarlıklar oluşturun. farklı olacak
// tablo için tanımlanan sınırlara göre.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## 4. Adım: Belgeyi kaydedin

  değiştirilmiş
Son olarak değiştirilen belgeyi bir dosyaya kaydedin. Çıktı belgesi için uygun bir ad ve konum seçebilirsiniz.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Tebrikler! Artık Aspose.Words for .NET'i kullanarak bir tabloyu ve bir hücreyi farklı kenarlıklarla biçimlendirdiniz.

### Aspose.Words for .NET kullanarak Tabloyu ve Hücreyi Farklı Kenarlıklarla Formatlamak için örnek kaynak kodu 

```csharp
	//Belge dizininizin yolu
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Tüm tablo için kenarlıkları ayarlayın.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// Bu hücre için hücre gölgelemesini ayarlayın.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// İkinci hücre için farklı bir hücre gölgelemesi belirtin.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// Önceki işlemlerden hücre biçimlendirmesini temizleyin.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// Bu satırın ilk hücresi için daha geniş kenarlıklar oluşturun. bu farklı olacak
	// tablo için ayarlanan kenarlıklarla karşılaştırılır.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir tabloyu ve hücreyi farklı kenarlıklarla nasıl biçimlendireceğimizi öğrendik. Bu adım adım kılavuzu izleyerek, Word belgelerinizdeki tablo ve hücre kenarlıklarını kolayca özelleştirebilirsiniz. Aspose.Words, belgelerinizdeki tabloları değiştirmek ve biçimlendirmek için güçlü ve esnek bir API sunar. Bu bilgiyle, Word belgelerinizin görsel sunumunu geliştirebilir ve belirli ihtiyaçları karşılayabilirsiniz.