---
title: Свойства сеанса OLE DB
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- sessions [OLE DB]
- SQL Server Native Client OLE DB provider, sessions
ms.assetid: 2498fbad-b3db-4bea-8fc6-fef5317d3eba
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 799d007dea8063486e836f47032fc3177c890168
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81388599"
---
# <a name="session-properties---sql-server-native-client-ole-db-provider"></a>Свойства сеанса — поставщик OLE DB для SQL Server Native Client
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  Поставщик [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OLE DB собственного клиента интерпретирует свойства OLE DB сеанса следующим образом.  
  
|Идентификатор свойства|Описание|  
|-----------------|-----------------|  
|DBPROP_SESS_AUTOCOMMITISOLEVELS|Поставщик [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] OLE DB собственного клиента поддерживает все уровни изоляции транзакций с автоматической фиксацией за исключением уровня Chaos DBPROPVAL_TI_CHAOS.|  
|||

 В DBPROPSET_SQLSERVERSESSION свойств, зависящих от поставщика, поставщик OLE DB [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] собственного клиента определяет следующее дополнительное свойство сеанса.  
  
|Идентификатор свойства|Описание|  
|-----------------|-----------------|  
|SSPROP_QUOTEDCATALOGNAMES|Тип: VT_BOOL<br /><br /> Чтение и запись в R/W<br /><br /> Значение по умолчанию: VARIANT_FALSE<br /><br /> Описание: заключенные в кавычки идентификаторы допускаются ограничением CATALOG.<br /><br /> VARIANT_TRUE: заключенные в кавычки идентификаторы распознаются ограничением каталога для наборов строк схемы, предоставляющих поддержку распределенных запросов.<br /><br /> VARIANT_FALSE: заключенные в кавычки идентификаторы не распознаются ограничением каталога для наборов строк схемы, предоставляющих поддержку распределенных запросов.<br /><br /> Дополнительные сведения о наборах строк схемы, обеспечивающих поддержку распределенных запросов, см. в статье [Поддержка распределенных запросов в наборах строк схемы](../../relational-databases/native-client/ole-db/schema-rowsets-distributed-query-support.md).|  
|Свойство SSPROP_ALLOWNATIVEVARIANT|Тип: VT_BOOL<br /><br /> Чтение и запись в R/W<br /><br /> Значение по умолчанию: VARIANT_FALSE<br /><br /> Описание: определяет, имеют ли данные, полученные в результате выборки, тип DBTYPE_VARIANT или DBTYPE_SQLVARIANT.<br /><br /> VARIANT_TRUE: возвращается тип столбца DBTYPE_SQLVARIANT. В этом случае в буфере сохраняется структура SSVARIANT.<br /><br /> VARIANT_FALSE: возвращается столбец типа DBTYPE_VARIANT, и в буфере сохраняется структура VARIANT.|  
|SSPROP_ASYNCH_BULKCOPY|Для использования асинхронного режима задайте значение VARIANT_TRUE характерного для поставщика свойства SSPROP_ASYNCH_BULKCOPY сеанса до вызова метода BCPExec. Это свойство доступно в наборе свойств DBPROPSET_SQLSERVERSESSION.|  
|||

## <a name="see-also"></a>См. также:  
 [Объекты источников данных (OLE DB)](../../relational-databases/native-client-ole-db-data-source-objects/data-source-objects-ole-db.md)  
  
  
