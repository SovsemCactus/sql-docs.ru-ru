---
title: Коды возврата | Документация Майкрософт
description: Коды возврата
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- OLE DB error handling, return codes
- OLE DB Driver for SQL Server, errors
- failed function [OLE DB]
- successful function [OLE DB]
- S_FALSE
- IS_ERROR macro
- DB_S_ERRORSOCCURRED return
- return codes [OLE DB]
- S_OK
- FAILED macro
- errors [OLE DB], return codes
author: pmasl
ms.author: pelopes
ms.openlocfilehash: a1deedd8903f69268ebc5e7f5caafaa79a7f7b18
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2020
ms.locfileid: "67994923"
---
# <a name="return-codes"></a>Коды возврата
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  Для краткости можно сказать, что вызов функции-члена класса или структуры завершается успешно либо с ошибкой. Точнее сказать, вызов функции может оказаться успешным, но результат оказывается не таким, на какой рассчитывал разработчик приложения.  
  
 Дополнительные сведения о кодах возврата OLE DB см. в статье [Коды возврата (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).  
  
 Если функция-член OLE DB Driver for SQL Server возвращает S_OK, значит выполнение функции завершилось успешно.  
  
 Если функция-член драйвера OLE DB для SQL Server возвращает не S_OK, с помощью макросов OLE/COM FAILED и IS_ERROR можно получить из возвращенного функцией значения HRESULT информацию об успешном или неуспешном выполнении функции.  
  
 Если макрос FAILED или IS_ERROR вернул значение TRUE, это служит сигналом для драйвера OLE DB для SQL Server, что выполнение функции было неуспешным. Если FAILED или IS_ERROR имеет значение FALSE, а HRESULT не равно S_OK, значит OLE DB Driver for SQL Server извещает потребителя о частично успешном выполнении функции. Потребитель может получить подробные сведения об этом "успехе с оговорками" через интерфейсы для работы с ошибками, предоставляемые драйвером OLE DB для SQL Server. Через эти же интерфейсы драйвера OLE DB для SQL Server можно получить подробные сведения в случае, когда вызов функции был явно неудачным (макрос FAILED возвращает значение TRUE).  
  
 Среди разных вариантов "успеха с оговорками" потребители OLE DB Driver for SQL Server чаще всего получают в параметре HRESULT значение DB_S_ERRORSOCCURRED. Функции-члены, возвращающие значение DB_S_ERRORSOCCURRED, обычно определяют один или несколько параметров, предоставляющих потребителю значения состояния. Информация, возвращаемая через параметры состояния, может быть единственной информацией о состоянии, доступной потребителю; поэтому для получения значений состояния, когда они доступны, потребители должны реализовать собственную логику приложения.  
  
 Функции-члены OLE DB Driver for SQL Server не возвращают код успеха S_FALSE. Все функции-члены OLE DB Driver for SQL Server обозначают успешное выполнение только кодом успеха S_OK.  
  
## <a name="see-also"></a>См. также:  
 [ошибки](../../oledb/ole-db-errors/errors.md)  
  
  
