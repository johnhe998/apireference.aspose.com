---
title: Metered.SetMeteredKey
second_title: Aspose.Words for .NET API Referansı
description: Metered yöntem. Ölçülü genel ve özel anahtarı ayarlar. Ölçülü lisans satın alırsanız uygulamayı başlattığınızda bu API çağrılmalıdır normalde bu yeterlidir. Ancak tüketim verileri her zaman yüklenemezse ve 24 saati aşarsa lisans değerlendirme durumuna ayarlanır böyle bir durumdan kaçınmak için  lisans durumunu düzenli olarak kontrol etmelisiniz eğer değerlendirme durumuysa bu APIyi tekrar arayın.
type: docs
weight: 20
url: /tr/net/aspose.words/metered/setmeteredkey/
---
## Metered.SetMeteredKey method

Ölçülü genel ve özel anahtarı ayarlar. Ölçülü lisans satın alırsanız, uygulamayı başlattığınızda bu API çağrılmalıdır, normalde bu yeterlidir. Ancak, tüketim verileri her zaman yüklenemezse ve 24 saati aşarsa, lisans değerlendirme durumuna ayarlanır, böyle bir durumdan kaçınmak için , lisans durumunu düzenli olarak kontrol etmelisiniz, eğer değerlendirme durumuysa bu API'yi tekrar arayın.

```csharp
public void SetMeteredKey(string publicKey, string privateKey)
```

| Parametre | Tip | Tanım |
| --- | --- | --- |
| publicKey | String | Genel anahtar |
| privateKey | String | Özel anahtar |

### Örnekler

Sayaçlı bir lisansın nasıl etkinleştirileceğini ve kredi/tüketimin nasıl izleneceğini gösterir.

```csharp
// Yeni bir Sayaçlı lisans oluşturun ve ardından kullanım istatistiklerini yazdırın.
Metered metered = new Metered();
metered.SetMeteredKey("MyPublicKey", "MyPrivateKey");

Console.WriteLine($"Credit before operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity before operation: {Metered.GetConsumptionQuantity()}");

// Aspose.Words kullanarak çalıştırın ve ardından ne kadar harcadığımızı görmek için ölçülen istatistiklerimizi tekrar yazdırın.
Document doc = new Document(MyDir + "Document.docx");
doc.Save(ArtifactsDir + "Metered.Usage.pdf");

// Aspose Metered Licensing mekanizması kullanım verilerini her seferinde satın alma sunucusuna göndermez,
// beklemeyi kullanmanız gerekiyor.
System.Threading.Thread.Sleep(10000);

Console.WriteLine($"Credit after operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity after operation: {Metered.GetConsumptionQuantity()}");
```

### Ayrıca bakınız

* class [Metered](../)
* ad alanı [Aspose.Words](../../metered/)
* toplantı [Aspose.Words](../../../)


