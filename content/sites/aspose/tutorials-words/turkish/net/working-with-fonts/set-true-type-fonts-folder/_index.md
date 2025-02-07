---
title: True Type Yazı Tipleri Klasörünü Ayarla
linktitle: True Type Yazı Tipleri Klasörünü Ayarla
second_title: Aspose.Words Belge İşleme API'sı
description: Aspose.Words for .NET kullanarak bir belgeyi işlerken gerçek tip yazı tipi klasörünü ayarlamak için adım adım kılavuz.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-true-type-fonts-folder/
---

Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi işlerken gerçek tip yazı tipleri klasörünü ayarlamak için size adım adım yol göstereceğiz. Birlikte verilen C# kaynak kodunu açıklayacağız ve bu özelliği anlamanıza ve kendi projelerinizde uygulamanıza yardımcı olacak kapsamlı bir kılavuz sağlayacağız. Bu eğitimin sonunda, belgelerinizi Aspose.Words for .NET kullanarak işlerken True Type yazı tiplerini içeren özel bir klasörü nasıl belirteceğinizi öğreneceksiniz.

## 1. Adım: Belge dizinini tanımlayın
Öncelikle, belgeler dizininize giden yolu ayarlamanız gerekir. Bu, düzenlenen işlenmiş belgenizi kaydetmek istediğiniz konumdur. "BELGELER DİZİNİNİZİ" uygun yolla değiştirin.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. Adım: Oluşturulacak belgeyi yükleyin
 Ardından, kullanarak işlenecek belgeyi yüklemeniz gerekir.`Document` sınıf. Doğru belge yolunu belirttiğinizden emin olun.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 3. Adım: True Type Fonts Klasörünü Ayarlayın
Artık, gerçek tip yazı tiplerinin bir örneğini oluşturarak oluşturma sırasında kullanılacak klasörü belirtebilirsiniz.`FontSettings` sınıf ve kullanarak`SetFontsFolder()` yazı tipi klasörünü ayarlama yöntemi. True Type yazı tiplerinizi içeren özel bir klasör belirtebilirsiniz. için ikinci parametre`SetFontsFolder()` belirtilen klasörün alt klasörlerini de aramak isteyip istemediğinizi belirtir.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## 4. Adım: Oluşturulan belgeyi kaydedin
 Son olarak, işlenen belgeyi kullanarak bir dosyaya kaydedebilirsiniz.`Save()` yöntemi`Document` sınıf. Doğru yolu ve dosya adını belirttiğinizden emin olun.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Aspose.Words for .NET kullanarak Set True Type Fonts Klasörü için örnek kaynak kodu 

```csharp
//Belge dizininizin yolu
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Bu ayarın, varsayılan olarak aranmakta olan tüm varsayılan yazı tipi kaynaklarını geçersiz kılacağını unutmayın. Şimdi sadece bu klasörler aranacak
// Yazı tiplerini oluştururken veya katıştırırken yazı tipleri. Sistem yazı tipi kaynaklarını korurken fazladan bir yazı tipi kaynağı eklemek için hem FontSettings.GetFontSources hem de
// Bunun yerine FontSettings.SetFontSources
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Yazı tipi ayarlarını ayarla
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Çözüm
Bu öğreticide, Aspose.Words for .NET kullanarak bir belgeyi işlerken gerçek tip yazı tiplerini nasıl ayarlayacağımızı öğrendik. Bu adım adım kılavuzu izleyerek, belgelerinizi işlerken kullanmak üzere True Type yazı tiplerini içeren özel bir klasörü kolayca belirleyebilirsiniz. Aspose.Words, belgelerinizdeki yazı tipleriyle Kelime İşleme için güçlü ve esnek bir API sunar. Bu bilgiyle, belgelerinizi özel ihtiyaçlarınıza göre işlerken kullanılan yazı tiplerini kontrol edebilir ve özelleştirebilirsiniz.

### SSS

#### S: Aspose.Words'ta TrueType yazı tipleri klasörünü nasıl yapılandırabilirim?

 C: Aspose.Words'ta TrueType yazı tipleri klasörünü yapılandırmak için`SetTrueTypeFontsFolder` yöntemi`Fonts` TrueType yazı tiplerini içeren klasörün konumunu belirten sınıf.

#### S: Ne tür yazı tipleri TrueType yazı tipleri olarak kabul edilir?

Y: TrueType yazı tipleri popüler bir yazı tipi biçimidir. Genellikle Word belgelerinde kullanılırlar ve .ttf veya .ttc dosya uzantılarına sahiptirler.

#### S: Aspose.Words'ta birden fazla TrueType yazı tipi klasörü belirtebilir miyim?

C: Evet, Aspose.Words'ta birden fazla TrueType yazı tipi klasörü belirtebilirsiniz.`SetTrueTypeFontsFolder` yöntemi`Fonts` klasör konumlarının bir listesini içeren sınıf.

#### S: Aspose.Words'ta yapılandırılan TrueType yazı tipleri klasörünü nasıl kontrol edebilirim?

 C: Aspose.Words'ta yapılandırılan TrueType Fonts klasörünü kontrol etmek için`GetTrueTypeFontsFolder` yöntemi`Fonts` Yapılandırılan TrueType Fonts klasörünün konumunu almak için sınıf.

#### S: Aspose.Words'ta TrueType yazı tipleri klasörünü yapılandırmak neden önemlidir?

C: Aspose.Words'ta TrueType yazı tipleri klasörünün ayarlanması önemlidir çünkü Aspose.Words'ün Word belgelerini işlerken ihtiyaç duyduğu yazı tiplerini bulmasına yardımcı olur. Bu, farklı sistemlerde bile belge biçimlendirmesinde ve görünümünde tutarlılık sağlar.