---
title: sp_helpfile (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_helpfile
- sp_helpfile_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_helpfile
ms.assetid: 1546e0ae-5a99-4e01-9eb9-d147fa65884c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 812be95c9584e75d8452c946d1935625468a79a1
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82828340"
---
# <a name="sp_helpfile-transact-sql"></a>sp_helpfile (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Возвращает физические имена и атрибуты файлов, связанных с текущей базой данных. Используйте эту хранимую процедуру для определения имен файлов, чтобы присоединять или отсоединять их от сервера.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
sp_helpfile [ [ @filename= ] 'name' ]  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @filename = ] 'name'`Логическое имя любого файла в текущей базе данных. Аргумент *Name* имеет тип **sysname**и значение по умолчанию NULL. Если параметр *Name* не указан, возвращаются атрибуты всех файлов в текущей базе данных.  
  
## <a name="return-code-values"></a>Значения кода возврата  
 0 (успешное завершение) или 1 (неуспешное завершение)  
  
## <a name="result-sets"></a>Результирующие наборы  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|Логическое имя файла.|  
|**ИД**|**smallint**|Числовой идентификатор файла. Не возвращается, если указано *имя* *.*|  
|**файлов**|**nchar (260)**|Физическое имя файла.|  
|**filegroup**|**sysname**|Файловая группа, к которой принадлежит файл.<br /><br /> NULL = файл является файлом журнала. Такой файл никогда не является частью файловой группы.|  
|**size**|**nvarchar (15)**|Размер файла в килобайтах.|  
|**MAXSIZE**|**nvarchar (15)**|Определяет максимальный размер, до которого может вырасти файл. Значение UNLIMITED в этом поле означает, что файл может расти, пока диск не будет заполнен.|  
|**growth**|**nvarchar (15)**|Значение прироста размера файла. Оно указывает объем пространства, добавляемого к файлу каждый раз, когда требуется новое пространство.<br /><br /> 0 = файл имеет фиксированный размер и не может расти.|  
|**Загрузка**|**varchar (9)**|Для файла данных значением является **"только данные"** , а для файла журнала — **"только журнал"**.|  
  
## <a name="permissions"></a>Разрешения  
 Необходимо быть членом роли **public**.  
  
## <a name="examples"></a>Примеры  
 Следующий пример возвращает данные о файлах в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_helpfile;  
GO  
```  
  
## <a name="see-also"></a>См. также  
 [Ядро СУБД хранимых процедур &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [sp_helpfilegroup &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-helpfilegroup-transact-sql.md)   
 [sys. database_files &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-database-files-transact-sql.md)   
 [sys. master_files &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-master-files-transact-sql.md)   
 [sys. FILEGROUP &#40;&#41;Transact-SQL](../../relational-databases/system-catalog-views/sys-filegroups-transact-sql.md)   
 [Системные хранимые процедуры &#40;&#41;Transact-SQL](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Файлы и файловые группы базы данных](../../relational-databases/databases/database-files-and-filegroups.md)  
  
  
