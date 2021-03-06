---
title: syscollector_execution_stats (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- syscollector_execution_stats
- syscollector_execution_stats_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- syscollector_execution_stats view
- data collector view
ms.assetid: 23e35ac5-fbbf-4922-970c-f4fac44c1263
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d4ab4827ab9d9a86936a8562b0e4765b492acd15
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82824914"
---
# <a name="syscollector_execution_stats-transact-sql"></a>syscollector_execution_stats (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Отображает сведения о ходе выполнения задачи для набора элементов сбора или пакета.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**log_id**|**bigint**|Определяет выполнение каждого набора элементов сбора. Используется для соединения этого представления с другими подробными журналами. Не допускает значение NULL.|  
|**task_name**|**nvarchar(128)**|Имя набора сбора или задачи пакета, для которого производится отображение текущей информации. Не допускает значение NULL.|  
|**execution_row_count_in**|**int**|Количество обработанных строк на момент запуска потока данных. Допускает значение NULL.|  
|**execution_row_count_out**|**int**|Количество обработанных строк на момент окончания потока данных. Допускает значение NULL.|  
|**execution_row_count_errors**|**int**|Количество строк с ошибками, обработанных в потоке данных. Допускает значение NULL.|  
|**execution_time_ms**|**int**|Время, требуемое для завершения задачи, в миллисекундах. Допускает значение NULL.|  
|**log_time**|**datetime**|Время занесения данной информации в журнал. Не допускает значение NULL.|  
  
## <a name="permissions"></a>Разрешения  
 Требуется разрешение SELECT для **dc_operator**.  
  
## <a name="see-also"></a>См. также  
 [Хранимые процедуры сборщика данных &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)   
 [Представления сборщика данных &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/data-collector-views-transact-sql.md)   
 [Сбор данных](../../relational-databases/data-collection/data-collection.md)  
  
  
