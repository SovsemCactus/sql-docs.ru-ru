---
title: sp_replcounters (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_replcounters
- sp_replcounters_TSQL
helpviewer_keywords:
- sp_replcounters
ms.assetid: fe585b1f-edda-421f-81d6-8a03a3a535d2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 859e214a0caccc9e515a5377d707aeb3d29c69da
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82833134"
---
# <a name="sp_replcounters-transact-sql"></a>sp_replcounters (Transact-SQL)
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

  Возвращает статистику по репликации, касающуюся задержек, пропускной способности и числа транзакций для каждой опубликованной базы данных. Эта хранимая процедура выполняется на подписчике в любой базе данных.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_replcounters  
  
```  
  
## <a name="result-sets"></a>Результирующие наборы  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**База данных**|**sysname**|Имя базы данных.|  
|**Replicated transactions**|**int**|Количество транзакций в журнале, ожидающих доставки в базу данных распространителя|  
|**Replication rate trans/sec**|**float**|Среднее количество транзакций, переданных в базу данных распространителя в секунду.|  
|**Задержка репликации**|**float**|Среднее время в секундах, в течение которого транзакции находились в журнале и до того момента, как они были отправлены.|  
|**Replbeginlsn**|**binary(10)**|Указывает регистрационный номер транзакции в журнале (LSN) для текущей точки усечения журнала.|  
|**Replnextlsn**|**binary(10)**|Номер LSN следующей записи фиксации, ожидающей доставки в базу данных распространителя.|  
  
## <a name="remarks"></a>Remarks  
 **sp_replcounters** используется в репликации транзакций.  
  
## <a name="permissions"></a>Разрешения  
 Требуется членство в предопределенной роли базы данных **db_owner** или предопределенной роли сервера **sysadmin** .  
  
## <a name="see-also"></a>См. также  
 [sp_replcmds &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-replcmds-transact-sql.md)   
 [sp_repldone &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-repldone-transact-sql.md)   
 [sp_replflush &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-replflush-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
