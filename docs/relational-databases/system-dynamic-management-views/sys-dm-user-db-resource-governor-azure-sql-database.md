---
title: sys. dm_user_db_resource_governance (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/17/2019
ms.prod: sql
ms.prod_service: sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.resource_governance
- sys.resource_governance_TSQL
- resource_governance
- resource_governance_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.resource_governance catalog view
ms.assetid: ''
author: joesackmsft
ms.author: josack
monikerRange: =azuresqldb-current||=sqlallproducts-allversions
ms.openlocfilehash: f853f1778a62b345accff745aade5fb5608322fd
ms.sourcegitcommit: 1be90e93980a8e92275b5cc072b12b9e68a3bb9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84627403"
---
# <a name="sysdm_user_db_resource_governance-transact-sql"></a>sys. dm_user_db_resource_governance (Transact-SQL)

[!INCLUDE[appliesto-xx-asdb-xxxx-xxx-md](../../includes/appliesto-xx-asdb-xxxx-xxx-md.md)]

Возвращает фактические параметры конфигурации и емкости, используемые механизмами управления ресурсами в текущей базе данных или эластичном пуле.
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**database_id**|INT|Идентификатор базы данных, уникальный на сервере базы данных SQL Azure.|
|**logical_database_guid**|UNIQUEIDENTIFIER|Логический идентификатор GUID для пользовательской базы данных, который остается в течение жизненного цикла пользовательской базы данных.  Переименование базы данных или изменение ее цели уровня обслуживания не приведет к изменению этого значения.|
|**physical_database_guid**|UNIQUEIDENTIFIER|Физический идентификатор GUID для пользовательской базы данных, который остается в течение всего времени существования физического экземпляра пользовательской базы данных. Изменение цели уровня обслуживания базы данных приведет к изменению этого значения.|
|**server_name**|nvarchar|Имя логического сервера.|
|**database_name**|nvarchar|Имя логической базы данных.|
|**slo_name**|nvarchar|Цель уровня обслуживания, включая создание оборудования.|
|**dtu_limit**|INT|Предел DTU базы данных (NULL для Виртуальное ядро).|
|**cpu_limit**|INT|Виртуальное ядро ограничение базы данных (значение NULL для баз данных DTU).|
|**min_cpu**|tinyint|Значение MIN_CPU_PERCENT пула ресурсов рабочей нагрузки пользователя. См. раздел [Основные понятия пула ресурсов](https://docs.microsoft.com/sql/relational-databases/resource-governor/resource-governor-resource-pool?#resource-pool-concepts).|
|**max_cpu**|tinyint|Значение MAX_CPU_PERCENT пула ресурсов рабочей нагрузки пользователя. См. раздел [Основные понятия пула ресурсов](https://docs.microsoft.com/sql/relational-databases/resource-governor/resource-governor-resource-pool?#resource-pool-concepts).|
|**cap_cpu**|tinyint|Значение CAP_CPU_PERCENT пула ресурсов рабочей нагрузки пользователя. См. раздел [Основные понятия пула ресурсов](https://docs.microsoft.com/sql/relational-databases/resource-governor/resource-governor-resource-pool?#resource-pool-concepts).|
|**min_cores**|smallint|Только для внутреннего применения.|
|**max_dop**|smallint|Значение MAX_DOP для группы рабочей нагрузки пользователя. См. раздел [Создание группы рабочей нагрузки](https://docs.microsoft.com/sql/t-sql/statements/create-workload-group-transact-sql).|
|**min_memory**|INT|Значение MIN_MEMORY_PERCENT пула ресурсов рабочей нагрузки пользователя. См. раздел [Основные понятия пула ресурсов](https://docs.microsoft.com/sql/relational-databases/resource-governor/resource-governor-resource-pool?#resource-pool-concepts).|
|**max_memory**|INT|Значение MAX_MEMORY_PERCENT пула ресурсов рабочей нагрузки пользователя. См. раздел [Основные понятия пула ресурсов](https://docs.microsoft.com/sql/relational-databases/resource-governor/resource-governor-resource-pool?#resource-pool-concepts).|
|**max_sessions**|INT|Максимальное число сеансов, разрешенное в группе рабочей нагрузки пользователя.|
|**max_memory_grant**|INT|Значение REQUEST_MAX_MEMORY_GRANT_PERCENT для группы рабочей нагрузки пользователя. См. раздел [Создание группы рабочей нагрузки](https://docs.microsoft.com/sql/t-sql/statements/create-workload-group-transact-sql).|
|**max_db_memory**|INT|Только для внутреннего применения.|
|**govern_background_io**|bit|Только для внутреннего применения.|
|**min_db_max_size_in_mb**|BIGINT|Минимальное max_size значение для файла данных в МБ. См. раздел [sys. database_files](https://docs.microsoft.com/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql).|
|**max_db_max_size_in_mb**|BIGINT|Максимальное max_size значение для файла данных в МБ. См. раздел [sys. database_files](https://docs.microsoft.com/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql).|
|**default_db_max_size_in_mb**|BIGINT|Значение max_size по умолчанию для файла данных в МБ. См. раздел [sys. database_files](https://docs.microsoft.com/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql).|
|**db_file_growth_in_mb**|BIGINT|Шаг роста по умолчанию для файла данных в МБ. См. раздел [sys. database_files](https://docs.microsoft.com/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql).|
|**initial_db_file_size_in_mb**|BIGINT|Размер по умолчанию для нового файла данных в МБ. См. раздел [sys. database_files](https://docs.microsoft.com/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql).|
|**log_size_in_mb**|BIGINT|Размер по умолчанию для нового файла журнала в МБ. См. раздел [sys. database_files](https://docs.microsoft.com/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql).|
|**instance_cap_cpu**|INT|Только для внутреннего применения.|
|**instance_max_log_rate**|BIGINT|Ограничение скорости создания журнала для экземпляра SQL Server, в байтах в секунду. Применяется ко всему журналу, созданному экземпляром, включая `tempdb` и другие системные базы данных. В эластичном пуле применяется к журналу, созданному всеми базами данных в пуле.|
|**instance_max_worker_threads**|INT|Ограничение рабочего потока для экземпляра SQL Server.|
|**replica_type**|INT|Тип реплики, где 0 — первичный, а 1 — вторичный.|
|**max_transaction_size**|BIGINT|Максимальное пространство журнала, используемое любой транзакцией, в КБ.|
|**checkpoint_rate_mbps**|INT|Только для внутреннего применения.|
|**checkpoint_rate_io**|INT|Только для внутреннего применения.|
|**last_updated_date_utc**|DATETIME|Дата и время последнего изменения параметра или его перенастройки в формате UTC.|
|**primary_group_id**|INT|Идентификатор группы рабочей нагрузки для пользовательской рабочей нагрузки на первичной реплике и во вторичных репликах.|
|**primary_group_max_workers**|INT|Ограничение рабочего потока для группы рабочей нагрузки пользователя.|
|**primary_min_log_rate**|BIGINT|Минимальная частота журнала в байтах в секунду на уровне группы рабочей нагрузки пользователя. Управление ресурсами не будет пытаться сократить частоту ведения журнала ниже этого значения.|
|**primary_max_log_rate**|BIGINT|Максимальная скорость журнала (в байтах в секунду) на уровне группы рабочей нагрузки пользователя. В управлении ресурсами не будет разрешена скорость ведения журнала выше этого значения.|
|**primary_group_min_io**|INT|Минимальное число операций ввода-вывода для группы рабочей нагрузки пользователя. Управление ресурсами не будет пытаться сократить количество операций ввода-вывода ниже этого значения.|
|**primary_group_max_io**|INT|Максимальное число операций ввода-вывода в секунду для группы рабочей нагрузки пользователя. Управление ресурсами не позволит выполнять операции ввода-вывода выше этого значения.|
|**primary_group_min_cpu**|FLOAT|Минимальный процент использования ЦП для уровня группы рабочей нагрузки пользователя. Управление ресурсами не будет пытаться уменьшить загрузку ЦП ниже этого значения.|
|**primary_group_max_cpu**|FLOAT|Максимальный процент использования ЦП для уровня группы рабочей нагрузки пользователя. Управление ресурсами не разрешит использование ЦП выше этого значения.|
|**primary_log_commit_fee**|INT|Тариф на фиксацию контроля частоты журналов для группы рабочей нагрузки пользователя в байтах. Плата за фиксацию увеличивает размер каждой операции ввода-вывода журнала на фиксированное значение только в целях учета скорости журнала. Фактические операции ввода-вывода журнала в хранилище не увеличиваются.|
|**primary_pool_max_workers**|INT|Ограничение рабочего потока для пула ресурсов рабочей нагрузки пользователя.|
|**pool_max_io**|INT|Максимальный предел операций ввода-вывода в секунду для пула ресурсов рабочей нагрузки пользователя.|
|**govern_db_memory_in_resource_pool**|bit|Только для внутреннего применения.|
|**volume_local_iops**|INT|Только для внутреннего применения.|
|**volume_managed_xstore_iops**|INT|Только для внутреннего применения.|
|**volume_external_xstore_iops**|INT|Только для внутреннего применения.|
|**volume_type_local_iops**|INT|Только для внутреннего применения.|
|**volume_type_managed_xstore_iops**|INT|Только для внутреннего применения.|
|**volume_type_external_xstore_iops**|INT|Только для внутреннего применения.|
|**volume_pfs_iops**|INT|Только для внутреннего применения.|
|**volume_type_pfs_iops**|INT|Только для внутреннего применения.|
|||

## <a name="permissions"></a>Разрешения

Для этого представления необходимо разрешение VIEW DATABASE STATE.

## <a name="remarks"></a>Комментарии

Описание руководства по управлению ресурсами в базе данных SQL Azure см. в разделе [ограничения ресурсов базы данных SQL](https://docs.microsoft.com/azure/sql-database/sql-database-resource-limits-database-server).

> [!IMPORTANT]
> Большая часть данных, возвращаемых этим DMV, предназначена для внутреннего использования и может быть изменена в любое время.

## <a name="examples"></a>Примеры

Следующий запрос, выполняемый в контексте пользовательской базы данных, возвращает максимальную скорость ведения журнала и максимальное число операций ввода-вывода для группы рабочей нагрузки пользователя и уровня пула ресурсов. Для одной базы данных возвращается одна строка. Для базы данных в пуле эластичных БД возвращается строка для каждой базы данных в пуле.

```
SELECT database_name,
       primary_group_id,
       primary_max_log_rate,
       primary_group_max_io,
       pool_max_io
FROM sys.dm_user_db_resource_governance
ORDER BY database_name;  
```

## <a name="see-also"></a>См. также:

- [Регулятор ресурсов](https://docs.microsoft.com/sql/relational-databases/resource-governor/resource-governor)
- [sys.dm_resource_governor_resource_pools (Transact-SQL)](https://docs.microsoft.com/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql)
- [sys.dm_resource_governor_workload_groups (Transact-SQL)](https://docs.microsoft.com/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-transact-sql)
- [sys. dm_resource_governor_resource_pools_history_ex (Transact-SQL)](https://docs.microsoft.com/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-history-ex-azure-sql-database)
- [sys.dm_resource_governor_workload_groups_history_ex (база данных SQL Azure)](https://docs.microsoft.com/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-workload-groups-history-ex-azure-sql-database)
- [Управление частотой ведения журнала транзакций](https://docs.microsoft.com/azure/sql-database/sql-database-resource-limits-database-server#transaction-log-rate-governance)
- [Ограничения ресурсов на основе DTU для отдельной базы данных](https://docs.microsoft.com/azure/sql-database/sql-database-dtu-resource-limits-single-databases)
- [Ограничения ресурсов виртуального ядра для отдельной базы данных](https://docs.microsoft.com/azure/sql-database/sql-database-vcore-resource-limits-single-databases)
