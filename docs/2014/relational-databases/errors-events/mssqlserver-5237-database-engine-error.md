---
title: MSSQLSERVER_5237 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5237 (Database Engine error)
ms.assetid: 9ff28935-d1eb-47ee-99b3-1a65cb948ce7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 224317e290ce15aaed979129733b6273b3b663df
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85032744"
---
# <a name="mssqlserver_5237"></a>MSSQLSERVER_5237
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|5237|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE|  
|Текст сообщения|Перекрестная проверка наборов строк с помощью команды DBCC для объекта NAME (идентификатор объекта O_ID) окончилась неудачей, так как произошла внутренняя ошибка запроса.|  
  
## <a name="explanation"></a>Объяснение  
 Внутренняя ошибка привела к тому, что в команде DBCC не удалось выполнить запрос для проверки индексированных представлений.  
  
## <a name="user-action"></a>Действие пользователя  
 Повторно выполните команду DBCC.  
  
  
