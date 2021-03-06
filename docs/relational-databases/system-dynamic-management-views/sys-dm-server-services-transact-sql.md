---
title: sys. dm_server_services (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 01/07/2018
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_server_services
- sys.dm_server_services
- sys.dm_server_services_TSQL
- dm_server_services_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_server_services dynamic management view
ms.assetid: 3f0defd0-478d-4e7f-96be-8795c9de4e3f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ed3638e3c8811235778ab2362700c9e08bf08ca5
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82811462"
---
# <a name="sysdm_server_services-transact-sql"></a>sys.dm_server_services (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Возвращает сведения о SQL Server, полнотекстовом панель запуска SQL Server службе (SQL Server 2017 +) и службах агент SQL Server в текущем экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Это динамическое административное представление позволяет получить сведения о состоянии данных служб.  
  
 
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|servicename|**nvarchar(256)**|Имя [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] службы, полнотекстового или агент SQL Server. Не может иметь значение null.|  
|startup_type|**int**|Показывает режим запуска службы. Ниже приведены возможные значения и соответствующие им описания.<br /><br /> 0: другое<br />1: другое<br />2: автоматически<br />3: вручную<br />4: отключено<br /><br /> Допускает значение NULL.|  
|startup_type_desc|**nvarchar(256)**|Описывает режим запуска службы. Ниже приведены возможные значения и соответствующие им описания.<br /><br /> Другое: другое (загрузочный запуск)<br />Другие: другие (системный запуск)<br />Автоматически: автоматический запуск<br />Вручную: запуск по требованию<br />Отключено: отключено<br /><br /> Не может иметь значение null.|  
|status|**int**|Показывает текущее состояние службы. Ниже приведены возможные значения и соответствующие им описания.<br /><br /> 1: остановлено<br />2: другое (ожидается запуск)<br />3: другое (ожидание ожидания)<br />4: работает<br />5: другое (ожидается продолжение)<br />6: другое (ожидание приостановки)<br />7: приостановлено<br /><br /> Допускает значение NULL.|  
|status_desc|**nvarchar(256)**|Описывает текущее состояние службы. Ниже приведены возможные значения и соответствующие им описания.<br /><br /> Остановлено: служба остановлена.<br />Другое (ожидание операции запуска): служба находится в процессе запуска.<br />Другое (ожидание операции остановки): служба находится в процессе остановки.<br />Работает: служба запущена.<br />Другое (ожидается продолжение операций): служба находится в состоянии ожидания.<br />Другое (ожидание приостановки): служба находится в процессе приостановки.<br />Приостановлено: служба приостановлена.<br /><br /> Не может иметь значение null.|  
|process_id|**int**|Идентификатор процесса службы. Не может иметь значение null.|  
|last_startup_time|**datetimeoffset(7)**|Дата и время последнего запуска службы. Допускает значение NULL.|  
|service_account|**nvarchar(256)**|Учетная запись, имеющая право управлять этой службой. Данная учетная запись может запускать и останавливать службу или изменять ее свойства. Не может иметь значение null.|  
|filename|**nvarchar(256)**|Полный путь и имя исполняемого файла службы. Не может иметь значение null.|  
|is_clustered|**nvarchar (1)**|Указывает, установлена ли служба в качестве ресурса кластеризованного сервера. Не может иметь значение null.|  
|cluster_nodename|**nvarchar(256)**|Имя узла кластера, на котором установлена служба. Допускает значение NULL.|
|instant_file_initialization_enabled|**nvarchar (1)**|Указывает, включена ли Мгновенная инициализация файлов для [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] службы.<br /><br />Y = Мгновенная инициализация файлов включена для службы.<br /><br />N = Мгновенная инициализация файлов отключена для службы.<br /><br /> Допускает значение NULL.<br /><br /> **Примечание.** Не применяется к другим службам, таким как агент SQL Server.<br /><br /> **Применимо к:** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (Начиная с [!INCLUDE[sssql11](../../includes/sssql11-md.md)] SP4 и [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] пакет обновления 1 (SP1) и более поздние версии).|  

## <a name="security"></a>Безопасность  
  
### <a name="permissions"></a>Разрешения  
 Необходимо разрешение `VIEW SERVER STATE` на сервере.  
  
## <a name="see-also"></a>См. также  
 [sys. dm_server_registry &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-server-registry-transact-sql.md)  
  
