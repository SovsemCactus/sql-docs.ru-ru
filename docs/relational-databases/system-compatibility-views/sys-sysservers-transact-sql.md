---
title: sys. sysservers (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.sysservers
- sysservers_TSQL
- sysservers
- sys.sysservers_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysservers system table
- sys.sysservers compatibility view
ms.assetid: d02f186f-c00f-44a6-b38d-dc78a3d2145b
author: rothja
ms.author: jroth
ms.openlocfilehash: 333be9cb6c86c1db3801ac50159610c6d19d1611
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "68941104"
---
# <a name="syssysservers-transact-sql"></a>sys.sysservers (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Содержит одну строку для каждого сервера, к которому экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] может обращаться как к источнику данных OLE DB.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**srvid**|**smallint**|Идентификатор (только для локального использования) удаленного сервера.|  
|**срвстатус**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**срвнаме**|**sysname**|Имя сервера.|  
|**срвпродукт**|**sysname**|Название продукта для удаленного сервера.|  
|**ProviderName**|**nvarchar(128)**|Имя поставщика OLE DB для доступа к этому серверу.|  
|**DataSource**|**nvarchar(4000)**|Значение источника данных OLE DB.|  
|**расположение**|**nvarchar(4000)**|Местоположение OLE DB.|  
|**провидерстринг**|**nvarchar(4000)**|Строка поставщика OLE DB.|  
|**schemadate**|**datetime**|Дата последнего обновления этой строки.|  
|**topologyx**|**int**|Не используется.|  
|**topologyy**|**int**|Не используется.|  
|**каталога**|**sysname**|Каталог, который используется при соединении с поставщиком OLE DB.|  
|**srvcollation**|**sysname**|Параметры сортировки сервера.|  
|**connecttimeout**|**int**|Время ожидания соединения с сервером.|  
|**QueryTimeout**|**int**|Время ожидания выполнения запросов на сервере.|  
|**srvnetname**|**char (30)**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**isremote**|**bit**|1 = удаленный сервер.<br /><br /> 0 = связанный сервер.|  
|**удаленного**|**bit**|1 = **sp_serveroption\@RPC** имеет значение **true** или **On**.<br /><br /> 0 = **sp_serveroption\@** параметру RPC присвоено значение **false** или **Off**.|  
|**pub**|**bit**|1 = **sp_serveroption\@Pub** имеет значение **true** или **On**.<br /><br /> 0 = **sp_serveroption\@параметр pub** **имеет значение false** или **Off**.|  
|**Директор**|**bit**|1 = **sp_serveroption\@** **имеет значение true** или **On**.<br /><br /> 0 = **sp_serveroption\@** значение **false** или **Off**.|  
|**dist**|**bit**|1 = **sp_serveroption\@расп** имеет значение **true** или **On**.<br /><br /> 0 = **sp_serveroption\@расп** имеет значение **false** или **Off**.|  
|**dpub**|**bit**|1 = **sp_serveroption\@дпуб** имеет значение **true** или **On**.<br /><br /> 0 = **sp_serveroption\@дпуб** имеет значение **false** или **Off**.|  
|**rpcout**|**bit**|1 = **sp_serveroption\@RPC out** имеет значение **true** или **On**.<br /><br /> 0 = **sp_serveroption\@RPC out** установлено в **значение false** или **Off**.|  
|**DataAccess**|**bit**|1 = **sp_serveroption\@доступ к данным** имеет значение **true** или **On**.<br /><br /> 0 = **sp_serveroption\@доступ к данным** имеет значение **false** или **Off**.|  
|**collationcompatible**|**bit**|1 = **Параметры\@сортировки, совместимые с sp_serveroption** , имеют значение **true** или **On**.<br /><br /> 0 = **Параметры\@сортировки, совместимые с sp_serveroption** , имеют значение **false** или **Off**.|  
|**система**|**bit**|1 = **sp_serveroption\@система** имеет значение **true** или **On**.<br /><br /> 0 = **sp_serveroption\@система** имеет значение **false** или **Off**.|  
|**useremotecollation**|**bit**|1 = **sp_serveroption\@параметру remote collation** задано **значение true** или **On**.<br /><br /> 0 = **sp_serveroption\@параметрам удаленных параметров сортировки** присвоено **значение false** или **Off**.|  
|**lazyschemavalidation**|**bit**|1 = **sp_serveroption\@для отложенной проверки схемы** задано значение **true** или **On**.<br /><br /> 0 = **sp_serveroption\@для отложенной проверки схемы** задано значение **false** или **Off**.|  
|**параметры сортировки**|**sysname**|Параметры сортировки сервера задаются **sp_serveroption\@именем параметров сортировки**.|  
|**nonsqlsub**|bit|0 = сервер является экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<br /><br /> 1= сервер не является экземпляром [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
  
## <a name="see-also"></a>См. также:  
 [Сопоставление системных таблиц с системными представлениями &#40;&#41;Transact-SQL](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Представления совместимости (Transact-SQL)](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
