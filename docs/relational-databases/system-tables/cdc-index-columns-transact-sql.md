---
title: CDC. index_columns (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- cdc.index_columns_TSQL
- cdc.index_columns
dev_langs:
- TSQL
helpviewer_keywords:
- cdc.index_columns
ms.assetid: 256ec8a5-3031-40a8-9fdb-99db42ea453d
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: c2dac6ec3b2799a4489d660c9467000b27391236
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82833097"
---
# <a name="cdcindex_columns-transact-sql"></a>cdc.index_columns (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Возвращает по одной строке для каждого столбца индекса, связанного с таблицей изменений. Столбцы индекса используются в системе отслеживания измененных данных для уникальной идентификации строк исходной таблицы. По умолчанию столбцы первичного ключа исходной таблицы также включены в индексацию. Однако, если исходной таблице после активации системы отслеживания измененных данных был присвоен уникальный индекс, то вместо столбцов первичного ключа используются столбцы указанного индекса. Первичный ключ или уникальный индекс исходной таблицы используется при отслеживании сетевых изменений. Дополнительные сведения см. в разделе [sys. sp_cdc_enable_table &#40;&#41;Transact-SQL ](../../relational-databases/system-stored-procedures/sys-sp-cdc-enable-table-transact-sql.md).  
  
 Не рекомендуется непосредственно запрашивать системные таблицы. Вместо этого выполните хранимую процедуру [sys. sp_cdc_help_change_data_capture](../../relational-databases/system-stored-procedures/sys-sp-cdc-help-change-data-capture-transact-sql.md) .  

  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|Идентификатор таблицы изменений.|  
|**column_name**|**sysname**|Имя столбца индекса.|  
|**index_ordinal**|**tinyint**|Порядковый номер (нумерация начинается с 1) столбца внутри индекса.|  
|**column_id**|**int**|Идентификатор столбца в исходной таблице.|  
  
## <a name="see-also"></a>См. также  
 [CDC. change_tables &#40;&#41;Transact-SQL](../../relational-databases/system-tables/cdc-change-tables-transact-sql.md)  
  
  
