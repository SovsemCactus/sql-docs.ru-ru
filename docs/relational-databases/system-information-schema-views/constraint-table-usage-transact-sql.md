---
title: CONSTRAINT_TABLE_USAGE (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- CONSTRAINT_TABLE_USAGE_TSQL
- CONSTRAINT_TABLE_USAGE
dev_langs:
- TSQL
helpviewer_keywords:
- CONSTRAINT_TABLE_USAGE view
- INFORMATION_SCHEMA.CONSTRAINT_TABLE_USAGE view
ms.assetid: 5770b696-6c04-4d5c-a8db-9eb92022fa42
author: CarlRabeler
ms.author: carlrab
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 99c4e9f79bb0080c5977be0dff3a4da8757671b6
ms.sourcegitcommit: 4cb53a8072dbd94a83ed8c7409de2fb5e2a1a0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83669519"
---
# <a name="constraint_table_usage-transact-sql"></a>CONSTRAINT_TABLE_USAGE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Возвращает по строке для каждой из таблиц текущей базы данных, в которых определено ограничение. Это представление информационной схемы возвращает сведения об объектах, на которые у текущего пользователя есть разрешения.  
  
 Чтобы получить сведения из этих представлений, укажите полное имя **INFORMATION_SCHEMA.** _view_name_.  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**TABLE_CATALOG**|**nvarchar (** 128 **)**|Квалификатор таблицы.|  
|**TABLE_SCHEMA**|**nvarchar (** 128 **)**|Имя схемы, содержащей таблицу.<br /><br /> **&#42;&#42; важно &#42;&#42;** Не используйте INFORMATION_SCHEMA представления для определения схемы объекта. INFORMATION_SCHEMA представления представляют только подмножество метаданных объекта. Единственный надежный способ найти схему объекта — направить запрос к представлению каталога sys.objects.|  
|**TABLE_NAME**|**sysname**|Имя таблицы.|  
|**CONSTRAINT_CATALOG**|**nvarchar (** 128 **)**|Квалификатор ограничения.|  
|**CONSTRAINT_SCHEMA**|**nvarchar (** 128 **)**|Имя схемы, содержащей ограничение.<br /><br /> **&#42;&#42; важно &#42;&#42;** Не используйте INFORMATION_SCHEMA представления для определения схемы объекта. INFORMATION_SCHEMA представления представляют только подмножество метаданных объекта. Единственный надежный способ найти схему объекта — направить запрос к представлению каталога sys.objects.|  
|**CONSTRAINT_NAME**|**sysname**|Имя ограничения.|  
  
## <a name="see-also"></a>См. также:  
 [Системные представления &#40;&#41;Transact-SQL](https://msdn.microsoft.com/library/35a6161d-7f43-4e00-bcd3-3091f2015e90)   
 [Представления информационной схемы &#40;&#41;Transact-SQL](~/relational-databases/system-information-schema-views/system-information-schema-views-transact-sql.md)   
 [sys. Objects &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)   
 [sys. check_constraints &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-check-constraints-transact-sql.md)   
 [sys. key_constraints &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-key-constraints-transact-sql.md)   
 [sys. foreign_keys &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-foreign-keys-transact-sql.md)  
  
  
