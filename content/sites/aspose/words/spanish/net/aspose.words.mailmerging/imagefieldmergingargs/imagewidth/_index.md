---
title: ImageFieldMergingArgs.ImageWidth
second_title: Referencia de API de Aspose.Words para .NET
description: ImageFieldMergingArgs propiedad. Especifica el ancho de imagen para que la imagen se inserte en el documento.
type: docs
weight: 50
url: /es/net/aspose.words.mailmerging/imagefieldmergingargs/imagewidth/
---
## ImageFieldMergingArgs.ImageWidth property

Especifica el ancho de imagen para que la imagen se inserte en el documento.

```csharp
public MergeFieldImageDimension ImageWidth { get; set; }
```

### Observaciones

El valor de esta propiedad proviene inicialmente del código del MERGEFIELD correspondiente, contenido en el documento de plantilla . Para anular el valor inicial, debe asignar una instancia de [`MergeFieldImageDimension`](../../../aspose.words.fields/mergefieldimagedimension/) class a esta propiedad o establezca las propiedades para la instancia de[`MergeFieldImageDimension`](../../../aspose.words.fields/mergefieldimagedimension/) clase, devuelta por esta propiedad.

Para indicar que se debe aplicar el valor original del ancho de la imagen, debe asignar el **nulo** valor a esta propiedad o establecer el[`Value`](../../../aspose.words.fields/mergefieldimagedimension/value/) propiedad para la instancia de[`MergeFieldImageDimension`](../../../aspose.words.fields/mergefieldimagedimension/) clase, devuelta por esta propiedad, a un valor negativo.

### Ejemplos

Muestra cómo establecer las dimensiones de las imágenes tal como las acepta MERGEFIELDS durante una combinación de correspondencia.

```csharp
{
    Document doc = new Document();

    // Inserte un MERGEFIELD que aceptará imágenes de una fuente durante una combinación de correspondencia. Use el código de campo para hacer referencia
    // una columna en la fuente de datos que contiene los nombres de archivo del sistema local de las imágenes que deseamos usar en la combinación de correspondencia.
    DocumentBuilder builder = new DocumentBuilder(doc);
    FieldMergeField field = (FieldMergeField)builder.InsertField("MERGEFIELD Image:ImageColumn");

    // La fuente de datos debe tener una columna de este tipo denominada "ImageColumn".
    Assert.AreEqual("Image:ImageColumn", field.FieldName);

    // Crear una fuente de datos adecuada.
    DataTable dataTable = new DataTable("Images");
    dataTable.Columns.Add(new DataColumn("ImageColumn"));
    dataTable.Rows.Add(ImageDir + "Logo.jpg");
    dataTable.Rows.Add(ImageDir + "Transparent background logo.png");
    dataTable.Rows.Add(ImageDir + "Enhanced Windows MetaFile.emf");

    // Configure una devolución de llamada para modificar los tamaños de las imágenes en el momento de la combinación, luego ejecute la combinación de correspondencia.
    doc.MailMerge.FieldMergingCallback = new MergedImageResizer(200, 200, MergeFieldImageDimensionUnit.Point);
    doc.MailMerge.Execute(dataTable);

    doc.UpdateFields();
    doc.Save(ArtifactsDir + "Field.MERGEFIELD.ImageDimension.docx");

/// <summary>
/// Establece el tamaño de todas las imágenes combinadas de correo a un ancho y alto definidos.
/// </summary>
private class MergedImageResizer : IFieldMergingCallback
{
    public MergedImageResizer(double imageWidth, double imageHeight, MergeFieldImageDimensionUnit unit)
    {
        mImageWidth = imageWidth;
        mImageHeight = imageHeight;
        mUnit = unit;
    }

    public void FieldMerging(FieldMergingArgs e)
    {
        throw new NotImplementedException();
    }

    public void ImageFieldMerging(ImageFieldMergingArgs args)
    {
        args.ImageFileName = args.FieldValue.ToString();
        args.ImageWidth = new MergeFieldImageDimension(mImageWidth, mUnit);
        args.ImageHeight = new MergeFieldImageDimension(mImageHeight, mUnit);

        Assert.AreEqual(mImageWidth, args.ImageWidth.Value);
        Assert.AreEqual(mUnit, args.ImageWidth.Unit);
        Assert.AreEqual(mImageHeight, args.ImageHeight.Value);
        Assert.AreEqual(mUnit, args.ImageHeight.Unit);
    }

    private readonly double mImageWidth;
    private readonly double mImageHeight;
    private readonly MergeFieldImageDimensionUnit mUnit;
}
```

### Ver también

* class [MergeFieldImageDimension](../../../aspose.words.fields/mergefieldimagedimension/)
* class [ImageFieldMergingArgs](../)
* espacio de nombres [Aspose.Words.MailMerging](../../imagefieldmergingargs/)
* asamblea [Aspose.Words](../../../)


