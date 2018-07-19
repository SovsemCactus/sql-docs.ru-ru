---
title: Подключение к Microsoft SQL Server Analysis Services (SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connsqlserveras.f1
ms.assetid: 7f3244ee-b690-471c-893d-68e361c2d416
caps.latest.revision: 11
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 43a7dd31c52c81f7a2bfcbf87d1a8df3f6740081
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37323664"
---
# <a name="connect-to-microsoft-sql-server-analysis-services-ssas"></a>Соединение со службами Microsoft SQL Server Analysis Services (SSAS)
  На этой странице **мастера импорта таблиц** позволяет указать параметры импорта данных из куба служб Microsoft SQL Server Analysis Services или книгу PowerPivot, размещенной на сайте SharePoint. Для доступа к мастеру из [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]выберите пункт **Импорт из источника данных** в меню **Модель**.  
  
 Для соединения с источником данных на компьютере должен быть установлен соответствующий поставщик.  
  
> [!NOTE]  
>  При выборе базы данных на этой странице используются учетные данные текущего пользователя. Тем не менее импорт не будет успешным, если пользователь, указанный на странице сведений об олицетворении, не имеет достаточных прав для чтения из выбранной базы данных.  
  
## <a name="uielement-list"></a>Список элементов пользовательского интерфейса  
 **Понятное имя соединения**  
 Введите уникальное имя для соединения с источником данных. Это поле является обязательным.  
  
 **Имя сервера или файла**  
 Введите одно из следующих значений.  
  
-   Введите имя или IP-адрес сервера служб SQL Server Analysis Services, с которым необходимо установить соединение.  
  
     Для указания локального сервера можно использовать точку (.), (local) или localhost.  
  
-   Введите URL-адрес книги PowerPivot, опубликованной на сайте SharePoint.  
  
 **Использовать проверку подлинности Windows**  
 Укажите, следует ли использовать проверку подлинности Windows для подключения к серверу служб SQL Server Analysis Services.  
  
 Режим проверки подлинности Windows позволяет подключаться с учетной записью Windows. При возможности используйте проверку подлинности Windows.  
  
 При использовании проверки подлинности Windows учетные данные текущего пользователя задействованы при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта. Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.  
  
 **Использовать проверку подлинности SQL Server**  
 Укажите, следует ли использовать проверку подлинности SQL Server для подключения к серверу служб SQL Server Analysis Services.  
  
 При проверке подлинности SQL Server последний проверяет существование учетной записи входа SQL Server и совпадение указанного пароля с ранее сохраненным паролем.  
  
 Проверка подлинности SQL Server используется для создания строки подключения для источника данных. Эти учетные данные также используются при просмотре и фильтрации данных в окне «Свойства таблицы» и в мастере импорта. Эти учетные данные не используются для импорта или обновления данных. Вместо них используются учетные данные Windows, указанные на странице сведений об олицетворении.  
  
 **Имя пользователя**  
 Укажите имя пользователя для подключения к базе данных. Этот параметр доступен только при соединении с использованием метода проверки подлинности Windows.  
  
 **Пароль**  
 Укажите пароль для подключения к базе данных. Этот параметр доступен для редактирования только при подключении с использованием проверки подлинности SQL Server.  
  
 **Сохранить пароль**  
 Укажите, нужно ли сохранить пароль, введенный в поле **Пароль** . Этот параметр доступен только при выборе проверки подлинности SQL Server.  
  
 **Имя базы данных**  
 Выберите базу данных из списка баз данных.  
  
 **Дополнительно**  
 Задайте дополнительные свойства соединения в диалоговом окне **Задание дополнительных свойств** . Дополнительные сведения см. в разделе [Установка дополнительных свойств (SSAS)](set-advanced-properties-ssas.md).  
  
 **Проверка соединения**  
 Установите соединение с источником данных с использованием текущих параметров. Появится сообщение об успешном или неуспешном соединении.  
  
  