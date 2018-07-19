---
title: Сравнение решений со скриптами и пользовательских объектов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- docset-sql-devref
- integration-services
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- managed tasks [Integration Services]
- Script task [Integration Services], vs. custom managed tasks
- SSIS Script task, vs. custom managed tasks
- custom tasks [Integration Services], scripts
ms.assetid: c0aea822-a21e-44e1-a3d3-8777bd0a1c34
caps.latest.revision: 40
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2e104afbc404b6889b75066490e536863d8d9408
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37152395"
---
# <a name="comparing-scripting-solutions-and-custom-objects"></a>Сравнение решений со сценариями и пользовательских объектов
  Задача «Скрипт» или компонент скрипта служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] может реализовать значительную часть функций, которые обеспечиваются пользовательской управляемой задачей или компонентом потока данных. Ниже приведены некоторые рекомендации, которые помогут выбрать тип задачи, отвечающий потребностям пользователя.  
  
-   Если конфигурация или функция относятся к отдельному пакету, следует создать задачу «Скрипт» или компонент скрипта, а не разрабатывать пользовательский объект.  
  
-   Если функциональность имеет общий характер и может использоваться в дальнейшем для других пакетов или другими разработчиками, то вместо решения, основанного на использовании сценариев, следует создать пользовательский объект. Пользовательский объект может быть использован в любом пакете, в то время как скрипт может использоваться только в пакете, для которого он был создан.  
  
-   Если код может быть использован повторно в рамках того же пакета, целесообразно рассмотреть возможность создания пользовательского объекта. Копирование кода из одной задачи «Скрипт» (или компонента скриптов) в другую приведет к усложнению сопровождения кода из-за необходимости поддерживать работоспособность и обеспечивать обновление нескольких копий кода.  
  
-   Если со временем предполагается внести изменения в реализацию, рассмотрите возможность использования пользовательского объекта. Пользовательские объекты можно разрабатывать и развертывать отдельно от родительского пакета, в то время как обновление, которое вносится в решение на основе сценария, требует повторного развертывания всего пакета.  
  
![Значок служб Integration Services (маленький)](../media/dts-16.gif "значок служб Integration Services (маленький)")**оставаться до даты со службами Integration Services** <br /> Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:<br /><br /> [Посетите страницу служб Integration Services на сайте MSDN](http://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.  
  
## <a name="see-also"></a>См. также  
 [Расширение пакетов с помощью пользовательских объектов](../extending-packages-custom-objects/extending-packages-with-custom-objects.md)  
  
  