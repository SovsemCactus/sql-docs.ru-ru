---
title: sys. sp_xtp_checkpoint_force_garbage_collection (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 08/02/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.sp_xtp_checkpoint_force_garbage_collection_TSQL
- sys.sp_xtp_checkpoint_force_garbage_collection
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_xtp_checkpoint_force_garbage_collection
ms.assetid: 82b35b2b-edbd-44ac-9fc8-80695f2fd1df
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 45eb999d6101902ebf9d079235f56d28e343f8e9
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82814496"
---
# <a name="syssp_xtp_checkpoint_force_garbage_collection-transact-sql"></a>sys.sp_xtp_checkpoint_force_garbage_collection (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2014-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2014-xxxx-xxxx-xxx-md.md)]

  Помечает исходные файлы, используемые при выполнении операции слияния, регистрационным номером транзакции в журнале (LSN), после чего файлы больше не требуются и их можно собирать как мусор. Кроме того, перемещает файлы, связанный номер LSN которых меньше точки усечения журнала, в сборку мусора файлового потока.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
 
## <a name="syntax"></a>Синтаксис  
  
```  
sys.sp_xtp_checkpoint_force_garbage_collection [[ @dbname=database_name]  
```  
  
## <a name="arguments"></a>Аргументы  
 *database_name*  
 База данных, в которой будет выполняться сборка мусора. Значение по умолчанию — текущая база данных.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 0 — успешное завершение. Ненулевое значение — ошибка.  
  
## <a name="result-set"></a>Результирующий набор  
 Возвращаемая строка содержит следующие сведения.  
  
|Столбец|Описание|  
|------------|-----------------|  
|num_collected_items|Отображает число файлов, которые были перенесены в сборку мусора файлового потока. Это файлы, номер LSN которых меньше номера LSN точки усечения журнала.|  
|num_marked_for_collection_items|Указывает количество файлов данных и разностных файлов, номер LSN которых был обновлен с использованием blockID журнала с конечным номером LSN журнала.|  
|last_collected_xact_seqno|Возвращает последний соответствующий номер LSN, до которого файлы были перенесены в сборку мусора файлового потока.|  
  
## <a name="permissions"></a>Разрешения  
 Необходимо разрешение владельца базы данных.  
  
## <a name="sample"></a>Образец  
  
```  
exec [sys].[sp_xtp_checkpoint_force_garbage_collection] hkdb1  
```  
  
## <a name="see-also"></a>См. также  
 [Системные хранимые процедуры &#40;&#41;Transact-SQL](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Выполняющаяся в памяти OLTP (оптимизация в памяти)](../../relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
