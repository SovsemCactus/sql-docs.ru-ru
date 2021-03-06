---
title: Диалоговое окно «Свойства отчета», ссылки (построитель отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 99fe80a22f380bbe1406d357846c4103eeb0083e
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2020
ms.locfileid: "66104389"
---
# <a name="report-properties-dialog-box-references-report-builder"></a>Диалоговое окно «Свойства отчета» — «Ссылки» (построитель отчетов)
  На вкладке **Ссылки** диалогового окна **Свойства отчета** можно удалить или добавить ссылки на пользовательские или другие внешние сборки и экземпляры пользовательских классов, используемые выражениями в определении отчета. Пользовательские сборки не поддерживаются в локальном режиме построителя отчетов. Для создания отчетов, использующих пользовательские сборки, используйте [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]конструктор отчетов в.  
  
## <a name="options"></a>Параметры  
 **Добавить или удалить сборки**  
 Отображает список сборок, на которые имеются ссылки в отчете. Сборка должна быть доступна на компьютере, на котором установлено средство для создания отчетов, и на сервере отчетов. Имя ссылки должно точно совпадать с содержимым тегов ** \<CodeModule>** в файле языка определения отчетов (RDL).  
  
 **Добавление**  
 Нажмите, чтобы добавить сборку. Нажмите кнопку с многоточием (...), чтобы открыть диалоговое окно **Открыть** , и выберите сборки, необходимые для завершения обработки отчета и оценки выражений.  
  
 **Удалить**  
 Чтобы удалить ссылку на сборку из списка, выделите имя сборки, а затем нажмите кнопку **Удалить** .  
  
 **Добавить или удалить классы**  
 Отображает список экземпляров классов, которые используются в отчете. Список классов используется только элементами на основе экземпляров, но не статическими элементами.  
  
 **Добавление**  
 Нажмите, чтобы добавить ссылку на класс. Нажмите кнопку с многоточием (...), чтобы открыть диалоговое окно **Открыть** , и выберите классы, необходимые для завершения обработки отчета и оценки выражений.  
  
 **Удалить**  
 Чтобы удалить экземпляр класса, выберите его и нажмите кнопку **Удалить** .  
  
 **Вверх**  
 Применительно к классам, характеризующимся наличием зависимостей, допускается перемещение этой ссылки в более высокую позицию списка.  
  
 **Вниз**  
 Применительно к классам, характеризующимся наличием зависимостей, допускается перемещение этой ссылки в более низкую позицию списка.  
  
## <a name="see-also"></a>См. также  
 [Построитель отчетов справки по диалоговым окнам, панелям и мастерам](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [Выражения (построитель отчетов и службы SSRS)](report-design/expressions-report-builder-and-ssrs.md)  
  
  
