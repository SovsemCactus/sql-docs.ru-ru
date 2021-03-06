---
title: Межбазовые запросы | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a0305f5b-91bd-4d18-a2fc-ec235b062fd3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b86fb120d8263ae48bb9a4e874e4cf0d012bf7a
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85050209"
---
# <a name="cross-database-queries"></a>Межбазовые запросы
  В [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]транзакции между базами данных не поддерживаются с таблицами, оптимизированными для памяти. Нельзя получить доступ к другой базе данных из той же транзакции или того же запроса, которые также получают доступ к оптимизированной для памяти таблицы. Нельзя скопировать данные из одной таблицы в базе данных в оптимизированную для памяти таблицу в другой базе данных.  
  
 Табличные переменные не является транзакционными. Поэтому табличные переменные, оптимизированные для памяти, можно использовать в запросах между базами данных. Такие переменные упрощают перемещение данных из таблицы в одной базе данных в оптимизированные для памяти таблицы в другой базе данных. Можно использовать две транзакции. В первой транзакции вставьте данные из удаленной таблицы в переменную. Во второй транзакции вставьте данные в локальную оптимизированную для памяти таблицу из переменной.  
  
 Например, чтобы скопировать строку из таблицы T1 в базе данных DB1 в таблицу T2 в DB2, используя переменную @v1 типа dbo. TT1, можно использовать нечто вроде:  
  
```sql  
USE db2   
GO   
DECLARE @v1 dbo.tt1   
INSERT @v1 SELECT * FROM db1.dbo.t1   
INSERT dbo.t2 SELECT * FROM @v1   
GO  
```  
  
## <a name="see-also"></a>См. также:  
 [Миграция в In-Memory OLTP](migrating-to-in-memory-oltp.md)  
  
  
