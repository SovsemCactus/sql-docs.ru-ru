---
title: ROWCOUNT_BIG (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 03/13/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- ROWCOUNT_BIG
- ROWCOUNT_BIG_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- ROWCOUNT_BIG function
- number of rows affected by statement
- row affected by statements [SQL Server]
- statements [SQL Server], last statement
- counting rows
ms.assetid: 6e18a0eb-bb36-4348-90d9-8b1ecf095064
author: julieMSFT
ms.author: jrasnick
ms.openlocfilehash: e1ccc5aa9619c96fd75400531041442138e0b4f3
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82828644"
---
# <a name="rowcount_big-transact-sql"></a>ROWCOUNT_BIG (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Возвращает число строк, затронутых при выполнении последней инструкции. Эта функция работает подобно [@@ROWCOUNT](../../t-sql/functions/rowcount-transact-sql.md) за исключением того, что она возвращает значение типа **bigint**.  
  
 ![Значок ссылки на раздел](../../database-engine/configure-windows/media/topic-link.gif "Значок ссылки на раздел") [Синтаксические обозначения в Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
ROWCOUNT_BIG ( )  
```  
  
## <a name="return-types"></a>Типы возвращаемых данных  
 **bigint**  
  
## <a name="remarks"></a>Remarks  
 При использовании после инструкции SELECT данная функция возвращает число строк, возвращенных инструкцией SELECT.  
  
 При использовании после инструкции INSERT UPDATE или DELETE данная функция возвращает число строк, затронутых инструкцией изменения данных.  
  
 При использовании после инструкций, не возвращающих ни одной строки (например, инструкции IF), возвращает 0.  
  
## <a name="see-also"></a>См. также:  
 [COUNT_BIG (Transact-SQL)](../../t-sql/functions/count-big-transact-sql.md)   
 [Типы данных (Transact-SQL)](../../t-sql/data-types/data-types-transact-sql.md)  
  
  
