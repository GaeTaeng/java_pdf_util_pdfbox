# JAVA Spring PDFDocument

PDFDocument 라는 클래스를 만들어 전체적인 PDF관련 작업을 간편하게 진행하기 위함
(+ 회사에서 작업하는데 너무 삽질을 많이해서 혼자 만들어보고 적용해보기 위함)
사용 예제등은 하단 참고


예정 기능
 - 에디터기능 — 1차범위 (로테크 자문계약관리 지출비용리스트 PDF 생성필요 기능)
 - Header Title 텍스트 추가 (Center 정렬처리)
 - Contents 텍스트 추가(일반 텍스트 입력)
 - 문자열로 된 텍스트 입력 시 알아서 줄바꿈 처리 등
 - 줄바꿈 처리 간 페이지 변경 시 페이지 추가
 - 테이블 추가
 - 테이블 페이지 변경 시 페이지 추가 후 테이블 계속 생성
 - 에디터기능 — 2차범위
 - html to PDF (pdfBox를 이용하여 가능한지 체크 필요)
 - 이미지 추가(내용에 추가)
 - Header(머릿말)
 - PDF 상단 좌or우측 고정 데이터
 - 생성 이후 모든 페이지에 계속 유지되는 데이터
 - Footer(꼬릿말)
 - PDF 하단 좌or우측 고정 데이터
 - 생성 이후 모든 페이지에 계속 유지되는 데이터
 - PDF Text Line별 정렬 위치 변경
 - Table Cell별 정렬 위치 변경
 - 이미지 추가(PDF 뒤에 갖다붙이기)
 - PDF 합치기
 - 썸네일(첫 화면용) 페이지 추가
 - 이미지 추가
 - Parameter 또는 storage로 부터 다운받은 이미지, PDF등 합쳐서 하나의 PDF 생성



![스크린샷 2022-11-24 11 24 17](https://user-images.githubusercontent.com/41108735/203680165-86ddeb4c-d889-4f07-b43e-f03329c59e43.png)


#사용예제 페이지 넘김등 자동 기능 
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
![스크린샷 2022-11-24 11 28 56](https://user-images.githubusercontent.com/41108735/203680746-d1c0a13f-44f1-4e59-b4c9-4a14a2fff720.png)
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
```
![스크린샷 2022-11-24 11 29 12](https://user-images.githubusercontent.com/41108735/203680781-4a0dc41f-c1db-4e1f-ae9d-9ea78cdb753c.png)
[지출비용_내역서.pdf](https://github.com/GaeTaeng/java_pdf_util_pdfbox/files/10080343/_.82.pdf)

