---
title: sp_statistics (Transact-SQL) | Документация Майкрософт
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_statistics_TSQL
- sp_statistics
dev_langs:
- TSQL
helpviewer_keywords:
- sp_statistics
ms.assetid: 0bb6495f-258a-47ec-9f74-fd16671d23b8
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 3cdde96f57f813dbc25434867ed78ff884c2e7ab
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82820313"
---
# <a name="sp_statistics-transact-sql"></a>sp_statistics (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Возвращает список всех индексов и статистику для указанной таблицы или индексированного представления.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-- Syntax for SQL Server, Azure SQL Database, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
sp_statistics [ @table_name = ] 'table_name'    
     [ , [ @table_owner = ] 'owner' ]   
     [ , [ @table_qualifier = ] 'qualifier' ]   
     [ , [ @index_name = ] 'index_name' ]   
     [ , [ @is_unique = ] 'is_unique' ]  
     [ , [ @accuracy = ] 'accuracy' ]  
```  
  
## <a name="arguments"></a>Аргументы  
`[ @table_name = ] 'table_name'`Указывает таблицу, используемую для возврата сведений о каталоге. Аргумент *table_name* имеет тип **sysname**и не имеет значения по умолчанию. Сопоставление по шаблону не поддерживается.  
  
`[ @table_owner = ] 'owner'`Имя владельца таблицы, используемой для возврата сведений о каталоге. Аргумент *table_owner* имеет тип **sysname**и значение по умолчанию NULL. Сопоставление по шаблону не поддерживается. Если параметр *owner* не указан, применяются правила видимости таблиц по умолчанию базовой СУБД.  
  
 В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], если текущий пользователь является владельцем таблицы с указанным именем, возвращаются индексы таблицы. Если *владелец* не указан и текущий пользователь не владеет таблицей с указанным *именем*, эта процедура ищет таблицу с указанным *именем* , принадлежащую владельцу базы данных. Если владелец существует, возвращаются индексы этой таблицы.  
  
`[ @table_qualifier = ] 'qualifier'`Имя квалификатора таблицы. *квалификатор* имеет тип **sysname**и значение по умолчанию NULL. Различные продукты СУБД поддерживают имена таблиц (_Квалификаторы_**,** состоящие из трех частей). _владелец_**.** _имя_). В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] этот аргумент представляет имя базы данных. В некоторых СУБД он представляет имя сервера в среде базы данных, где находится таблица.  
  
`[ @index_name = ] 'index_name'`Имя индекса. Аргумент *index_name* имеет тип **sysname**и значение по умолчанию%. Поиск совпадений по шаблону поддерживается.  
  
`[ @is_unique = ] 'is_unique'`Указывает, должны ли возвращаться только уникальные индексы (если **Y**). *is_unique* имеет **тип char (1)** и значение по умолчанию **N**.  
  
`[ @accuracy = ] 'accuracy'`Уровень количества элементов и точность страниц для статистики. *точность* имеет **тип char (1)** и значение по умолчанию **Q**. Укажите значение **E** , чтобы обеспечить обновление статистики таким образом, чтобы количество элементов и страниц было точным.  
  
 Значение **E** (SQL_ENSURE) запрашивает драйвер для безусловного получения статистики.  
  
 Значение **Q** (SQL_QUICK) требует, чтобы драйвер получал кратность и страницы только в том случае, если они легко доступны с сервера. В этом случае драйвер не гарантирует актуальность значений. Приложения, написанные в соответствии со стандартом Open Group, всегда получают значение SQL_QUICK из драйверов, совместимых с ODBC 3.x.  
  
## <a name="result-sets"></a>Результирующие наборы  
  
|Имя столбца|Тип данных|Описание|  
|-----------------|---------------|-----------------|  
|**TABLE_QUALIFIER**|**sysname**|Имя квалификатора таблицы. Этот столбец может принимать значение NULL.|  
|**TABLE_OWNER**|**sysname**|Имя владельца таблицы. Этот столбец всегда возвращает значение.|  
|**TABLE_NAME**|**sysname**|Имя таблицы. Этот столбец всегда возвращает значение.|  
|**NON_UNIQUE**|**smallint**|NOT NULL<br /><br /> 0 = уникальное<br /><br /> 1 = неуникальное|  
|**INDEX_QUALIFIER**|**sysname**|Имя владельца индекса. В некоторых СУБД пользователям, не являющимся владельцами таблицы, разрешено создавать индексы. В [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] этот столбец всегда совпадает с **table_name**.|  
|**INDEX_NAME**|**sysname**|Имя индекса. Этот столбец всегда возвращает значение.|  
|**ТИП**|**smallint**|Этот столбец всегда возвращает значение:<br /><br /> 0 = статистика по таблице<br /><br /> 1 = кластеризованный<br /><br /> 2 = хэшированный<br /><br /> 3 = некластеризованный|  
|**SEQ_IN_INDEX**|**smallint**|Позиция столбца в индексе.|  
|**COLUMN_NAME**|**sysname**|Имя столбца для каждого столбца возвращаемого **table_name** . Этот столбец всегда возвращает значение.|  
|**ПАРАМЕТРЫ сортировки**|**char (1)**|Порядок сортировки. Возможны следующие варианты:<br /><br /> A = по возрастанию<br /><br /> D = по убыванию<br /><br /> NULL = неприменимо|  
|**КОЛИЧЕСТВА элементов**|**int**|Число строк в таблице или уникальных значений в индексе.|  
|**СМ**|**int**|Число страниц для хранения индекса или таблицы.|  
|**FILTER_CONDITION**|**varchar (128)**|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не возвращает значение.|  
  
## <a name="return-code-values"></a>Значения кода возврата  
 None  
  
## <a name="remarks"></a>Remarks  
 Индексы в результирующем наборе отображаются в возрастающем порядке по столбцам **NON_UNIQUE**, **Type**, **index_name**и **SEQ_IN_INDEX**.  
  
 Кластеризованный индекс — это индекс, при котором физический порядок хранения данных таблицы соответствует последовательности индекса. Это соответствует [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] кластеризованным индексам.  
  
 Хешированный индекс обеспечивает поиск по полному совпадению или диапазону. Для поиска по шаблону он не используется.  
  
 **sp_statistics** эквивалентен **SQLStatistics** в ODBC. Возвращаемые результаты упорядочиваются по **NON_UNIQUE**, **типу**, **INDEX_QUALIFIER**, **index_name**и **SEQ_IN_INDEX**. Дополнительные сведения см. в [справочнике по API ODBC](https://go.microsoft.com/fwlink/?LinkId=68323).  
  
## <a name="permissions"></a>Разрешения  
 Необходимо разрешение SELECT для схемы.  
  
## <a name="example-sssdwfull-and-sspdw"></a>Пример: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] и[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 В следующем примере возвращаются сведения о `DimEmployee` таблице.  
  
```  
-- Uses AdventureWorks  
  
EXEC sp_statistics DimEmployee;  
```  
  
## <a name="see-also"></a>См. также  
 [Хранимые процедуры каталога &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/catalog-stored-procedures-transact-sql.md)   
 [Системные хранимые процедуры (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  

