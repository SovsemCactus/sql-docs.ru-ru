---
title: Столбцы без имени | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- names [SQL Server], columns without
ms.assetid: 440de44e-3a56-4531-b4e4-1533ca933cac
author: rothja
ms.author: jroth
ms.openlocfilehash: c295a0795e8c073ae55fcb61457782496a91526f
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85046943"
---
# <a name="columns-without-a-name"></a>Столбцы без имени
  Любой столбец, не имеющий имени, будет встроенным. Например, вычисляемые столбцы или вложенные скалярные запросы, в которых не задан псевдоним столбца, формируют столбцы без имени. Если столбец имеет тип данных `xml`, в него помещается содержимое экземпляра этого типа данных. В противном случае содержимое столбца вставляется как текстовый узел.  
  
```  
SELECT 2+2  
FOR XML PATH  
```  
  
 Создание этого XML. По умолчанию для каждой строки в наборе строк в итоговом XML-документе формируется элемент <`row`>. То же самое происходит в режиме RAW.  
  
 `<row>4</row>`  
  
 Следующий запрос возвращает набор строк с тремя столбцами. Третий столбец, без названия, содержит XML-данные. Режим PATH вставляет экземпляр типа xml.  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ;  
GO  
```  
  
 Частичный результат:  
  
 `<row>`  
  
 `<ProductModelID>7</ProductModelID>`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<MI:Location ...LocationID="10" ...></MI:Location>`  
  
 `<MI:Location ...LocationID="20" ...></MI:Location>`  
  
 `...`  
  
 `</row>`  
  
## <a name="see-also"></a>См. также:  
 [Использование режима PATH совместно с FOR XML](use-path-mode-with-for-xml.md)  
  
  
