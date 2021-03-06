---
title: FOR XML (SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, about FOR XML clause
- PATH FOR XML mode, construction
- EXPLICIT FOR XML mode
- RAW FOR XML mode
- retrieving XML data
- XML [SQL Server], FOR XML clause
- AUTO FOR XML mode
- XML [SQL Server], construction
ms.assetid: 2b6b5c61-c5bd-49d2-8c0c-b7cf15857906
author: rothja
ms.author: jroth
ms.openlocfilehash: c13c1d4cdf7b1bbc72c956652bb89c2014103d76
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85059463"
---
# <a name="for-xml-sql-server"></a>FOR XML (SQL Server)
  Запрос SELECT возвращает результаты в виде набора строк. При необходимости можно получать результаты SQL-запроса в формате XML. Для этого в запросе необходимо указать предложение FOR XML. Предложение FOR XML может использоваться в запросах верхнего уровня и во вложенных запросах. Предложение FOR XML верхнего уровня можно использовать только в инструкции SELECT. Во вложенных запросах предложение FOR XML можно использовать в инструкциях INSERT, UPDATE и DELETE. Оно также может использоваться в инструкциях присваивания.  
  
 В предложении FOR XML можно указать один из следующих режимов:  
  
-   RAW  
  
-   AUTO  
  
-   EXPLICIT  
  
-   PATH  
  
 Режим RAW создает один \<row> элемент на строку в наборе строк, возвращаемом инструкцией SELECT. XML-иерархию можно создать с помощью написания вложенных запросов FOR XML.  
  
 В режиме AUTO вложенность XML создается эвристически, в зависимости от метода определения инструкции SELECT. Управление формой создаваемой XML структуры минимально. Для создания XML-иерархии, расширяющей возможности XML-структуры, созданной эвристически в режиме AUTO, можно написать вложенные запросы FOR XML.  
  
 Режим EXPLICIT предоставляет больше возможностей по управлению формой XML-структуры. В XML-структуре могут быть использованы смешанные атрибуты и элементы. Это требует особого формата для результирующего набора строк, создаваемого в результате выполнения запроса. Формат этого набора строк затем сопоставляется с формой XML-структуры. Преимущества режима EXPLICIT состоят в возможности использования смешанных атрибутов и элементов, в возможности создания упаковщиков и вложенных составных свойств, создания значений, разделенных пробелами (например, атрибут OrderID может содержать список значений идентификаторов порядка), и смешанного содержимого.  
  
 Однако написание запросов в режиме EXPLICIT может быть очень обременительным. Можно использовать некоторые новые возможности предложения FOR XML, например написание вложенных запросов FOR XML в режиме RAW/AUTO/PATH и директивы TYPE вместо использования режима EXPLICIT для создания иерархий. Вложенные запросы FOR XML могут создавать любую XML структуру, которую можно создать с помощью режима EXPLICIT. Дополнительные сведения см. в статьях [Использование вложенных запросов FOR XML](use-nested-for-xml-queries.md) и [Директива TYPE в запросах FOR XML](type-directive-in-for-xml-queries.md).  
  
 Режим PATH совместно с вложенным запросом FOR XML обеспечивает гибкость режима EXPLICIT более простым образом.  
  
 Эти режимы на самом деле работают только при выполнении запросов, для которых они установлены. Они не влияют на результаты любых последующих запросов.  
  
 Предложение FOR XML недопустимо для выборки с использованием предложений FOR BROWSE.  
  
## <a name="example"></a>Пример  
 Следующая инструкция `SELECT` получает данные из таблиц `Sales.Customer` и `Sales.SalesOrderHeader` базы данных `AdventureWorks2012` . В этом запросе задается режим `AUTO` в предложении `FOR XML` :  
  
```  
USE AdventureWorks2012  
GO  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       OrderHeader.Status  
FROM Sales.Customer Cust   
INNER JOIN Sales.SalesOrderHeader OrderHeader  
ON Cust.CustomerID = OrderHeader.CustomerID  
FOR XML AUTO  
```  
  
## <a name="the-for-xml-clause-and-server-names"></a>Предложение FOR XML и имена сервера  
 Если в инструкции SELECT, использующей предложение FOR XML, указано четырехкомпонентное имя, в возвращаемом документе имя сервера отсутствует, если запрос выполняется на локальном компьютере. Однако имя сервера возвращается как часть имени, если запрос выполняется на сетевом сервере.  
  
 В качестве примера рассмотрим запрос:  
  
```  
SELECT TOP 1 LastName  
FROM ServerName.AdventureWorks2012.Person.Person  
FOR XML AUTO  
```  
  
 Если `ServerName` — локальный сервер, результат запроса будет таким:  
  
```  
<AdventureWorks2012.Person.Person LastName="Achong" />  
```  
  
 Если `ServerName` — сетевой сервер, результат запроса будет таким:  
  
```  
<ServerName.AdventureWorks2012.Person.Person LastName="Achong" />  
```  
  
 Этой возможной неоднозначности можно избежать с помощью такого псевдонима:  
  
```  
SELECT TOP 1 LastName  
FROM ServerName.AdventureWorks2012.Person.Person x  
FOR XML AUTO   
```  
  
 Результат этого запроса будет таким:  
  
```  
<x LastName="Achong"/>  
```  
  
## <a name="see-also"></a>См. также:  
 [Базовый синтаксис предложения FOR XML](basic-syntax-of-the-for-xml-clause.md)   
 [Использование режима RAW с FOR XML](use-raw-mode-with-for-xml.md)   
 [Использование режима AUTO с FOR XML](use-auto-mode-with-for-xml.md)   
 [Использование режима EXPLICIT с FOR XML](use-explicit-mode-with-for-xml.md)   
 [Использование режима PATH с FOR XML](use-path-mode-with-for-xml.md)   
 [SQL Server &#40;OPENXML&#41;](openxml-sql-server.md)   
 [Добавление пространств имен в запросы с WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md)  
  
  
