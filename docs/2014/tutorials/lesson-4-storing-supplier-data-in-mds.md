---
title: Занятие 4. хранение данных поставщика в MDS | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: bacd9eaf-4d12-4f25-aec7-d785dec1b623
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 15f15ff1fd48321ed4f13826fb239b6cede46242
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85006673"
---
# <a name="lesson-4-storing-supplier-data-in-mds"></a>Занятие 4: Хранение данных поставщика в MDS
  Службы Master Data Services (MDS) — это решение SQL Server для управления основными данными. Управление основными данными (MDM) описывает усилия, предпринимаемые организациями, чтобы обнаружить и определить нетранзакционные списки данных.  
  
 Модели — высший уровень организации данных в службах Master Data Services; они упорядочивают структуру основных данных. Реализация MDS может иметь одну или две модели, где каждая модель группирует схожие данные. В общем случае основные данные могут быть сгруппированы одним из четырех способов: по лицам, местам, предметам или понятиям. Например, можно создать модель «Продукт» для данных, связанных с продуктами, или модель «Клиент»для данных, связанных с клиентами. Дополнительные сведения см. в публикации [Модели (службы Master Data Services)](https://msdn.microsoft.com/library/ee633746.aspx) .  
  
 Модель может содержать одну или несколько сущностей. Каждая сущность имеет атрибуты (столбцы) и элементы (строки). Каждая строка содержит основные данные. На этом занятии будет создана модель «Поставщики» с двумя сущностями с именами «Поставщик» и «Штат». Сущность «Поставщик» будет иметь следующие атрибуты: «Код», «Имя», «Имя контактного лица», «Фамилия контактного лица», «Адрес электронной почты контактного лица», «Адрес», «Город», «Штат», «Почтовый индекс», «Страна». Дополнительные общие сведения об атрибутах см. в публикации [Атрибуты (службы Master Data Services)](https://msdn.microsoft.com/library/ee633745.aspx) . Атрибуты кода и имени соответствуют столбцам SupplierID и «Имя поставщика» в файле Excel, содержащем список очищенных и сопоставленных поставщиков.  
  
 Атрибут на основе домена — это атрибут, значения которого заполняются элементами другой сущности. Атрибуты на основе домена не позволяют пользователям вводить недопустимые значения атрибутов. Значение атрибута можно выбрать только из раскрывающегося списка, заполненного значениями из другой сущности. В этом учебнике атрибут «Штат» сущности поставщика — это атрибут на основе домена со значениями из сущности «Штат». Значение атрибута «Штат» сущности поставщика можно изменить только на одно из значений в сущности «Штат». Дополнительные сведения см. в публикации [Атрибуты на основе домена](../master-data-services/domain-based-attributes-master-data-services.md) .  
  
 Производная иерархия в MDS выводится из связи атрибутов на основе домена в модели. В этом учебнике рассматривается создание производной иерархии между сущностью «Поставщик» и сущностью «Штат». После создания производной иерархии отображается список штатов в браузере диспетчера основных данных. При щелчке штата в списке отображаются поставщики этого штата на правой панели. В будущем будет создана производная иерархия на основе этой связи. Дополнительные сведения см. в публикации [Производные иерархии](../master-data-services/derived-hierarchies-master-data-services.md) .  
  
 Вы создали базу знаний в службе DQS и использовали ее для очистки и сопоставления данных о поставщике и сохранения результатов в файле Cleansed and Matched Supplier Data.xls. На этом занятии очищенные и связанные данные будут переданы в MDS. DQS содержит только сведения о данных (метаданные), в то время как в MDS хранятся собственно данные (основной набор). Например: Службы DQS могут знать о нескольких поставщиках, однако службы MDS поддерживают информацию только о тех поставщиках, с которыми работает компания.  
  
 На этом занятии требуется выполнить следующие задачи:  
  
1.  Создать модель **Поставщики** в **MDS** с помощью **веб-приложения диспетчера основных данных**.  
  
2.  Откройте файл **Cleansed and Matched Supplier Data.xls** в Excel и используйте **Надстройку MDS для Excel** для создания именованной сущности **Поставщик** и передачи данных в MDS.  
  
3.  Убедитесь, что данные создаются в MDS с помощью **диспетчера основных данных**.  
  
4.  Создайте сущность с именем **Штат** и обновите атрибут **Штат** сущности **Поставщик** , чтобы он стал атрибутом на основе домена в зависимости от сущности **Штат** . Это делается с помощью **Надстройки MDS для Excel**.  
  
5.  Убедитесь, что атрибут на основе домена создается с помощью **диспетчера основных данных** , и обновите значения атрибута **Имя** сущности **Штат** .  
  
6.  Просмотрите обновления, выполненные с помощью **диспетчера основных данных** в **Excel**.  
  
7.  Загрузите значения из сущности **Штат** в **Excel** , добавьте значение и проверьте добавление с помощью **диспетчера основных данных**.  
  
8.  Создание и использование производной иерархии с помощью связей атрибутов на основе домена между сущностью **Поставщик** и сущностью **Штат** (атрибут «Штат» сущности поставщика имеет тип сущности «Штат») с помощью **диспетчера основных данных**.  
  
## <a name="next-step"></a>Следующий шаг  
 [Задача 1. Создание модели поставщиков с помощью диспетчера основных данных](../../2014/tutorials/task-1-creating-suppliers-model-using-master-data-manager.md)  
  
  
