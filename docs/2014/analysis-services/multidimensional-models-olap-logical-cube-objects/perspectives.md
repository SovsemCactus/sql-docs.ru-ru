---
title: Перспективы | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- ready-only cube view
- OLAP objects [Analysis Services], perspectives
- storing data [Analysis Services], perspectives
- perspectives [Analysis Services]
- cubes [Analysis Services], perspectives
- visibility [Analysis Services]
- storage [Analysis Services], perspectives
ms.assetid: b064171e-b1b4-4f32-95e5-59e1b831c4c9
author: minewiskan
ms.author: owend
ms.openlocfilehash: f385fd078500739d97394cd8856fc8bd6a3b87e8
ms.sourcegitcommit: f0772f614482e0b3cde3609e178689ce62ca3a19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84545216"
---
# <a name="perspectives"></a>Перспективы
  Перспективой называется определение, позволяющее пользователям рассматривать куб с помощью более простого способа. Перспектива — это подмножество средств куба. Перспектива позволяет администраторам создавать представление куба и помогает пользователям сосредоточиться на данных, имеющих для них наибольшую значимость. Перспектива содержит подмножества множества всех объектов куба. Перспектива не может включать элементы, которые не определены в родительском кубе.  
  
 Простой объект <xref:Microsoft.AnalysisServices.Perspective> состоит из основной информации, измерений, групп мер, вычислений, ключевых показателей эффективности и действий. Основная информация включает имя и меру перспективы по умолчанию. Измерения — это подмножество измерений куба. Группы мер — это подмножество групп мер куба. Вычисления — это подмножество вычислений куба. Ключевые показатели эффективности представляют собой подмножество ключевых показателей производительности куба. Действия — это подмножество действий куба.  
  
 Вначале должны быть проведены обновление и обработка куба, и только после этого появляется возможность использовать перспективу.  
  
 Кубы могут быть очень сложными объектами для просмотра пользователями [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] . Один куб может представлять содержимое целого хранилища данных, при этом несколько групп мер в кубе будут представлять несколько таблиц фактов и несколько измерений, основанных на нескольких таблицах измерений. Такой куб представляет собой очень сложную конструкцию с высокоразвитой структурой, что может отпугнуть пользователей, которым для удовлетворения своих запросов в области бизнес-аналитики и отчетности зачастую необходимо взаимодействовать только с небольшой частью куба.  
  
 В [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] можно использовать перспективу для снижения воспринимаемой сложности Куба в [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] . Перспектива определяет просматриваемое подмножество куба, которое предоставляет точки зрения на данные куба, учитывающие особенности предприятия и приложения. Перспектива контролирует видимость объектов, содержащихся в кубе. В перспективе можно отображать или скрывать следующие объекты:  
  
-   Измерения  
  
-   Атрибуты  
  
-   Иерархии  
  
-   Группы мер  
  
-   Меры  
  
-   Ключевые показатели эффективности  
  
-   Вычисления (вычисляемые элементы, именованные наборы и команды скриптов)  
  
-   Действия  
  
 Например, куб **Adventure Works** в [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] образце [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] базы данных содержит одиннадцать групп мер и двадцать одно измерение куба, представляющее продажи, прогнозирование продаж и финансовые данные. Клиентское приложение может напрямую указывать весь куб, но такая точка зрения может быть перегружена для пользователя, пытающегося извлечь основные сведения о прогнозах продаж. Вместо этого тот же пользователь может использовать перспективу « **цели продаж** », чтобы ограничить представление куба **Adventure Works** только теми объектами, которые относятся к прогнозу продаж.  
  
 Даже те объекты куба, которые не видны пользователю в перспективе, могут быть указаны напрямую и извлечены с помощью инструкций XML для аналитики, многомерных выражений или расширений интеллектуального анализа данных. Перспективы не ограничивают доступ к объектам в кубе и не должны использоваться с такой целью. Перспективы используются для улучшения качества работы пользователя с кубом.  
  
 Перспектива является представлением куба в режиме только для чтения. Перспективу нельзя использовать для переименования или изменения объектов в кубе. Также с помощью перспективы нельзя изменить поведение или возможности куба, например использование визуальных итогов.  
  
## <a name="security"></a>Безопасность  
 Перспективы предназначены для использования не в качестве механизма обеспечения безопасности, а как средство улучшения качества работы пользователя в приложениях бизнес-аналитики. Все параметры безопасности перспективы наследуются из базового куба. Например, перспективы не могут обеспечить доступ к объектам куба, к которым пользователь еще не имеет доступа. Безопасность куба должна быть разрешена прежде, чем будет предоставлен доступ к объектам в кубе через перспективу.  
  
  
