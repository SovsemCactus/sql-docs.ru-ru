---
title: Перенос баз данных Oracle в SQL Server (OracleToSQL) | Документация Майкрософт
description: Используйте этот рекомендуемый процесс для переноса баз данных Oracle в SQL Server или базу данных SQL Azure с помощью Помощник по миграции SQL Server (SSMA).
ms.prod: sql
ms.custom: ''
ms.date: 04/22/2018
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 1d196dd6-4322-4c98-bb72-602c57d96134
author: Shamikg
ms.author: Shamikg
manager: shamikg
ms.openlocfilehash: 67fb6eeba0a1385d3d764dfa2d8e55f40f34455a
ms.sourcegitcommit: 59cda5a481cfdb4268b2744edc341172e53dede4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84294056"
---
# <a name="migrating-oracle-databases-to-sql-server-oracletosql"></a>Миграция баз данных Oracle в SQL Server (OracleToSQL)
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Помощник по миграции (SSMA) для Oracle — это Комплексная среда, которая помогает быстро переносить базы данных Oracle в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , базу данных SQL Azure или хранилище Azure SQL. С помощью SSMA для Oracle можно просматривать объекты и данные базы данных, оценивать базы данных для миграции, переносить объекты баз данных в хранилище данных SQL Azure, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] а также выполнять миграцию данных в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , базу данных SQL Azure или хранилище Azure SQL. Обратите внимание, что нельзя перенести системные схемы SYS и Oracle.
  
## <a name="recommended-migration-process"></a>Рекомендуемый процесс миграции  
Чтобы успешно выполнить миграцию объектов и данных из баз данных Oracle в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , базу данных SQL Azure или хранилище Azure SQL, используйте следующую процедуру.
  
1.  [Создайте новый проект SSMA](working-with-ssma-projects-oracletosql.md).  
  
    После создания проекта можно задать параметры преобразования проекта, миграции и сопоставления типов. Сведения о параметрах проекта см. в разделе [Установка параметров проекта &#40;OracleToSQL&#41;](../../ssma/oracle/setting-project-options-oracletosql.md). Сведения о настройке сопоставлений типов данных см. в разделе [Сопоставление типов данных Oracle и SQL Server &#40;OracleToSQL&#41;](../../ssma/oracle/mapping-oracle-and-sql-server-data-types-oracletosql.md).  
  
2.  [Подключитесь к серверу базы данных Oracle](connecting-to-oracle-database-oracletosql.md).  
  
3.  [Подключитесь к экземпляру SQL Server](connecting-to-sql-server-oracletosql.md).  
  
4.  [Сопоставьте схемы базы данных Oracle с SQL Server схемами базы данных](mapping-oracle-schemas-to-sql-server-schemas-oracletosql.md).  
  
5.  При необходимости [Создайте отчеты об оценке](assessing-oracle-schemas-for-conversion-oracletosql.md) для оценки объектов базы данных для преобразования и оценки времени преобразования.  
  
6.  [Преобразование схем базы данных Oracle в схемы SQL Server](converting-oracle-schemas-oracletosql.md).  
  
7.  [Загрузите преобразованные объекты базы данных в SQL Server](loading-converted-database-objects-into-sql-server-oracletosql.md).  
  
    Это можно сделать одним из следующих способов:  
  
    -   Сохраните скрипт и запустите его в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
    -   Синхронизируйте объекты базы данных.  
  
8.  [Перенос данных в SQL Server](migrating-oracle-data-into-sql-server-oracletosql.md).  
  
9. При необходимости обновите приложения базы данных.  
  
## <a name="see-also"></a>См. также:  
[Установка SSMA для Oracle &#40;OracleToSQL&#41;](../../ssma/oracle/installing-ssma-for-oracle-oracletosql.md)  
[Начало работы с SSMA для Oracle &#40;OracleToSQL&#41;](../../ssma/oracle/getting-started-with-ssma-for-oracle-oracletosql.md)  
  
