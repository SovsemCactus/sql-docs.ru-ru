---
title: Определение полуаддитивного режима | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- semiadditive
- Business Intelligence enhancements [Analysis Services], semiadditive behavior
- measures [Analysis Services], semiadditive
ms.assetid: b25726bc-728b-4601-ad87-9015c39dc615
caps.latest.revision: 28
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 5a96921b37affe35fcb4344a66ef36aaf26cadeb
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37265420"
---
# <a name="define-semiadditive-behavior"></a>Определение полуаддитивного режима
  Во многих бизнес-сценариях широко распространены полуаддитивные меры, которые не используют статистическое вычисление единообразно для всех измерений. Со временем данная проблема затрагивает все кубы, основанные на моментальных снимках балансов. Такие моментальные снимки можно найти в приложениях, связанных с ценными бумагами, балансом счета, бюджетированием, персоналом, страховыми полисами и требованиями, и многими другими областями коммерческой деятельности.  
  
 Для определения метода статистического вычисления для отдельных мер или элементов атрибута типа учетной записи добавьте к кубу полуаддитивный режим. Если в кубе содержится измерение счетов, то полуаддитивный режим можно добавлять автоматически на основании типа учетной записи.  
  
 Чтобы добавить полуаддитивный режим, откройте куб в конструкторе кубов и выберите команду **Добавить бизнес-аналитику** в меню «Куб». В мастере бизнес-аналитики выберите параметр **Определить полуаддитивный режим** на странице **Выбор расширения** . Данный мастер затем проведет пользователя по шагам, определяющим меры, работающие в полуаддитивном режиме.  
  
 За исключением режима LastChild, который доступен в выпуске Standard Edition, полуаддитивные режимы доступны только в бизнес-аналитике или в выпуске Enterprise Edition.  
  
## <a name="define-semiadditive-behavior"></a>Определение полуаддитивного режима  
 На странице **Определение полуаддитивного режима** мастера выберите способ определения полуаддитивности, выбрав один из следующих параметров:  
  
 **Отключить полуаддитивный режим**  
 Удаляет полуаддитивный режим из куба, в котором полуаддитивный режим был ранее определен. Данный выбор восстанавливает для показателя `SUM` если он задан для любого из следующих типов статистической функции:  
  
-   By Account  
  
-   Average of Children  
  
-   First Child  
  
-   Last Child  
  
-   Last Nonempty Child  
  
-   First Nonempty Child  
  
-   None  
  
 Этот параметр не меняет меры с обычной статистической функцией: `Sum`, `Min`, `Max`, `Count`, или `Distinct``Count`.  
  
 **Мастер определил измерение счетов «Учетная запись», в которой содержатся полуаддитивные элементы. Сервер будет выполнять статистическую обработку элементов этого измерения согласно полуаддитивному режиму, указанному для каждого типа счета.**  
 Приводит к тому, что система установит все меры из групп мер, измеренных измерением типа «Счет» статистической функцией «By Account», а сервер будет собирать члены измерения согласно полуаддитивному поведению, заданному для каждого счетного типа.  
  
> [!NOTE]  
>  Данный параметр будет выбран по умолчанию, если мастер определит измерение типа «Учетная запись».  
  
 **Определение полуаддитивного режима для отдельных мер**  
 Позволяет выбрать полуаддитивный режим каждой меры в отдельности. Значение по умолчанию — `SUM` (полностью Аддитивное).  
  
> [!NOTE]  
>  Данный параметр выбирается по умолчанию, если мастер не определяет измерение типа «Учетная запись».  
  
 Для каждой меры можно выбирать любой из типов полуаддитивных функций, описанных в следующей таблице.  
  
|Полуаддитивная функция|Описание|  
|---------------------------|-----------------|  
|Average of Children|Статистическая схема элемента представляет собой среднее его потомков.|  
|ByAccount|Система читает полуаддитивное поведение, заданное для счетного типа.|  
|Count|Статистическая схема представляет собой число элементов.|  
|Количество различных|Статистическая схема представляет собой число уникальных элементов.|  
|First Child|Значение элемента вычисляется как значение его первого потомка в соответствии с измерением времени.|  
|FirstNonEmpty|Значение элемента вычисляется как значение его первого потомка в соответствии с измерением времени, содержащим данные.|  
|LastChild|Значение элемента вычисляется как значение его последнего потомка в соответствии с измерением времени.|  
|LastNonEmpty|Значение элемента вычисляется как значение его последнего потомка в соответствии с измерением времени, содержащим данные.|  
|Max|Применяется стандартная максимальная статистическая функция.|  
|Min|Применяется стандартная минимальная статистическая функция.|  
|None|Статистическая схема не применяется.|  
|SUM|Применяется стандартная функция суммирования.|  
  
 После завершения работы с мастером любой существующий полуаддитивный режим будет заменен.  
  
  