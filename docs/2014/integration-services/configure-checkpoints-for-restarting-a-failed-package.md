---
title: Настройка контрольных точек для перезапуска непройденного пакета | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- checkpoints [Integration Services]
- restarting packages
- starting packages
ms.assetid: 9afffa5a-d803-4653-8afc-386453fc163f
author: janinezhang
ms.author: janinez
ms.openlocfilehash: d743341d7d1d6cae23165c7c1e4b1ddb15779927
ms.sourcegitcommit: 9ee72c507ab447ac69014a7eea4e43523a0a3ec4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84921845"
---
# <a name="configure-checkpoints-for-restarting-a-failed-package"></a>Настройка контрольных точек для повторного запуска пакета, завершившегося с ошибкой
  Устанавливая свойства, влияющие на контрольные точки, можно настроить пакеты служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] таким образом, чтобы они перезапускались с точки сбоя вместо выполнения всего пакета с начала.  
  
### <a name="to-configure-a-package-to-restart"></a>Настройка пакета для перезапуска  
  
1.  В среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]откройте проект служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , содержащий пакет, который нужно настроить.  
  
2.  В **Обозреватель решений**дважды щелкните пакет, чтобы открыть его.  
  
3.  Перейдите на вкладку **Поток управления** .  
  
4.  Щелкните правой кнопкой мыши в области конструктора потока управления и выберите **Свойства**.  
  
5.  Задайте для свойства SaveCheckpoints значение `True` .  
  
6.  Введите имя файла контрольных точек в поле свойства CheckpointFileName.  
  
7.  Установите значение свойства CheckpointUsage в одно из двух значений:  
  
    -   Установите `Always`, чтобы всегда перезапускать пакет с контрольной точки.  
  
        > [!IMPORTANT]  
        >  Если файл контрольных точек недоступен, то возникнет ошибка.  
  
    -   Выберете свойство `IfExists`, чтобы перезапускать пакет, только если доступен файл контрольных точек.  
  
8.  Настройте задачи и контейнеры, из которых пакет может быть перезапущен.  
  
    -   Правой кнопкой мыши щелкните задание или контейнер и выберите пункт **Свойства**.  
  
    -   Задайте для свойства FailPackageOnFailure значение `True` для каждой выбранной задачи и контейнера.  
  
## <a name="see-also"></a>См. также:  
 [Перезапуск пакетов с помощью контрольных точек](packages/restart-packages-by-using-checkpoints.md)  
  
  
