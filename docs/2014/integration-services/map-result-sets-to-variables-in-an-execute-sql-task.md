---
title: Сопоставьте результирующие наборы с переменными в задаче «Выполнение SQL» | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- result sets [Integration Services]
- mapping result sets to variables [Integration Services]
- variables [Integration Services], mapping result sets to
ms.assetid: f76738b6-dc75-4ff9-a3dd-8b083d8e410e
author: janinezhang
ms.author: janinez
ms.openlocfilehash: 6bf36f47e84b5e4965946c2109cce7d852fc88e2
ms.sourcegitcommit: f71e523da72019de81a8bd5a0394a62f7f76ea20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84951164"
---
# <a name="map-result-sets-to-variables-in-an-execute-sql-task"></a>Сопоставление результирующих наборов с переменными в задаче "Выполнение SQL"
  В этом разделе описывается создание сопоставления между результирующими наборами и переменной в задаче «Выполнение SQL». Сопоставление между результирующим набором и переменной делает результирующий набор доступным для других элементов пакета. Например, скрипт в задаче «Скрипт» может считать переменную, а потом использовать значения из результирующего набора, или источник XML может использовать результирующий набор, сохраненный в переменной. Если результирующий набор создан родительским пакетом, его можно сделать доступным дочернему пакету, вызываемому задачей «Выполнение пакета», сопоставив результирующий набор с переменной в родительском пакете, а затем для хранения значения родительской переменной создав конфигурацию переменных родительского пакета в дочернем пакете.  
  
 Описание различных типов результирующих наборов и переменных типов данных, которые можно сопоставить с результирующими наборами, см. в разделе [Результирующие наборы в задаче "Выполнение SQL"](control-flow/execute-sql-task.md).  
  
### <a name="to-map-a-result-set-to-a-variable"></a>Сопоставление результирующего набора с переменной  
  
1.  В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий необходимый пакет.  
  
2.  В **Обозреватель решений**дважды щелкните пакет, чтобы открыть его.  
  
3.  Перейдите на вкладку **Поток управления** .  
  
4.  Если пакет не включает задачу «Выполнение SQL», добавьте его к потоку управления пакета. Дополнительные сведения см. [в разделе Добавление или удаление задачи или контейнера в потоке управления](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md) .  
  .  
  
5.  Дважды щелкните задачу «Выполнение SQL».  
  
6.  В диалоговом окне **Редактор задачи «Выполнение SQL»** на странице **Общие** выберите в качестве типа результирующего набора **Одиночная строка**, **Полный результирующий набор**или **XML** .  
  
     Описание различных результирующих наборов см. в разделе [Результирующие наборы в задаче "Выполнение SQL"](result-sets-in-the-execute-sql-task.md).  
  
7.  Щелкните **Результирующий набор**.  
  
8.  Чтобы добавить сопоставление результирующего набора, щелкните **Добавить**.  
  
9. В списке **Имя переменной** выберите переменную либо создайте новую переменную. Дополнительные сведения см. в разделе [Добавление, удаление и изменение области определяемой пользователем переменной в пакете](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).  
  
     Описание переменных типов данных, которые можно сопоставить с результирующими наборами, см. в разделе [Результирующие наборы в задаче "Выполнение SQL"](result-sets-in-the-execute-sql-task.md).  
  
     Дополнительные сведения о сопоставлении переменной с отдельным столбцом и сопоставлении нескольких переменных с несколькими столбцами см. в разделе **Заполнение переменной из результирующего набора** в [Result Sets in the Execute SQL Task](control-flow/execute-sql-task.md).  
  
10. В списке **Имя результата** при необходимости измените имя результирующего набора.  
  
     Обычно можно использовать имя столбца в качестве имени результирующего набора. Также можно использовать порядковый номер столбца в списке столбцов в качестве результирующего набора. Возможность использовать имя столбца в качестве имени результирующего набора зависит от поставщика, для работы с которым настроена задача. Не все поставщики разрешают использовать имена столбцов.  
  
11. Нажмите кнопку **ОК**.  
  
## <a name="see-also"></a>См. также:  
 [Задача «Выполнение SQL»](control-flow/execute-sql-task.md)   
 [Результирующие наборы в задаче «Выполнение SQL»](result-sets-in-the-execute-sql-task.md)   
 [Задача "выполнение пакета"](control-flow/execute-package-task.md)   
 [Конфигурации пакетов](../../2014/integration-services/package-configurations.md)   
 [Создание конфигураций пакетов](../../2014/integration-services/create-package-configurations.md)   
 [Использование значений переменных и параметров в дочернем пакете](../../2014/integration-services/use-the-values-of-variables-and-parameters-in-a-child-package.md)   
 [Переменные в службах Integration Services (SSIS)](integration-services-ssis-variables.md)  
  
  
