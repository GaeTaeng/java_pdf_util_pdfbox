# to be
java pdf util use pdfbox
![스크린샷 2022-11-24 11 24 17](https://user-images.githubusercontent.com/41108735/203680165-86ddeb4c-d889-4f07-b43e-f03329c59e43.png)


#example
```
PDFDocument pdfDocument = PDFDocument.createPDFDocument("A4");
pdfDocument.newPage("A4");
 
 
String[][] content =
    {{"오리고기+볶음밥", "50,000원"},
     {"기타 등등", "50,000,000원"},
     {"불닭볶음면", "2,000원"},
     {"닭갈비", "20,000원"},
     {"숯불 치킨 + 양념...", "21,000원"},
     {"과자", "18,000원"}} ;
 
 
//auto sort Center
pdfDocument.writeCenterLine("지출비용 내역서", 25);
 
 
//input "L", "C", "R" -> sort type
pdfDocument.drawTable(content, "C");
ByteArrayOutputStream bos = pdfDocument.endPDFDocument_bos();
```
[지출비용_내역서.pdf](https://github.com/GaeTaeng/java_pdf_util_pdfbox/files/10080341/_.77.pdf)


```
PDFDocument pdfDocument = PDFDocument.createPDFDocument("A4");
pdfDocument.newPage("A4");
 
 
String[][] content =
    {{"과자", "18,000원"},
     {"숯불 치킨 + 양념...", "21,000원"},
     {"불닭볶음면", "2,000원"},
     {"닭갈비", "20,000원"},
     {"오리고기+볶음밥", "50,000원"},
     {"기타 등등", "50,000,000원"},
     {"1", "2원"},
     {"2", "2원"},
     {"3", "2원"},
     {"4", "2원"},
     {"5", "2원"},
     {"6", "2원"},
     {"7", "2원"},
     {"8", "2원"},
     {"9", "2원"},
     {"10", "2원"},
     {"11", "2원"},
     {"12", "2원"},
     {"13", "2원"},
     {"14", "2원"},
     {"15", "2원"},
     {"16", "2원"},
     {"17", "2원"},
     {"18", "2원"},
     {"19", "2원"},
     {"20", "2원"},
     {"21", "2원"},
     {"22", "2원"},
     {"23", "2원"},
     {"24", "2원"},
     {"25", "2원"},
     {"26", "2원"},
     {"27", "2원"},
     {"28", "2원"},
     {"29", "2원"},
     {"30", "2원"}} ;
 
//auto sort Center
pdfDocument.writeCenterLine("지출비용 내역서", 25);
 
 
//input "L", "C", "R" -> sort type
pdfDocument.writeLine("FONT SIZE 14 //FONT SIZE 14 //FONT SIZE 14 //FONT SIZE 14
//FONT SIZE 14 //FONT SIZE 14 //FONT SIZE 14 //FONT SIZE 14 //FONT SIZE 14 //FONT SIZE 14
//FONT SIZE 14 //FONT SIZE 14 //FONT SIZE 14 //FONT SIZE 14 //FONT SIZE 14 //FONT SIZE 14
//FONT SIZE 14 //FONT SIZE 14 //", 14, "L");
pdfDocument.drawTable(content, "C");
ByteArrayOutputStream bos = pdfDocument.endPDFDocument_bos();
```[지출비용_내역서.pdf](https://github.com/GaeTaeng/java_pdf_util_pdfbox/files/10080343/_.82.pdf)

