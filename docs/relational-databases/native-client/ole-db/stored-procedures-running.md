---
title: Выполнение хранимых процедур (OLE DB) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- stored procedures [OLE DB], executing
- OLE DB, stored procedures
- SQL Server Native Client OLE DB provider, stored procedures
ms.assetid: c77d9be9-2176-4438-8c7a-04b63ebece08
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 3f01c5e43d7d451cbcdca30dd66cf2ca70227541
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81305353"
---
# <a name="stored-procedures---running"></a>Выполнение хранимых процедур
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  При выполнении инструкций вызов хранимой процедуры в источнике данных (вместо выполнения или подготовки инструкции непосредственно в клиентском приложении) может обеспечить следующее:  
  
-   высокую производительность;  
  
-   низкие издержки сети;  
  
-   лучшую согласованность;  
  
-   большую точность;  
  
-   дополнительные возможности.  
  
 Поставщик [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB собственного клиента поддерживает три механизма, с помощью которых [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] хранимые процедуры возвращают данные:  
  
-   Каждая инструкция SELECT в хранимой процедуре формирует результирующий набор.  
  
-   Процедура может возвращать данные через выходные параметры.  
  
-   Процедура может иметь целочисленный код возврата.  
  
 Приложение должно быть способно обработать все эти данные, возвращаемые хранимыми процедурами.  
  
 Разные поставщики OLE DB возвращают выходные параметры и значения на разных этапах во время обработки результатов. В случае с [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] поставщиком собственного клиента OLE DB выходные параметры и коды возврата не предоставляются до тех пор, пока потребитель не извлек или не отменил результирующие наборы, возвращенные хранимой процедурой. Коды возврата и выходные параметры возвращаются сервером в последнем пакете потока табличных данных.  
  
 Поставщики используют свойство DBPROP_OUTPUTPARAMETERAVAILABILITY для сообщения о возвращении выходных параметров и возвращаемых значений. Это свойство доступно в наборе свойств DBPROPSET_DATASOURCEINFO.  
  
 Поставщик [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB собственного клиента задает для свойства DBPROP_OUTPUTPARAMETERAVAILABILITY значение DBPROPVAL_OA_ATROWRELEASE, чтобы указать, что коды возврата и выходные параметры не возвращаются до тех пор, пока результирующий набор не будет обработан или освобожден.  
  
## <a name="see-also"></a>См. также:  
 [Хранимые процедуры](../../../relational-databases/native-client/ole-db/stored-procedures.md)  
  
  
