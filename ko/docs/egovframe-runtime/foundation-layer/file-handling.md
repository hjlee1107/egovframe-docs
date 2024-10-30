---
linkTitle: "File Handling"
weight: 31
title: File Handling
description: Excel 다운로드를 위한 파일 처리 서비스를 적용한 예제 코드와 설정을 제공한다.
---
# File Handling

## 개요

[File Handling Service](./file-handling.md) 를 적용해서 Excel 다운로드 하기 위한 Excel 정보를 설정한다.

[Excel](./excel-service.md) Service에 적용되어 있다.

## 설명

### Source

```java
FileObject writtenFile = manager.resolveFile(baseDir, this.propertyPath);
FileContent writtenContents = writtenFile.getContent();
InputStream is = writtenContents.getInputStream();
 
BufferedReader reader = new BufferedReader(new InputStreamReader(is));
StringBuffer sb = new StringBuffer();
 
for (String line = ""; (line = reader.readLine()) != null; sb.append(line));
is.close();
```