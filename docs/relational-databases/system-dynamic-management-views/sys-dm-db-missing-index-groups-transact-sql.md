---
title: sys. dm_db_missing_index_groups (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_db_missing_index_groups
- sys.dm_db_missing_index_groups_TSQL
- dm_db_missing_index_groups
- dm_db_missing_index_groups_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_db_missing_index_groups dynamic management view
- missing indexes feature [SQL Server], sys.dm_db_missing_index_groups dynamic management view
ms.assetid: 9cc00acd-d83d-49f8-be72-5b2aebed246b
author: CarlRabeler
ms.author: carlrab
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: c92162cb78043b078e38dac63e22a3ca3267251c
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82828092"
---
# <a name="sysdm_db_missing_index_groups-transact-sql"></a>sys.dm_db_missing_index_groups (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Это динамическое административное представление возвращает сведения о индексах, отсутствующих в определенной группе индекса, за исключением пространственных индексов. 
  
 Динамические административные представления в среде [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] не могут предоставлять информацию, которая может повлиять на автономность базы данных, или информацию о других базах данных, к которым имеет доступ пользователь. Во избежание раскрытия этой информации все строки, содержащие данные, не принадлежащие подключенному клиенту, отфильтровываются.  
   
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**index_group_handle**|**int**|Идентифицирует группу отсутствующих индексов.|  
|**index_handle**|**int**|Идентифицирует отсутствующий индекс, принадлежащий к группе, указанной в столбце **index_group_handle**.<br /><br /> Группа индексов содержит только один индекс.|  
  
## <a name="remarks"></a>Примечания  
 Сведения, возвращаемые представлением **sys.dm_db_missing_index_groups**, обновляются при оптимизации запроса оптимизатором запроса и не сохраняются. Сведения об отсутствующих индексах хранятся только до перезапуска [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Администраторы базы данных должны периодически делать резервные копии сведений об отсутствующих индексах, чтобы сохранить их после перезагрузки сервера.  
  
 Ни один из столбцов выходного результирующего набора не установлен в качестве ключа, но вместе они формируют ключ индекса.  

  >[!NOTE]
  >Результирующий набор для этого динамического административного представления ограничен 600 строк. Каждая строка содержит один отсутствующий индекс. Если у вас больше 600 отсутствующих индексов, следует устранить существующие отсутствующие индексы, чтобы можно было просмотреть новые.
  
## <a name="permissions"></a>Разрешения  
 Для выполнения запроса к этому динамическому административному представлению пользователям должно быть предоставлено разрешение VIEW SERVER STATE или любое другое, подразумевающее разрешение VIEW SERVER STATE.  
  
## <a name="see-also"></a>См. также  
 [sys. dm_db_missing_index_columns &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-missing-index-columns-transact-sql.md)   
 [sys. dm_db_missing_index_details &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-missing-index-details-transact-sql.md)   
 [sys. dm_db_missing_index_group_stats &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-missing-index-group-stats-transact-sql.md)  
  
  
