---
title: "AsposePdfSetInfo"
second_title: Aspose.PDF for JavaScript via C++
description: "Set info (metadata) in PDF file."
type: docs
url: /javascript-cpp/core/asposepdfsetinfo/
---

_Set info (metadata) in PDF file._

```js
function AsposePdfSetInfo(
    fileBlob,
    fileName,
    title, 
    creator, 
    author,
    subject,
    keywords,
    creation,
    mod,
    fileNameResult
)
```

**Parameters**: 

* **fileBlob** Blob object 
* **fileName** file name 
* **title** title
* **creator** creator
* **author** author
* **subject** subject
* **keywords** list keywords
* **creation** creation date
* **mod** modify date
* **fileResultName** result file name

For 'title', 'creator', 'author', 'subject', 'keywords', 'creation' and 'mod', if not need to set value, use undefined or "" (empty string)

**Return**: 

JSON object 

* **errorCode** - code error (0 no error)
* **errorText** - text error ("" no error)
* **fileNameResult** - result file name


**Example**:

```js
  var ffilePdfSetInfo = function (e) {
    const file_reader = new FileReader();
    file_reader.onload = (event) => {
      /*Set info (metadata) in PDF file.*/
      /*Set PDF info: title, creator, author, subject, keywords, creation (date), mod (date modify)*/
      /*if not need to set value, use undefined or "" (empty string)*/
      /*set info a PDF-file and save the "ResultSetInfo.pdf"*/
      const json = AsposePdfSetInfo(event.target.result, e.target.files[0].name, "Setting PDF Document Information", "", "Aspose", undefined, "Aspose.Pdf, DOM, API", undefined, "16/02/2023 11:55 PM", "ResultSetInfo.pdf");
      if (json.errorCode == 0) document.getElementById('output').textContent = json.fileNameResult;
      else document.getElementById('output').textContent = json.errorText;
      /*make a link to download the result file*/
      DownloadFile(json.fileNameResult, "application/pdf");
    };
    file_reader.readAsArrayBuffer(e.target.files[0]);
  };
```
**Web Worker**:
```js
  /*Create Web Worker*/
  const AsposePDFWebWorker = new Worker("AsposePDFforJS.js");
  AsposePDFWebWorker.onerror = evt => console.log(`Error from Web Worker: ${evt.message}`);
  AsposePDFWebWorker.onmessage = evt => document.getElementById('output').textContent = 
    (evt.data == 'ready') ? 'loaded!' :
      (evt.data.json.errorCode == 0) ?
        `Result:\n${DownloadFile(evt.data.json.fileNameResult, "application/pdf", evt.data.params[0])}` :
        `Error: ${evt.data.json.errorText}`;

  /*Event handler*/
  const ffilePdfSetInfo = e => {
    const file_reader = new FileReader();
    file_reader.onload = event => {
      /*PDF info: title, creator, author, subject, keywords, creation (date), mod (date modify)*/
      const title = 'Setting PDF Document Information';
      const creator = ''; /*if not need to set value, use: undefined or ""/'' (empty string)*/
      const author = 'Aspose';
      const subject = undefined;
      const keywords = 'Aspose.Pdf, DOM, API';
      const creation = undefined; /*create date*/
      const mod = '16/02/2023 11:55 PM'; /*modify date*/
      /*set info a PDF-file and save the "ResultSetInfo.pdf" - Ask Web Worker*/
      AsposePDFWebWorker.postMessage(
        { "operation": 'AsposePdfSetInfo',
          "params": [event.target.result, e.target.files[0].name, title, creator, author, subject, keywords, creation, mod, "ResultSetInfo.pdf"] },
        [event.target.result]
      );
    };
    file_reader.readAsArrayBuffer(e.target.files[0]);
  };

  /*make a link to download the result file*/
  const DownloadFile = (filename, mime, content) => {
      mime = mime || "application/octet-stream";
      var link = document.createElement("a"); 
      link.href = URL.createObjectURL(new Blob([content], {type: mime}));
      link.download = filename;
      link.innerHTML = "Click here to download the file " + filename;
      document.body.appendChild(link); 
      document.body.appendChild(document.createElement("br"));
      return filename;
    }
```