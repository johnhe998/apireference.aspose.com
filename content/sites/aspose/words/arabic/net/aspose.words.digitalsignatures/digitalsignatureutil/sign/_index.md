---
title: DigitalSignatureUtil.Sign
second_title: Aspose.Words لمراجع .NET API
description: DigitalSignatureUtil طريقة. يوقع المستند المصدر باستخدام معينCertificateHolder وSignOptions بالتوقيع الرقمي ويكتب المستند الموقع إلى تيار الوجهة.
type: docs
weight: 30
url: /ar/net/aspose.words.digitalsignatures/digitalsignatureutil/sign/
---
## Sign(Stream, Stream, CertificateHolder, SignOptions) {#sign_1}

يوقع المستند المصدر باستخدام معين[`CertificateHolder`](../../certificateholder/) و[`SignOptions`](../../signoptions/) بالتوقيع الرقمي ويكتب المستند الموقع إلى تيار الوجهة.

يجب أن يكون المستند إماDoc أوDocx.

**ستتم كتابة الإخراج في بداية البث وسيتم تحديث حجم البث بطول المحتوى.**

```csharp
public static void Sign(Stream srcStream, Stream dstStream, CertificateHolder certHolder, 
    SignOptions signOptions)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| srcStream | Stream | الدفق الذي يحتوي على الوثيقة للتوقيع. |
| dstStream | Stream | الدفق الذي ستتم كتابة المستند الموقع عليه. |
| certHolder | CertificateHolder | [`CertificateHolder`](../../certificateholder/) بشهادة تستخدم لتوقيع الملف. يجب أن تحتوي الشهادة الموجودة في الحامل على مفاتيح خاصة وأن تحتوي على مجموعة العلامات X509KeyStorageFlags.Exportable. |
| signOptions | SignOptions | [`SignOptions`](../../signoptions/) مع خيارات توقيع متنوعة. |

### أمثلة

يوضح كيفية توقيع المستندات رقميًا.

```csharp
// أنشئ شهادة X.509 من متجر PKCS # 12 ، والتي يجب أن تحتوي على مفتاح خاص.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

// أنشئ تعليقًا وتاريخًا سيتم تطبيقه بتوقيعنا الرقمي الجديد.
SignOptions signOptions = new SignOptions
{
    Comments = "My comment", 
    SignTime = DateTime.Now
};

// خذ مستندًا غير موقع من نظام الملفات المحلي عبر تدفق ملف ،
// ثم أنشئ نسخة موقعة منه يحددها اسم ملف تدفق ملف الإخراج.
using (Stream streamIn = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    using (Stream streamOut = new FileStream(ArtifactsDir + "DigitalSignatureUtil.SignDocument.docx", FileMode.OpenOrCreate))
    {
        DigitalSignatureUtil.Sign(streamIn, streamOut, certificateHolder, signOptions);
    }
}
```

### أنظر أيضا

* class [CertificateHolder](../../certificateholder/)
* class [SignOptions](../../signoptions/)
* class [DigitalSignatureUtil](../)
* مساحة الاسم [Aspose.Words.DigitalSignatures](../../digitalsignatureutil/)
* المجسم [Aspose.Words](../../../)

---

## Sign(string, string, CertificateHolder, SignOptions) {#sign_3}

يوقع المستند المصدر باستخدام معين[`CertificateHolder`](../../certificateholder/) و[`SignOptions`](../../signoptions/) بالتوقيع الرقمي ويكتب المستند الموقع إلى ملف الوجهة.

يجب أن يكون المستند إماDoc أوDocx.

```csharp
public static void Sign(string srcFileName, string dstFileName, CertificateHolder certHolder, 
    SignOptions signOptions)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| srcFileName | String | اسم ملف المستند المراد توقيعه. |
| dstFileName | String | اسم ملف إخراج المستند الموقع. |
| certHolder | CertificateHolder | [`CertificateHolder`](../../certificateholder/) بشهادة تستخدم لتوقيع الملف. يجب أن تحتوي الشهادة الموجودة في الحامل على مفاتيح خاصة وأن تحتوي على مجموعة العلامات X509KeyStorageFlags.Exportable. |
| signOptions | SignOptions | [`SignOptions`](../../signoptions/) مع خيارات توقيع متنوعة. |

### أمثلة

يوضح كيفية إضافة سطر توقيع إلى مستند ، ثم توقيعه باستخدام شهادة رقمية.

```csharp
public static void Sign()
        {
            string signeeName = "Ron Williams";
            string srcDocumentPath = MyDir + "Document.docx";
            string dstDocumentPath = ArtifactsDir + "SignDocumentCustom.Sign.docx";
            string certificatePath = MyDir + "morzal.pfx";
            string certificatePassword = "aw";

            CreateSignees();

            Signee signeeInfo = mSignees.Find(c => c.Name == signeeName);

            if (signeeInfo != null)
                SignDocument(srcDocumentPath, dstDocumentPath, signeeInfo, certificatePath, certificatePassword);
            else
                Assert.Fail("Signee does not exist.");
        }

        /// <summary>
        /// ينشئ نسخة من مستند مصدر موقع باستخدام معلومات الموقّع المقدمة وشهادة X509.
        /// </summary>
        private static void SignDocument(string srcDocumentPath, string dstDocumentPath,
            Signee signeeInfo, string certificatePath, string certificatePassword)
        {
            Document document = new Document(srcDocumentPath);
            DocumentBuilder builder = new DocumentBuilder(document);

            // تكوين وإدراج سطر توقيع ، وهو كائن في المستند سيعرض توقيعًا نوقعه به.
            SignatureLineOptions signatureLineOptions = new SignatureLineOptions
            {
                Signer = signeeInfo.Name, 
                SignerTitle = signeeInfo.Position
            };

            SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
            signatureLine.Id = signeeInfo.PersonId;

            // أولاً ، سنحفظ نسخة غير موقعة من وثيقتنا.
            builder.Document.Save(dstDocumentPath);

            CertificateHolder certificateHolder = CertificateHolder.Create(certificatePath, certificatePassword);

            SignOptions signOptions = new SignOptions
            {
                SignatureLineId = signeeInfo.PersonId,
                SignatureLineImage = signeeInfo.Image
            };

            // اكتب فوق المستند غير الموقع الذي حفظناه أعلاه بإصدار موقع باستخدام الشهادة.
            DigitalSignatureUtil.Sign(dstDocumentPath, dstDocumentPath, certificateHolder, signOptions);
        }

#if NET48 || JAVA
        /// <summary>
        /// يحول صورة إلى مصفوفة بايت.
        /// </summary>
        private static byte[] ImageToByteArray(Image imageIn)
        {
            using (MemoryStream ms = new MemoryStream())
            {
                imageIn.Save(ms, ImageFormat.Png);
                return ms.ToArray();
            }
        }
#endif

        public class Signee
        {
            public Guid PersonId { get; set; }
            public string Name { get; set; }
            public string Position { get; set; }
            public byte[] Image { get; set; }

            public Signee(Guid guid, string name, string position, byte[] image)
            {
                PersonId = guid;
                Name = name;
                Position = position;
                Image = image;
            }
        }

        private static void CreateSignees()
        {
            mSignees = new List<Signee>
            {
                #if NET48 || JAVA
                new Signee(Guid.NewGuid(), "Ron Williams", "Chief Executive Officer",
                    ImageToByteArray(Image.FromFile(ImageDir + "Logo.jpg"))),
                #elif NET5_0_OR_GREATER || __MOBILE__
                new Signee(Guid.NewGuid(), "Ron Williams", "Chief Executive Officer", 
                    SkiaSharp.SKBitmap.Decode(ImageDir + "Logo.jpg").Bytes),
                #endif

                #if NET48 || JAVA
                new Signee(Guid.NewGuid(), "Stephen Morse", "Head of Compliance",
                    ImageToByteArray(Image.FromFile(ImageDir + "Logo.jpg")))
                #elif NET5_0_OR_GREATER || __MOBILE__
                new Signee(Guid.NewGuid(), "Stephen Morse", "Head of Compliance", 
                    SkiaSharp.SKBitmap.Decode(ImageDir + "Logo.jpg").Bytes)
                #endif
            };
        }

        private static List<Signee> mSignees;
```

### أنظر أيضا

* class [CertificateHolder](../../certificateholder/)
* class [SignOptions](../../signoptions/)
* class [DigitalSignatureUtil](../)
* مساحة الاسم [Aspose.Words.DigitalSignatures](../../digitalsignatureutil/)
* المجسم [Aspose.Words](../../../)

---

## Sign(Stream, Stream, CertificateHolder) {#sign}

يوقع المستند المصدر باستخدام معين[`CertificateHolder`](../../certificateholder/)مع التوقيع الرقمي_ ويكتب المستند الموقع إلى تيار الوجهة.

يجب أن يكون المستند إماDoc أوDocx.

**ستتم كتابة الإخراج في بداية البث وسيتم تحديث حجم البث بطول المحتوى.**

```csharp
public static void Sign(Stream srcStream, Stream dstStream, CertificateHolder certHolder)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| srcStream | Stream | الدفق الذي يحتوي على الوثيقة للتوقيع. |
| dstStream | Stream | الدفق الذي ستتم كتابة المستند الموقع عليه. |
| certHolder | CertificateHolder | [`CertificateHolder`](../../certificateholder/) بشهادة تستخدم لتوقيع الملف. يجب أن تحتوي الشهادة الموجودة في الحامل على مفاتيح خاصة وأن تحتوي على مجموعة العلامات X509KeyStorageFlags.Exportable. |

### أمثلة

يوضح كيفية توقيع المستندات بشهادات X.509.

```csharp
// تحقق من عدم توقيع المستند.
Assert.False(FileFormatUtil.DetectFileFormat(MyDir + "Document.docx").HasDigitalSignature);

// أنشئ كائن CertificateHolder من ملف PKCS12 ، والذي سنستخدمه لتوقيع الوثيقة.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw", null);

// توجد طريقتان لحفظ نسخة موقعة من المستند في نظام الملفات المحلي:
// 1 - قم بتعيين مستند باسم ملف نظام محلي وحفظ نسخة موقعة في موقع محدد بواسطة اسم ملف آخر.
DigitalSignatureUtil.Sign(MyDir + "Document.docx", ArtifactsDir + "Document.DigitalSignature.docx", 
    certificateHolder, new SignOptions() { SignTime = DateTime.Now } );

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// 2 - خذ مستندًا من دفق واحفظ نسخة موقعة في دفق آخر.
using (FileStream inDoc = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    using (FileStream outDoc = new FileStream(ArtifactsDir + "Document.DigitalSignature.docx", FileMode.Create))
    {
        DigitalSignatureUtil.Sign(inDoc, outDoc, certificateHolder);
    }
}

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// الرجاء التحقق من أن جميع التوقيعات الرقمية الخاصة بالمستند صالحة وتحقق من تفاصيلها.
Document signedDoc = new Document(ArtifactsDir + "Document.DigitalSignature.docx");
DigitalSignatureCollection digitalSignatureCollection = signedDoc.DigitalSignatures;

Assert.True(digitalSignatureCollection.IsValid);
Assert.AreEqual(1, digitalSignatureCollection.Count);
Assert.AreEqual(DigitalSignatureType.XmlDsig, digitalSignatureCollection[0].SignatureType);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].IssuerName);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].SubjectName);
```

### أنظر أيضا

* class [CertificateHolder](../../certificateholder/)
* class [DigitalSignatureUtil](../)
* مساحة الاسم [Aspose.Words.DigitalSignatures](../../digitalsignatureutil/)
* المجسم [Aspose.Words](../../../)

---

## Sign(string, string, CertificateHolder) {#sign_2}

يوقع المستند المصدر باستخدام معين[`CertificateHolder`](../../certificateholder/) مع التوقيع الرقمي_ وكتابة المستند الموقع إلى الملف الوجهة.

يجب أن يكون المستند إماDoc أوDocx.

```csharp
public static void Sign(string srcFileName, string dstFileName, CertificateHolder certHolder)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| srcFileName | String | اسم ملف المستند المراد توقيعه. |
| dstFileName | String | اسم ملف إخراج المستند الموقع. |
| certHolder | CertificateHolder | [`CertificateHolder`](../../certificateholder/) بشهادة تستخدم لتوقيع الملف. يجب أن تحتوي الشهادة الموجودة في الحامل على مفاتيح خاصة وأن تحتوي على مجموعة العلامات X509KeyStorageFlags.Exportable. |

### أمثلة

يوضح كيفية توقيع المستندات بشهادات X.509.

```csharp
// تحقق من عدم توقيع المستند.
Assert.False(FileFormatUtil.DetectFileFormat(MyDir + "Document.docx").HasDigitalSignature);

// أنشئ كائن CertificateHolder من ملف PKCS12 ، والذي سنستخدمه لتوقيع الوثيقة.
CertificateHolder certificateHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw", null);

// توجد طريقتان لحفظ نسخة موقعة من المستند في نظام الملفات المحلي:
// 1 - قم بتعيين مستند باسم ملف نظام محلي وحفظ نسخة موقعة في موقع محدد بواسطة اسم ملف آخر.
DigitalSignatureUtil.Sign(MyDir + "Document.docx", ArtifactsDir + "Document.DigitalSignature.docx", 
    certificateHolder, new SignOptions() { SignTime = DateTime.Now } );

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// 2 - خذ مستندًا من دفق واحفظ نسخة موقعة في دفق آخر.
using (FileStream inDoc = new FileStream(MyDir + "Document.docx", FileMode.Open))
{
    using (FileStream outDoc = new FileStream(ArtifactsDir + "Document.DigitalSignature.docx", FileMode.Create))
    {
        DigitalSignatureUtil.Sign(inDoc, outDoc, certificateHolder);
    }
}

Assert.True(FileFormatUtil.DetectFileFormat(ArtifactsDir + "Document.DigitalSignature.docx").HasDigitalSignature);

// الرجاء التحقق من أن جميع التوقيعات الرقمية الخاصة بالمستند صالحة وتحقق من تفاصيلها.
Document signedDoc = new Document(ArtifactsDir + "Document.DigitalSignature.docx");
DigitalSignatureCollection digitalSignatureCollection = signedDoc.DigitalSignatures;

Assert.True(digitalSignatureCollection.IsValid);
Assert.AreEqual(1, digitalSignatureCollection.Count);
Assert.AreEqual(DigitalSignatureType.XmlDsig, digitalSignatureCollection[0].SignatureType);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].IssuerName);
Assert.AreEqual("CN=Morzal.Me", signedDoc.DigitalSignatures[0].SubjectName);
```

### أنظر أيضا

* class [CertificateHolder](../../certificateholder/)
* class [DigitalSignatureUtil](../)
* مساحة الاسم [Aspose.Words.DigitalSignatures](../../digitalsignatureutil/)
* المجسم [Aspose.Words](../../../)


