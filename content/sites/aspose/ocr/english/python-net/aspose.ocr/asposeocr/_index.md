---
title: AsposeOcr
second_title: Aspose.OCR for Python via .NET API Reference
description: 
type: docs
weight: 10
url: /python-net/aspose.ocr/asposeocr/
---

## AsposeOcr class

Main API for Aspose OCR library

The AsposeOcr type exposes the following members:
## Constructors
| Name | Description |
| :- | :- |
|AsposeOcr()|Initializes a new instance of the [AsposeOcr](/ocr/python-net/aspose.ocr/asposeocr/) class.<br/>            Empty constructor.|
## Methods
| Name | Description |
| :- | :- |
|recognize(images)|Recognizes text on images / documents.<br/>            Supports GIF, PNG, JPEG, BMP, TIFF, JFIF, stream, directory, arrays, archives.|
|recognize(images, settings)|Recognizes text on images / documents.<br/>            Supports GIF, PNG, JPEG, BMP, TIFF, JFIF, stream, directory, arrays, archives.|
|recognize_receipt(input)|Recognizes text on receipts.|
|recognize_receipt(input, settings)|Recognizes text on receipts.|
|recognize_invoice(input)|Recognizes text on invoices.|
|recognize_invoice(input, settings)|Recognizes text on invoices.|
|recognize_id_card(input)|Recognizes text on ID card.|
|recognize_id_card(input, settings)|Recognizes text on ID card.|
|recognize_car_plate(input)|Recognizes text on car plate.|
|recognize_car_plate(input, settings)|Recognizes text on car plate.|
|recognize_passport(input)|Recognizes text on passport.|
|recognize_passport(input, settings)|Recognizes text on passport.|
|recognize_lines(images)|Recognizes images that contain single line of text.<br/>            Supports GIF, PNG, JPEG, BMP, TIFF, JFIF, stream, folder, arrays, archives.|
|recognize_lines(images, settings)|Recognizes images that contain single line of text.<br/>            Supports GIF, PNG, JPEG, BMP, TIFF, JFIF, stream, folder, arrays, archives.|
|detect_rectangles(images)|Detects text areas on images.<br/>            Supports GIF, PNG, JPEG, BMP, TIFF, JFIF, stream, folder, arrays, archives.|
|detect_rectangles(images, areas_type, detect_areas)|Detects text areas on images.<br/>            Supports GIF, PNG, JPEG, BMP, TIFF, JFIF, stream, folder, arrays, archives.|
|recognize_characters(images)|Detects symbols on images.<br/>            Supports GIF, PNG, JPEG, BMP, TIFF, JFIF, stream, folder, arrays, archives.|
|recognize_characters(images, detect_areas_mode, language)|Detects symbols on images.<br/>            Supports GIF, PNG, JPEG, BMP, TIFF, JFIF, stream, folder, arrays, archives.|
|image_has_text(full_path, text, settings, ignore_case)|Check if the image contains the provided text fragment.|
|compare_image_texts(full_path1, full_path2, settings, ignore_case)|Check if two images contain the same text.|
|image_text_diff(full_path1, full_path2, settings, ignore_case)|Compare the texts on the two images and return a number representing how similar they are (0 to 1).|
|correct_spelling(text, language, dictionary_path)|Corrects text (replaces misspelled words).|
|save_multipage_document(full_file_name, save_format, results)|  |
|recognize_fast(images)|Recognizes text on images / documents.<br/>            Supports GIF, PNG, JPEG, BMP, TIFF, JFIF, stream, directory, arrays, archives.|
|calculate_skew(images)|Calculates the skew angles of an images.<br/>            Supports GIF, PNG, JPEG, BMP, TIFF, JFIF, stream, folder, arrays, archives.|

### See Also

* namespace [aspose.ocr](/ocr/python-net/aspose.ocr/)
* assembly [Aspose.ocr](/ocr/python-net/)

