---
title: Функции работы с курсорами (Transact-SQL) | Документы Майкрософт
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- functions [SQL Server], cursors
- cursor functions
ms.assetid: 7d9daa10-4c50-4212-9400-42120222b2b8
author: julieMSFT
ms.author: jrasnick
ms.openlocfilehash: 7693717fc061f79b77eb8e18b5584c6bde40d92e
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82823917"
---
# <a name="cursor-functions-transact-sql"></a>Функции работы с курсорами (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

Следующие скалярные функции возвращают сведения о курсорах:
  
|||  
|-|-|  
|[@@CURSOR_ROWS](../../t-sql/functions/cursor-rows-transact-sql.md)|[CURSOR_STATUS](../../t-sql/functions/cursor-status-transact-sql.md)|  
|[@@FETCH_STATUS](../../t-sql/functions/fetch-status-transact-sql.md)||  
  
Все функции работы с курсорами являются недетерминированными. Это означает, что такие функции не всегда возвращают одинаковые значения при каждом выполнении, даже если наборы входных значений одинаковы. Дополнительные сведения о детерминированности функций см. в статье [Детерминированные и недетерминированные функции](../../relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions.md).
  
## <a name="see-also"></a>См. также раздел
[Встроенные функции (Transact-SQL)](~/t-sql/functions/functions.md)
  
  
