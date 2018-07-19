---
title: Учебник. Составление инструкций Transact-SQL | Документы Майкрософт
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL statements, tutorials
- Transact-SQL tutorials
- tutorials [Transact-SQL]
ms.assetid: 2addc9be-67d0-423d-a457-192fe9d7d058
caps.latest.revision: 18
author: edmacauley
ms.author: edmaca
manager: craigg
ms.openlocfilehash: 0334281467eea3d1324732a0c2ec1978aaadf60b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37241704"
---
# <a name="tutorial-writing-transact-sql-statements"></a>Учебник. Составление инструкций Transact-SQL
  Учебник «Составление инструкций [!INCLUDE[tsql](../includes/tsql-md.md)] ». Этот учебник предназначен для пользователей, не умеющих составлять инструкции SQL. Он поможет новым пользователям начать обучение с просмотра некоторых простых инструкций по созданию таблиц и вставке данных. Этот учебник использует язык [!INCLUDE[tsql](../includes/tsql-md.md)], [!INCLUDE[msCoName](../includes/msconame-md.md)] -реализацию стандарта SQL. Он представляет собой краткое введение в язык [!INCLUDE[tsql](../includes/tsql-md.md)] и не заменяет обучение языку [!INCLUDE[tsql](../includes/tsql-md.md)] . Инструкции в учебнике намеренно простые и не представляют всей сложности типичной производственной базы данных.  
  
> [!NOTE]  
>  Новые пользователи баз данных чаще всего считают, что с [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] легче работать с помощью среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] вместо инструкций [!INCLUDE[tsql](../includes/tsql-md.md)].  
  
## <a name="finding-more-information"></a>Дополнительные сведения  
 Дополнительные сведения об отдельных инструкциях см. в электронной документации по SQL Server либо по имени инструкции, либо используя вкладку "Содержание" для просмотра 1800 языковых элементов, перечисленных в алфавитном порядке в разделе [Справочник по Transact-SQL (компонент Database Engine)](/sql/t-sql/language-reference). Еще одной хорошей стратегией нахождения информации является ее поиск по ключевым словам, относящимся к интересующей вас тематике. Например, чтобы узнать, как возвратить часть даты (например, месяц), выполните поиск в индексе по **датам [SQL Server]**, а затем используйте **функции извлечения частей даты**. Это приведет к разделу [DATEPART (Transact-SQL)](/sql/t-sql/functions/datepart-transact-sql). В качестве другого примера, чтобы выяснить, как работать со строками, ищите **строковые функции**. Это приведет к разделу [Строковые функции (Transact-SQL)](/sql/t-sql/functions/string-functions-transact-sql).  
  
## <a name="what-you-will-learn"></a>Обзор учебника  
 В этом учебнике показано, как создать базу данных и таблицу в ней, вставить данные в таблицу, обновить их, прочитать и удалить данные, удалить таблицу. Будут созданы представления и хранимые процедуры, а для базы данных и данных будет настроен пользователь.  
  
 Учебник разделен на три занятия.  
  
 [Урок 1. Создание объектов базы данных](lesson-1-creating-database-objects.md)  
 В этом занятии будет создана база данных, таблица в ней, вставлены данные в таблицу, затем данные будут обновлены и прочитаны.  
  
 [Урок 2. Настройка разрешений для объектов базы данных](lesson-2-configuring-permissions-on-database-objects.md)  
 В этом занятии будут созданы имя входа и пользователь. Также будут созданы представление и хранимая процедура, и пользователю будет предоставлено разрешение на нее.  
  
 [Урок 3. Удаление объектов базы данных](lesson-3-1-deleting-database-objects.md)  
 В этом занятии доступ к данным будет запрещен, данные из таблицы удалены, сама таблица тоже удалена вместе с базой данных.  
  
## <a name="requirements"></a>Требования  
 Чтобы завершить этот учебник, не нужно обладать знаниями языка SQL, но нужно иметь основные понятия о базах данных, таких как таблицы. С помощью этого учебника будут созданы база данных и пользователь Windows. Эти задачи требуют высокого уровня разрешений, так что следует войти в систему в качестве администратора.  
  
 В системе должно быть установлено следующее.  
  
-   Любой выпуск [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].  
  
-   Среда [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] или Management Studio Express.  
  
-   Internet Explorer 6 или более поздней версии.  
  
> [!NOTE]  
>  При просмотре учебников рекомендуется добавить **Далее** и **Назад** кнопок панели инструментов средства просмотра документов.  
  
  