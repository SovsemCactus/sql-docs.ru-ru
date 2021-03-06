---
title: Пошаговое руководство по диаграмме кластера (надстройки интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Visio shapes, cluster
- diagram, cluster
- shapes, data mining
- shapes, cluster
- data mining layout toolbar
ms.assetid: 761bef6a-37d4-4b19-944e-f2aadc75a242
author: minewiskan
ms.author: owend
ms.openlocfilehash: 578b5b8e55fd3ae660db985eed2e608667dc768b
ms.sourcegitcommit: 2f166e139f637d6edfb5731510d632a13205eb25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84527490"
---
# <a name="cluster-diagram-walkthrough-data-mining-add-ins"></a>Пошаговое руководство по диаграмме кластеров (надстройки интеллектуального анализа данных)
  После создания модели кластеризации ее можно импортировать в Visio с помощью фигуры **кластера** , а затем продолжить настройку и расширение макета. **Фигуры интеллектуального анализа данных для Visio** включают следующие пользовательские элементы управления для работы с диаграммами интеллектуального анализа данных.  
  
-   создание элементов управления для диаграммы кластеров.  
  
     Эти параметры являются частью **мастера кластеров** , который запускается при перетаскивании фигуры в рабочую область Visio.  
  
-   Панель инструментов **макета интеллектуального анализа данных**  
  
     Эти параметры добавляется в рабочую область Visio для последующей работы с фигурами интеллектуального анализа данных. Параметры различаются в зависимости от используемого типа модели интеллектуального анализа данных.  
  
## <a name="build-a-cluster-diagram"></a>Создание диаграммы кластеров  
 Это пошаговое руководство демонстрирует, как можно создать и настроить диаграмму кластеризации в Visio.  
  
 Чтобы следовать описанным шагам, следует иметь готовую модель кластеризации. Если модель отсутствует, используйте [Мастер кластеров &#40;мастере надстроек интеллектуального анализа данных для Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md) и создайте модель с помощью набора обучающих данных в образце книги, используя все значения по умолчанию.  
  
#### <a name="use-the-cluster-visio-shape-wizard"></a>Используйте мастер фигур Visio в кластере  
  
1.  Если в списке **фигур** не отображаются **фигуры интеллектуального анализа данных Майкрософт** , щелкните **другие фигуры**, выберите **Открыть набор элементов**и откройте шаблон из расположения установки по умолчанию.  
  
     \<drive>: \Program files\Microsoft SQL Server 2012, надстройки DM  
  
2.  Перетащите фигуру **кластера** на страницу.  
  
3.  На странице приветствия **мастера фигур Visio в кластере**нажмите кнопку **Далее**.  
  
4.  На странице **Выбор источника данных** **мастера кластеров**выберите подключение к [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] серверу, содержащему модели интеллектуального анализа данных, которые необходимо визуализировать.  
  
5.  Выберите подходящую модель интеллектуального анализа данных и нажмите кнопку **Далее**.  
  
     Чтобы убедиться, что выбрана модель кластеризации, проверьте описание на панели **свойств** .  
  
6.  Если подключение установлено успешно, на странице **Параметры диаграммы кластеров**выберите тип диаграммы кластеров для включения в презентацию Visio:  
  
     **Отображать только фигуры кластеров**  
     Данный параметр создает простую диаграмму кластеров, при этом каждый кластер может отображаться в виде прямоугольника или любой другой формы, которую вы можете выбрать.  
  
     **Отображать кластеры с диаграммой характеристик**  
     Этот параметр позволяет создать диаграмму, аналогичную предыдущей, однако внутри ее форм представлены гистограммы, описывающие характеристики кластера.  
  
     ![Пример диаграммы характеристик кластера в Visio](media/dm13-visio-cluster-samplecharshape.gif "Пример диаграммы характеристик кластера в Visio")  
  
     **Отображать кластеры с диаграммой сравнения**  
     Этот параметр создает точно такую же схему, что и диаграмма кластеров, однако в ней приводится список характеристик текущего кластера, которыми он наиболее сильно отличается от других кластеров.  
  
     Можно переключиться на другой тип диаграммы после того, как мастер создаст диаграмму. Для этого щелкните кластер правой кнопкой мыши и выберите новый тип диаграммы. Пока выберите параметр **Показывать кластеры с диаграммой характеристик**.  
  
7.  Оставьте параметр, **число строк в диаграмме**, равное 5.  
  
     Этот параметр не изменяет число кластеров в модели. Он просто ограничивает количество атрибутов, которые могут отображаться как функции каждого кластера.  
  
     Однако этот параметр действует как фильтр для данных диаграммы, поэтому вы не можете увеличить число элементов позже.  
  
8.  Нажмите кнопку **Дополнительно**.  
  
     Диалоговое окно **Параметры кластера** используется для настройки внешнего вида фигур, используемых на схеме. Можно изменить цвета, используемые на диаграмме, и фигуру, используемую для кластеров.  
  
     Элемент управления " **Переменная заливки** " не работает в Office 2013.  
  
     ![нажмите кнопку «Дополнительно», чтобы выбрать цвета фигуры](media/dm13-visio-clusteroptions-advanced.gif "нажмите кнопку «Дополнительно», чтобы выбрать цвета фигуры")  
  
     **Совет.** Некоторые цвета можно изменить позже с помощью тем Visio и элементов управления редактированием фигур. Однако темы Visio также переопределяют некоторые из выбранных цветов, поэтому рекомендуется начать с цветами по умолчанию и применять изменения постепенно.  
  
9. Нажмите кнопку **Готово** , чтобы создать диаграмму.  
  
     Мастер извлекает сведения из модели интеллектуального анализа данных, отображает фигуры и заполняет каждый кластер атрибутами и значениями.  
  
     ![сеть зависимостей](media/dm13-visiodepnet-defaultgraph.gif "сеть зависимостей")  
  
## <a name="explore-and-modify-the-finished-diagram"></a>Просмотр и изменение законченной диаграммы  
 После завершения создания диаграммы можно продолжить настройку внешнего вида с помощью элементов управления Visio, как показано в следующем примере.  
  
 ![диаграмма кластеров, настроенная с помощью Visio](media/dm13-visio-clustercomplete1.gif "диаграмма кластеров, настроенная с помощью Visio")  
  
 Все основные формы кластеров формируются мастером. Используйте следующие средства для обновления и персонализации диаграммы.  
  
1.  Перетащите ползунок в элементе управления " **Параметры кластера** ", чтобы отфильтровать более слабые связи и упростить диаграмму.  
  
2.  Используйте параметр **страница повторного макета** Visio, чтобы поэкспериментировать с различными структурами кластеров.  
  
3.  Используйте параметр **соединители** на вкладке **конструктор** , чтобы изменить стиль соединителя так, чтобы строки пересекается с кластерами.  
  
4.  Щелкните ленту **надстройки** , а затем откройте одну из настраиваемых панелей инструментов, используемых для работы с диаграммами интеллектуального анализа данных.  
  
     **Макет**  
     Оптимизирует расположение кластеров для улучшения их размещения на текущей странице.  
  
     **Изменение размера страницы**  
     Этот элемент управления был предназначен для предыдущих версий HTML. Используйте элементы управления изменением размера страницы Visio.  
  
     **Описание**  
     Если выбран кластер, щелкните этот параметр, чтобы отобразить сведения о кластере.  
  
     ![щелкните «Описание», чтобы получить подробные сведения о кластере](media/dm13-visio-cluster-description-control.gif "щелкните «Описание», чтобы получить подробные сведения о кластере")  
  
     **Интенсивность ребра**  
     Указывает степень достоверности для линий, соединяющих кластеры.  
  
     Однако, если вы примените любое особое форматирование, отличное от форматирования по умолчанию мастера, в том числе с использованием некоторых фонов, возможно, эти цифры будут невидимы.  
  
     **Ползунок**  
     Фильтрует строки между кластерами. Перемещение ползунка вверх удаляет все, кроме наиболее важных взаимосвязей.  
  
     **Заливка**  
     Этот элемент управления не работает в Office 2013.  
  
5.  Используйте элемент управления **панорамой и масштабом** в области **задач** на ленте **представления** Visio, чтобы сосредоточиться на наборе кластеров и перемещаться по схеме.  
  
6.  Щелкните правой кнопкой мыши любой кластер, чтобы увидеть параметры, характерные для формы кластера.  
  
    -   Изменение стиля диаграммы.  
  
    -   Добавление диаграммы характеристик кластера.  
  
    -   Добавление диаграммы сравнения кластеров.  
  
## <a name="see-also"></a>См. также:  
 [Устранение неполадок диаграмм интеллектуального анализа данных Visio &#40;SQL Server надстроек интеллектуального анализа данных&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md)  
  
  
