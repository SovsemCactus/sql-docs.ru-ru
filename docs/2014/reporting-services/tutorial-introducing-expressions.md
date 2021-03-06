---
title: Учебник. Общие сведения о выражениях | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d05ef4c-5f91-48b2-8795-f0a201a0b3cc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 79563abac2c6a9ed64dff93667ff3d3966b70bc5
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2020
ms.locfileid: "66098848"
---
# <a name="tutorial-introducing-expressions"></a>Учебник. Общие сведения о выражениях
  Выражения позволяют создавать мощные и гибкие отчеты. С помощью этого учебника вы научитесь создавать и реализовывать выражения с часто используемыми функциями и операторами. Диалоговое окно **выражение** используется для написания выражений, объединяющих значения имени, поиска значений в отдельном наборе данных, отображения различных изображений на основе значений полей и т. д.  
  
 Это отчет, в котором чередуются строки белого и другого цвета. В отчет включен параметр для выбора цвета строк, отличных от белых.  
  
 На приведенном далее рисунке показан отчет, похожий на тот, который будет в итоге создан.  
  
 ![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a>Что вы узнаете  
 В этом учебнике рассматриваются следующие темы:  
  
1.  [Создание табличного отчета и набора данных с помощью мастера таблицы или матрицы](#Setup)  
  
2.  [Обновление имен по умолчанию для источника и набора данных](#UpdateNames)  
  
3.  [Отображение фамилии, имени и инициала отчества](#Concatenate)  
  
4.  [Отображение пола с помощью изображений](#Gender)  
  
5.  [Поиск имени в таблице CountryRegion](#Lookup)  
  
6.  [Подсчет дней с последней покупки](#Count)  
  
7.  [Отображение сравнения цен с помощью индикатора](#Indicator)  
  
8.  [Создание отчета с «зеленым» отчетом](#GreenBar)  
  
### <a name="other-optional-steps"></a>Другие дополнительные шаги  
  
-   [Форматирование столбца даты](#DateFormat)  
  
-   [Добавление заголовка отчета](#Title)  
  
-   [Сохранение отчета](#Save)  
  
 Предполагаемое время для выполнения заданий данного учебника: 30 минут.  
  
## <a name="requirements"></a>Требования  
 Дополнительные сведения о требованиях см. в разделе [Предварительные условия для использования учебников (построитель отчетов)](../reporting-services/report-builder-tutorials.md).  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a>1. Создание табличного отчета и набора данных с помощью мастера таблицы или матрицы  
 Создайте табличный отчет, источник данных и набор данных. При создании макета таблицы будут включены лишь несколько полей. После завершения работы мастера добавьте столбцы вручную. Мастер дает возможность легко разместить в отчете таблицу и применить стиль.  
  
> [!NOTE]  
>  В этом учебнике запрос уже содержит значения данных, поэтому внешний источник данных не требуется. В связи с этим запрос получается весьма длинным. В рабочей среде запрос не будет содержать данные. Этот запрос содержит данные только в учебных целях.  
  
> [!NOTE]  
>  В этом учебнике шаги работы с мастером объединены в одну процедуру. Пошаговые инструкции по переходу к серверу отчетов, выбору источника данных и созданию набора данных см. в первом учебнике этой серии: [Учебник. Создание простого табличного отчета &#40;построитель отчетов&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).  
  
#### <a name="to-create-a-new-table-report"></a>Создание нового табличного отчета  
  
1.  Нажмите кнопку **Пуск**, укажите пункт **программы**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]выберите пункт **Построитель отчетов**и щелкните **Построитель отчетов**.  
  
     Откроется диалоговое окно **Начало работы** .  
  
    > [!NOTE]  
    >  Если диалоговое окно **Начало работы** не отображается, на кнопке **Построитель отчетов** нажмите кнопку **создать**.  
  
    > [!NOTE]  
    >  Если вы предпочитаете использовать версию ClickOnce построитель отчетов, откройте диспетчер отчетов и нажмите кнопку " **Построитель отчетов**" или перейдите на сайт SharePoint, на котором Reporting Services типы содержимого, такие как отчеты, и щелкните **Построитель отчетов отчет** в меню " **создать документ** " на вкладке " **документы** " библиотеки общих документов.  
  
2.  Убедитесь, что на левой панели выбран **Новый отчет** .  
  
3.  На панели справа выберите **Мастер таблицы или матрицы**.  
  
4.  На странице **Выбор набора данных** выберите **Создать набор данных**.  
  
5.  Нажмите кнопку **Далее**.  
  
6.  На странице **Выбор соединения с источником данных** выберите источник данных, имеющий тип **SQL Server**. Выберите источник данных из списка или перейдите на сервер отчетов, чтобы выбрать его там.  
  
7.  Нажмите кнопку **Далее**.  
  
8.  На странице **Проектирование запроса** нажмите кнопку **Изменить как текст**.  
  
9. На панель запроса вставьте следующий запрос:  
  
    ```  
    SELECT 'Lauren' AS FirstName,'Johnson' AS LastName, 'American Samoa' AS StateProvince, 1 AS CountryRegionID,'Unknown' AS Gender, CAST(9996.60 AS money) AS YTDPurchase, CAST('2010-6-10' AS date) AS LastPurchase  
    UNION SELECT'Warren' AS FirstName, 'Pal' AS LastName, 'New South Wales' AS StateProvince, 2 AS CountryRegionID, 'Male' AS Gender, CAST(5747.25 AS money) AS YTDPurchase, CAST('2010-7-3' AS date) AS LastPurchase  
    UNION SELECT 'Fernando' AS FirstName, 'Ross' AS LastName, 'Alberta' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(9248.15 AS money) AS YTDPurchase, CAST('2010-10-17' AS date) AS LastPurchase  
    UNION SELECT 'Rob' AS FirstName, 'Caron' AS LastName, 'Northwest Territories' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(742.50 AS money) AS YTDPurchase, CAST('2010-4-29' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Bailey' AS LastName, 'British Columbia' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(1147.50 AS money) AS YTDPurchase, CAST('2010-6-15' AS date) AS LastPurchase  
    UNION SELECT  'Bridget' AS FirstName, 'She' AS LastName, 'Hamburg' AS StateProvince, 4 AS CountryRegionID, 'Female' AS Gender, CAST(7497.30 AS money) AS YTDPurchase, CAST('2010-5-10' AS date) AS LastPurchase  
    UNION SELECT 'Alexander' AS FirstName, 'Martin' AS LastName, 'Saxony' AS StateProvince, 4 AS CountryRegionID, 'Male' AS Gender, CAST(2997.60 AS money) AS YTDPurchase, CAST('2010-11-19' AS date) AS LastPurchase  
    UNION SELECT 'Yolanda' AS FirstName, 'Sharma' AS LastName ,'Micronesia' AS StateProvince, 5 AS CountryRegionID, 'Female' AS Gender, CAST(3247.95 AS money) AS YTDPurchase, CAST('2010-8-23' AS date) AS LastPurchase  
    UNION SELECT 'Marc' AS FirstName, 'Zimmerman' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1200.00 AS money) AS YTDPurchase, CAST('2010-11-16' AS date) AS LastPurchase  
    UNION SELECT 'Katherine' AS FirstName, 'Abel' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Female' AS Gender, CAST(2025.00 AS money) AS YTDPurchase, CAST('2010-12-1' AS date) AS LastPurchase  
    UNION SELECT 'Nicolas' as FirstName, 'Anand' AS LastName, 'Seine (Paris)' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1425.00 AS money) AS YTDPurchase, CAST('2010-12-11' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Peters' AS LastName, 'England' AS StateProvince, 12 AS CountryRegionID, 'Male' AS Gender, CAST(887.50 AS money) AS YTDPurchase, CAST('2010-8-15' AS date) AS LastPurchase  
    UNION SELECT 'Alison' AS FirstName, 'Nath' AS LastName, 'Alaska' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(607.50 AS money) AS YTDPurchase, CAST('2010-10-13' AS date) AS LastPurchase  
    UNION SELECT 'Grace' AS FirstName, 'Patterson' AS LastName, 'Kansas' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(1215.00 AS money) AS YTDPurchase, CAST('2010-10-18' AS date) AS LastPurchase  
    UNION SELECT 'Bobby' AS FirstName, 'Sanchez' AS LastName, 'North Dakota' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(6191.00 AS money) AS YTDPurchase, CAST('2010-9-17' AS date) AS LastPurchase  
    UNION SELECT 'Charles' AS FirstName, 'Reed' AS LastName, 'Nebraska' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8772.00 AS money) AS YTDPurchase, CAST('2010-8-27' AS date) AS LastPurchase  
    UNION SELECT 'Orlando' AS FirstName, 'Romeo' AS LastName, 'Texas' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8578.00 AS money) AS YTDPurchase, CAST('2010-7-29' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    ```  
  
     В запросе указываются имена таких столбцов, как дата рождения, фамилия, имя, область или республика, идентификатор страны или региона, пол и число покупок за последний год.  
  
10. На панели инструментов конструктора запросов нажмите кнопку **выполнить** (**!**). В результирующем наборе будет 20 строк данных, включающих следующие столбцы: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase и LastPurchase.  
  
11. Нажмите кнопку **Далее**.  
  
12. На странице **Размещение полей** перетащите следующие поля в указанном порядке из списка **Доступные поля** в список **Значения** .  
  
    -   StateProvince  
  
    -   CountryRegionID  
  
    -   LastPurchase  
  
    -   YTDPurchase  
  
     Поскольку столбцы CountryRegionID и YTDPurchase содержат числовые данные, по умолчанию к ним применяется статистическое выражение SUM.  
  
    > [!NOTE]  
    >  Поля FirstName и LastName не включаются. Их нужно будет добавить позже.  
  
13. В списке **значения** щелкните правой кнопкой мыши `CountryRegionID` и выберите параметр **Sum** .  
  
     Суммирование больше не применяется к полю CountryRegionID.  
  
14. В списке **Значения** щелкните правой кнопкой мыши **YTDPurchase** и выберите пункт **Сумма** .  
  
     Суммирование больше не применяется к полю YTDPurchase.  
  
15. Нажмите кнопку **Далее**.  
  
16. На странице **Выбор макета** нажмите кнопку **Далее**.  
  
17. На странице **Выбор стиля** щелкните элемент **содержание**и нажмите кнопку **Готово**.  
  
##  <a name="2-update-default-names-of-the-data-source-and-dataset"></a><a name="UpdateNames"></a>2. обновление имен по умолчанию для источника данных и набора данных  
  
#### <a name="to-update-the-default-name-of-the-data-source"></a>Изменение имени источника данных по умолчанию  
  
1.  В области данных отчета разверните узел **Источники данных**.  
  
2.  Щелкните правой кнопкой мыши пункт **DataSource1** и выберите пункт **Свойства источника данных**.  
  
3.  В поле **Имя** введите **ExpressionsDataSource**.  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-update-the-default-name-of-the-dataset"></a>Изменение имени набора данных по умолчанию  
  
1.  В области данных отчета разверните узел **Наборы данных**.  
  
2.  Щелкните правой кнопкой мыши пункт **DataSet1** и выберите пункт **Свойства набора данных**.  
  
3.  В поле **Имя** введите **Expressions**.  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="3-display-first-name-initial-and-last-name"></a><a name="Concatenate"></a>3. Отображение имени, начального и последнего имени  
 Укажите в выражении функцию **Left** и оператор **Concatenate** (**&**) для вычисления имени, состоящего из фамилии и инициала отчества. Можно построить выражение в пошаговом режиме либо пропустить процедуру, а затем скопировать и вставить выражение из учебника в диалоговом окне **Выражение** .  
  
#### <a name="to-add-the-name-column"></a>Добавление столбца Name  
  
1.  Щелкните правой кнопкой мыши столбец **StateProvince** , наведите указатель на пункт **Вставить столбец**, а затем выберите пункт **Слева**.  
  
     Новый столбец будет добавлен слева от столбца **StateProvince** .  
  
2.  Щелкните заголовок нового столбца и введите **Name**.  
  
3.  Щелкните правой кнопкой мыши ячейку данных для столбца **Name** и выберите пункт **Выражение**.  
  
4.  В диалоговом окне **Выражение** разверните узел **Общие функции**и выберите **Текст**.  
  
5.  В списке **Элемент** дважды щелкните **Left**.  
  
     В выражение будет добавлена функция **Left** .  
  
6.  В списке **Категория** щелкните **Поля (выражения)**.  
  
7.  В списке **Значения** дважды щелкните **FirstName**.  
  
8.  Введите **, 1)**  
  
     Это выражение извлекает один символ из значения **FirstName** , считая слева.  
  
9. Введите **&" "&**  
  
10. В списке **Значения** дважды щелкните **LastName**.  
  
     Готовое выражение: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. Нажмите кнопку **Выполнить** для предварительного просмотра отчета.  
  
##  <a name="4-use-images-to-display-gender"></a><a name="Gender"></a>4. Использование изображений для вывода пола  
 Пол можно показать с помощью изображений, обозначив неизвестный пол третьим изображением. Добавим в отчет три скрытых изображения в новом столбце, а затем определим изображение, которое будет отображаться в столбце исходя из значения поля Gender.  
  
 Чтобы применить цвет к ячейке таблицы, содержащей изображение, когда создается отчет с чередованием цвета строк, нужно добавить прямоугольник и добавить изображение в него. Использование прямоугольника обусловлено тем, что фоновый цвет можно применить к прямоугольнику, а не к изображению.  
  
 В учебнике используются изображения, устанавливаемые в составе Windows, однако можно использовать и любые другие доступные изображения. Внедренные изображения, которые мы будем использовать, не нужно устанавливать на локальном компьютере или сервере отчетов.  
  
#### <a name="to-add-images-to-the-report-body"></a>Добавление изображений в текст отчета  
  
1.  Щелкните **Конструктор** для возврата в режим конструктора.  
  
2.  На вкладке ленты **Вставка** щелкните **Изображение**, а затем текст отчета ниже таблицы.  
  
     Откроется диалоговое окно **Свойства изображения**.  
  
3.  Щелкните **Импорт** и перейдите в папку C:\Пользователи\Общие\Общие изображения\Образцы изображений.  
  
4.  Щелкните файл Penguins.JPG, а затем нажмите кнопку **Открыть**.  
  
     В диалоговом окне **Свойства изображения** щелкните **Видимость**, а затем выберите параметр **Скрыть**.  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  Повторите шаги с 2 по 5, выбрав файл Koala.JPG.  
  
7.  Повторите шаги с 2 по 5, выбрав Tulips.JPG.  
  
#### <a name="to-add-the-gender-column"></a>Добавление столбца Gender  
  
1.  Щелкните правой кнопкой мыши столбец **Name**, наведите указатель на пункт **Вставить столбец**, а затем выберите пункт **Справа**.  
  
     Новый столбец будет добавлен справа от столбца **Name**.  
  
2.  Щелкните название нового столбца и введите **Gender**.  
  
#### <a name="to-add-a-rectangle"></a>Добавление прямоугольника  
  
-   На вкладке ленты **Вставка** щелкните **Прямоугольник**, а затем щелкните ячейку данных в столбце **Gender**.  
  
     В ячейку будет добавлен прямоугольник.  
  
#### <a name="to-add-an-image-to-the-rectangle"></a>Добавление изображения в прямоугольник  
  
1.  Щелкните прямоугольник правой кнопкой мыши, наведите указатель на пункт **Вставить** и выберите пункт **Изображение**.  
  
2.  В диалоговом окне **Свойства изображения** щелкните стрелку вниз рядом с параметром **Использовать это изображение**, а затем выберите одно из добавленных изображений, например Penguins.JPG.  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-use-images-to-show-gender"></a>Отображение пола с помощью изображений  
  
1.  Щелкните правой кнопкой мыши изображение в ячейке данных в столбце **Gender** и выберите пункт **Свойства изображения**.  
  
2.  В диалоговом окне **Свойства изображения** нажмите кнопку выражения **fx** рядом с текстовым полем **Использовать это изображение**.  
  
3.  В диалоговом окне **Выражение** разверните узел **Общие функции** и выберите **Программный поток**.  
  
4.  В списке **Элемент** дважды щелкните **Switch**.  
  
5.  В списке **Категория** щелкните **Поля (выражения)**.  
  
6.  В списке **Значения** дважды щелкните **Gender**.  
  
7.  Введите **="Мужской", "Коала",**  
  
8.  В списке **Значения** дважды щелкните **Gender**.  
  
9. Введите **="Женский", "Пингвины",**  
  
10. В списке **Значения** дважды щелкните **Gender**.  
  
11. Введите **="Неизвестно", "Тюльпаны")**  
  
     Готовое выражение: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. Снова нажмите кнопку **ОК**, чтобы выйти из диалогового окна **Свойства изображения**.  
  
14. Нажмите кнопку **Выполнить** для предварительного просмотра отчета.  
  
##  <a name="5-look-up-countryregion-name"></a><a name="Lookup"></a>5. Поиск имени в названии "страна"  
 Создадим набор данных CountryRegion и покажем название страны или региона вместо идентификатора с помощью функции **Lookup**.  
  
#### <a name="to-create-the-countryregion-dataset"></a>Создание набора данных CountryRegion  
  
1.  Щелкните **Конструктор** для возврата в режим конструктора.  
  
2.  В области данных отчета нажмите кнопку **Создать** и выберите **Набор данных**.  
  
3.  Выберите **Использовать набор данных, внедренный в отчет**.  
  
4.  В списке **Источник данных** выберите ExpressionsDataSource.  
  
5.  В поле **Имя** введите **CountryRegion**.  
  
6.  Убедитесь в том, что выбран тип запроса **Текст** , и нажмите кнопку **Конструктор запросов**.  
  
7.  Нажмите кнопку **Изменить как текст**.  
  
8.  Скопируйте и вставьте на панели запросов следующий запрос:  
  
    ```  
    SELECT 1 AS ID, 'American Samoa' AS CountryRegion  
    UNION SELECT 2 AS CountryRegionID, 'Australia' AS CountryRegion  
    UNION SELECT 3 AS ID, 'Canada' AS CountryRegion  
    UNION SELECT 4 AS ID, 'Germany' AS CountryRegion  
    UNION SELECT 5 AS ID, 'Micronesia' AS CountryRegion  
    UNION SELECT 6 AS ID, 'France' AS CountryRegion  
    UNION SELECT 7 AS ID, 'United States' AS CountryRegion  
    UNION SELECT 8 AS ID, 'Brazil' AS CountryRegion  
    UNION SELECT 9 AS ID, 'Mexico' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Japan' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Australia' AS CountryRegion  
    UNION SELECT 12 AS ID, 'United Kingdom' AS CountryRegion  
    ```  
  
9. Нажмите кнопку **выполнить** (**!**), чтобы выполнить запрос.  
  
     Результатом запроса будут идентификаторы и названия стран и регионов.  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. Снова нажмите кнопку **ОК** , чтобы выйти из диалогового окна **Свойства набора данных** .  
  
#### <a name="to-look-up-values-in-the-countryregion-dataset"></a>Поиск значений в наборе данных CountryRegion  
  
1.  Щелкните заголовок столбца **Country Region ID** и удалите текст: ID.  
  
2.  Щелкните правой кнопкой мыши ячейку для столбца **Country Region** и выберите пункт **Выражение**.  
  
3.  Удалите выражение, оставив знак равенства «=».  
  
     Оставшееся выражение: `=`  
  
4.  В диалоговом окне **Выражение** разверните узел **Общие функции** и выберите **Прочее**.  
  
5.  В списке **Элемент** дважды щелкните **Lookup**.  
  
6.  В списке **Категория** щелкните **Поля (выражения)**.  
  
7.  В списке **значения** дважды щелкните `CountryRegionID`.  
  
8.  Если курсор не расположен сразу после `CountryRegionID.Value`, установите его в это положение.  
  
9. Удалите правую скобку и введите **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**  
  
     Готовое выражение: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`  
  
     Синтаксис функции **Lookup** задает поиск соответствия между CountryRegionID и ID в наборе данных CountryRegion, возвращающий значение CountryRegion, которое также имеется в наборе данных CountryRegion.  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. Нажмите кнопку **Выполнить** для предварительного просмотра отчета.  
  
##  <a name="6-count-days-since-last-purchase"></a><a name="Count"></a>6. Подсчет дней с момента последней покупки  
 Добавьте столбец, а затем используйте функцию **Now** или `ExecutionTime` встроенную глобальную переменную, чтобы рассчитать количество дней с сегодняшнего дня с момента последнего приобретения сотрудника.  
  
#### <a name="to-add-the-days-ago-column"></a>Добавление столбца Days Ago  
  
1.  Щелкните **Конструктор** для возврата в режим конструктора.  
  
2.  Щелкните правой кнопкой мыши столбец **Last Purchase** , наведите указатель на пункт **Вставить столбец**, а затем выберите пункт **Справа**.  
  
     Новый столбец будет добавлен справа от столбца **Last Purchase** .  
  
3.  В заголовке столбца введите **Days Ago**.  
  
4.  Щелкните правой кнопкой мыши ячейку столбца **Days Ago** и выберите пункт **Выражение**.  
  
5.  В диалоговом окне **Выражение** разверните узел **Общие функции** и выберите пункт **Дата и время**.  
  
6.  В списке **Элемент** дважды щелкните **DateDiff**.  
  
7.  Если курсор не расположен сразу после `DateDiff(`, установите его в это положение.  
  
8.  Введите **"d",**  
  
9. В списке **Категория** щелкните **Поля (выражения)**.  
  
10. В списке **Значения** дважды щелкните **LastPurchase**.  
  
11. Если курсор не расположен сразу после `Fields!LastPurchase.Value`, установите его в это положение.  
  
12. Тип **,**  
  
13. В списке **Категория** еще раз щелкните **Дата и время**.  
  
14. В списке **Элемент** дважды щелкните **Now**.  
  
    > [!WARNING]  
    >  В рабочих отчетах функцию **Now** нельзя использовать в выражениях, которые вычисляются многократно при подготовке отчета (например, в строках детализации отчета). Значение **Now** будет разным в разных строках, и эти различия повлияют на результаты вычислений, что может привести к некоторой несогласованности результатов. Вместо этого необходимо пользоваться глобальной переменной `ExecutionTime`, имеющейся в службах [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].  
  
15. Если курсор не расположен сразу после `Now(`, установите его в это положение.  
  
16. Удалите левую скобку и введите **)**  
  
     Готовое выражение: `=DateDiff("d", Fields!LastPurchase.Value, Now)`  
  
17. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="7-use-an-indicator-to-show-sales-comparison"></a><a name="Indicator"></a>7. Использование индикатора для отображения сравнения продаж  
 Добавьте новый столбец и используйте индикатор, чтобы узнать, будут ли покупки пользователя с начала года (YTD) выше или ниже среднего закупок с начала года. Функция **Round** округляет значения до целого числа.  
  
 Настройка индикатора и его состояний производится в несколько шагов. При необходимости в процедуре "Настройка индикатора" можно пропустить и скопировать и вставить заполненные выражения из этого учебника в диалоговое окно **выражение** .  
  
#### <a name="to-add-the--or---avg-sales-column"></a>Добавление столбца «+ or - AVG Sales»  
  
1.  Щелкните правой кнопкой мыши столбец **YTD Purchase** , наведите указатель на пункт **Вставить столбец**, а затем выберите пункт **Справа**.  
  
     Новый столбец будет добавлен справа от столбца **YTD Purchase** .  
  
2.  Щелкните заголовок нового столбца и введите **+ or - AVG Sales**  
  
#### <a name="to-add-an-indicator"></a>Добавление индикатора  
  
1.  На вкладке ленты **Вставка** щелкните **Индикатор**, а затем ячейку данных для столбца **+ or - AVG Sales**.  
  
     Откроется диалоговое окно **Выбор стиля индикатора** .  
  
2.  В группе наборов значков **Направляющие** щелкните набор из трех серых стрелок.  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-configure-the-indicator"></a>Настройка индикатора  
  
1.  Щелкните индикатор правой кнопкой мыши, выберите пункт **Свойства индикатора**, а затем щелкните **Значение и состояния**.  
  
2.  Нажмите кнопку выражения **fx** рядом с текстовым полем **Значение** .  
  
3.  В диалоговом окне **Выражение** разверните узел **Общие функции**и выберите **Математические**.  
  
4.  В списке **Элемент** дважды щелкните **Round**.  
  
5.  В списке **Категория** щелкните **Поля (выражения)**.  
  
6.  В списке **Значения** дважды щелкните **YTDPurchase**.  
  
7.  Если курсор не расположен сразу после `Fields!YTDPurchase.Value`, установите его в это положение.  
  
8.  Тип**-**  
  
9. Разверните узел **Общие функции** снова и выберите **Статистические**.  
  
10. В списке **Элемент** дважды щелкните **Avg**.  
  
11. В списке **Категория** щелкните **Поля (выражения)**.  
  
12. В списке **Значения** дважды щелкните **YTDPurchase**.  
  
13. Если курсор не расположен сразу после `Fields!YTDPurchase.Value`, установите его в это положение.  
  
14. Введите **, "Expressions"))**  
  
     Готовое выражение: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`  
  
15. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
16. В поле **Единица измерения состояний** выберите **Число**.  
  
17. В строке со стрелкой вниз нажмите кнопку **fx** справа от текстового поля для значения **Начало** .  
  
18. В диалоговом окне **Выражение** разверните узел **Общие функции**и выберите **Математические**.  
  
19. В списке **Элемент** дважды щелкните **Round**.  
  
20. В списке **Категория** щелкните **Поля (выражения)**.  
  
21. В списке **Значения** дважды щелкните **YTDPurchase**.  
  
22. Если курсор не расположен сразу после `Fields!YTDPurchase.Value`, установите его в это положение.  
  
23. Тип**-**  
  
24. Разверните узел **Общие функции** снова и выберите **Статистические**.  
  
25. В списке **Элемент** дважды щелкните **Avg**.  
  
26. В списке **Категория** щелкните **Поля (выражения)**.  
  
27. В списке **Значения** дважды щелкните **YTDPurchase**.  
  
28. Если курсор не расположен сразу после `Fields!YTDPurchase.Value`, установите его в это положение.  
  
29. Введите **, "Expressions")) < 0**  
  
     Готовое выражение: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`  
  
30. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
31. В текстовом поле для значения **Конец** введите **0**  
  
32. Щелкните строку, где находится горизонтальная стрелка, а затем щелкните **Удалить**.  
  
33. В строке со стрелкой вверх в поле **Начало** введите **0**  
  
34. Нажмите кнопку **fx** справа от текстового поля для значения **Конец** .  
  
35. В диалоговом окне **выражение** создайте выражение:`=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`  
  
36. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
37. Снова нажмите кнопку **ОК** , чтобы закрыть диалоговое окно **Свойства индикатора** .  
  
38. Нажмите кнопку **Выполнить** для предварительного просмотра отчета.  
  
##  <a name="8-make-the-report-a-green-bar-report"></a><a name="GreenBar"></a>8. Сделайте отчет отчетом «зеленая полоса»  
 Задайте в параметре цвет, который будет применен для чередования строк в отчете.  
  
#### <a name="to-add-a-parameter"></a>Добавление параметра  
  
1.  Щелкните **Конструктор** для возврата в режим конструктора.  
  
2.  На панели **Данные отчета** щелкните правой кнопкой мыши узел **Параметры** и выберите команду **Добавить параметр**.  
  
     Откроется диалоговое окно **Свойства параметра отчета** .  
  
3.  В поле **Подсказка**введите **Выберите цвет**  
  
4.  В поле **Имя**введите **RowColor**  
  
5.  На левой панели щелкните **Допустимые значения**.  
  
6.  Нажмите кнопку **Указать значения**.  
  
7.  Нажмите кнопку **Добавить**.  
  
8.  В поле **Метка** введите: **желтый** .  
  
9. В поле **Значение** введите **Yellow**  
  
10. Нажмите кнопку **Добавить**.  
  
11. В поле **Метка** введите **Green**  
  
12. В поле **Значение** введите **PaleGreen**  
  
13. Нажмите кнопку **Добавить**.  
  
14. В поле **Метка** введите **Blue**  
  
15. В поле **Значение** введите **LightBlue**  
  
16. Нажмите кнопку **Добавить**.  
  
17. В поле **Метка** введите **Pink**  
  
18. В поле **Значение** введите **Pink**  
  
19. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-apply-alternating-colors-to-detail-rows"></a>Применение цветов чередования строк детализации  
  
1.  Откройте на ленте вкладку **Вид** и убедитесь в том, что выбрано **Свойства**.  
  
2.  Щелкните ячейку данных для столбца **Name** и нажмите клавишу SHIFT.  
  
3.  Одну за другой щелкните все остальные ячейки в строке.  
  
4.  На панели свойств щелкните **BackgroundColor**.  
  
     Если на панели свойств свойства разбиты по категориям, свойство **BackgroundColor** находится в категории **Заливка**.  
  
5.  Нажмите стрелку вниз и выберите **Выражение**.  
  
6.  В диалоговом окне **Выражение** разверните узел **Общие функции** и выберите **Программный поток**.  
  
7.  В списке **Элемент** дважды щелкните **IIf**.  
  
8.  Разверните узел **Общие функции** и выберите **Статистические**.  
  
9. В списке **Элемент** дважды щелкните **RunningValue**.  
  
10. В списке **Категория** щелкните **Поля (выражения)**.  
  
11. В списке **Значения** дважды щелкните **FirstName**.  
  
12. Если курсор не расположен сразу после `Fields!FirstName.Value`, установите его в это положение, а затем введите **,**  
  
13. Разверните узел **Общие функции** и выберите **Статистические**.  
  
14. В списке **Элемент** дважды щелкните **Count**.  
  
15. Если курсор не расположен сразу после `Count(`, установите его в это положение.  
  
16. Удалите левую круглую скобку и введите **"Expressions")**  
  
    > [!NOTE]  
    >  Expressions — это имя набора данных, в котором нужно подсчитать строки данных.  
  
17. Разверните узел **Операторы** и выберите **Арифметические**.  
  
18. В списке **Элемент** дважды щелкните **Mod**.  
  
19. Если курсор не расположен сразу после `Mod`, установите его в это положение.  
  
20. Введите **2 =0,**  
  
    > [!IMPORTANT]  
    >  Перед числом 2 должен стоять пробел.  
  
21. Щелкните **Параметры** и в списке **Значения** дважды щелкните **RowColor**.  
  
22. Если курсор не расположен сразу после `Parameters!RowColor.Value`, установите его в это положение.  
  
23. Введите **, "белый")**  
  
     Готовое выражение: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`  
  
24. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="run-the-report"></a>Запустите отчет.  
  
1.  Если не открыта вкладка **Главная**, перейдите на вкладку **Главная**, чтобы вернуться в режим конструктора.  
  
2.  Нажмите кнопку **Выполнить**.  
  
3.  В раскрывающемся списке **Выбор цвета** выберите цвет для строк отчета, отличных от белых.  
  
4.  Нажмите кнопку **Просмотреть отчет**.  
  
     Отчет будет подготовлен к просмотру с выбранным цветом фона чередующихся строк.  
  
##  <a name="optional-format-date-column"></a><a name="DateFormat"></a>используемых Форматировать столбец даты  
 Отформатируйте столбец **Last Purchase**, который содержит даты.  
  
#### <a name="to-format-date-column"></a>Форматирование столбца даты  
  
1.  Щелкните **Конструктор** для возврата в режим конструктора.  
  
2.  Щелкните правой кнопкой мыши ячейку данных для столбца **Last Purchase** и выберите пункт **Свойства текстового поля**.  
  
3.  В диалоговом окне **Свойства текстового поля** щелкните **Число**, затем **Дата**, а затем выберите тип **\*1/31/2000**.  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-add-a-report-title"></a><a name="Title"></a>используемых Добавление заголовка отчета  
 Добавим заголовок отчета.  
  
#### <a name="to-add-a-report-title"></a>Добавление заголовка отчета  
  
1.  В области конструктора щелкните ссылку **Щелкните, чтобы добавить заголовок**.  
  
2.  Введите фразу **Сводка сравнения продаж** и щелкните за пределами текстового поля.  
  
3.  Щелкните правой кнопкой мыши текстовое поле **Сводка сравнения продаж** и выберите пункт **Свойства текстового поля**.  
  
4.  В диалоговом окне **Свойства текстового поля** нажмите кнопку **Шрифт**.  
  
5.  В списке **Размер** выберите **18пт**.  
  
6.  В списке **Цвет** выберите **Серый**.  
  
7.  Выберите **Полужирный** и **Курсив**.  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-save-the-report"></a><a name="Save"></a>используемых Сохранение отчета  
 Отчеты можно сохранять на сервере отчетов, в библиотеке SharePoint или на компьютере. Дополнительные сведения см. в разделе [Сохранение отчетов (построитель отчетов)](report-builder/saving-reports-report-builder.md).  
  
 В данном учебнике предусмотрено сохранение отчета на сервере отчетов. Если нет доступа к серверу отчетов, сохраните отчет на компьютере.  
  
#### <a name="to-save-the-report-to-a-report-server"></a>Сохранение отчета на сервере отчетов  
  
1.  На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.  
  
2.  Нажмите кнопку **Последние сайты и серверы**.  
  
3.  Выберите или введите имя сервера отчетов, для которого существует разрешение на сохранение отчетов.  
  
     Появится сообщение «Соединение с сервером отчетов». После того как соединение установлено, пользователю представляется содержимое папки, заданной администратором сервера отчетов в качестве места хранения отчетов по умолчанию.  
  
4.  В поле **Имя** замените имя по умолчанию на **Сводка сравнения продаж**.  
  
5.  Нажмите кнопку **Сохранить**.  
  
 Отчет будет сохранен на сервере отчетов. Имя сервера отчетов, с которым установлено соединение, будет отображено в строке состояния в нижней части окна.  
  
#### <a name="to-save-the-report-to-your-computer"></a>Сохранение отчета на компьютере  
  
1.  На кнопке **Построитель отчетов** нажмите кнопку **Сохранить как**.  
  
2.  Перейдите на **Рабочий стол**, откройте папку **Мои документы**или **Мой компьютер**и перейдите в папку, в которую нужно сохранить отчет.  
  
3.  В поле **Имя** замените имя по умолчанию на **Сводка сравнения продаж**.  
  
4.  Нажмите кнопку **Сохранить**.  
  
## <a name="see-also"></a>См. также:  
 [Выражения (построитель отчетов и службы SSRS)](report-design/expressions-report-builder-and-ssrs.md)   
 [Примеры выражений (построитель отчетов и службы SSRS)](report-design/expression-examples-report-builder-and-ssrs.md)   
 [Индикаторы &#40;построитель отчетов и службы SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md)   
 [Изображения, текстовые поля, прямоугольники и линии &#40;построитель отчетов и SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md)   
 [Таблицы &#40;построитель отчетов и службы SSRS&#41;](report-design/tables-report-builder-and-ssrs.md)   
 [Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](report-data/report-datasets-ssrs.md)  
  
  
