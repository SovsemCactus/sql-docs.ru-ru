---
title: sys. traces (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- traces
- sys.traces_TSQL
- sys.traces
- traces_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.traces catalog view
ms.assetid: 4a03be22-b7da-4e2a-97ff-94bed890a620
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 1a135dfd0f633858d828a476899094cb2f0409ed
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82821221"
---
# <a name="systraces-transact-sql"></a>sys.traces (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Представление каталога **sys. traces** содержит текущие выполняемые трассировки в системе. Это представление предназначено для замены функции **fn_trace_getinfo** .  
  
 Полный список поддерживаемых событий трассировки см. в разделе [Справочник по классам событий SQL Server](../../relational-databases/event-classes/sql-server-event-class-reference.md).  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] Вместо этого используйте представления каталога расширенных событий.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**идентификатор**|**int**|Идентификатор трассировки.|  
|**status**|**int**|Состояние трассировки:<br /><br /> 0 = остановлена<br /><br /> 1 = работает|  
|**path**|**nvarchar(260)**|Путь к файлу трассировки. Значение NULL, если трассировка является трассировкой наборов строк.|  
|**max_size**|**bigint**|Верхний предел размера файла трассировки в мегабайтах (МБ). Значение NULL, если трассировка является трассировкой наборов строк.|  
|**stop_time**|**datetime**|Время окончания выполняющейся трассировки.|  
|**max_files**|**int**|Максимальное количество файлов продолжения. Значение NULL, если максимальное количество файлов не установлено.|  
|**is_rowset**|**bit**|1 = трассировка набора строк.|  
|**is_rollover**|**bit**|1 = параметр продолжения включен.|  
|**is_shutdown**|**bit**|1 = параметр завершения включен.|  
|**is_default**|**bit**|1 = трассировка по умолчанию.|  
|**buffer_count**|**int**|Количество внутренних буферов памяти, используемых трассировкой.|  
|**buffer_size**|**int**|Размер каждого буфера (КБ).|  
|**file_position**|**bigint**|Положение последнего файла трассировки. Значение NULL, если трассировка является трассировкой наборов строк.|  
|**reader_spid**|**int**|Идентификатор сеанса чтения трассировки набора строк. Значение NULL, если трассировка является трассировкой файлов.|  
|**start_time**|**datetime**|Время начала трассировки.|  
|**last_event_time**|**datetime**|Время срабатывания последнего события.|  
|**event_count**|**bigint**|Общее количество произошедших событий.|  
|**dropped_event_count**|**int**|Общее количество удаленных событий.|  
  
## <a name="permissions"></a>Разрешения  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>См. также  
 [Представления каталога объектов &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [sys. trace_categories &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-categories-transact-sql.md)   
 [sys. trace_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-columns-transact-sql.md)   
 [sys. trace_events &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-events-transact-sql.md)   
 [sys. trace_event_bindings &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-event-bindings-transact-sql.md)   
 [sys. trace_subclass_values &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-trace-subclass-values-transact-sql.md)  
  
  
