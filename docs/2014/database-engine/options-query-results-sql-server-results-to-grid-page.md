---
title: Параметры (результаты запроса — страница «SQL Server-Results to Grid») | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLResultsToGrid
ms.assetid: f88a0f5c-e800-473b-ae23-c3943de5ed63
author: rothja
ms.author: jroth
ms.openlocfilehash: 5678c146dfffc4cf907e0050b2017208a0c7f141
ms.sourcegitcommit: 9ee72c507ab447ac69014a7eea4e43523a0a3ec4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84930057"
---
# <a name="options-query-results-sql-server-results-to-grid-page"></a>Параметры (результаты запроса — страница «SQL Server-Results to Grid»)
  Используйте эту страницу, чтобы указать параметры отображения результирующего набора запроса в формате сетки. Изменения этих параметров применяются только к новым запросам [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]. Чтобы изменить параметры для текущих запросов, в меню **запрос** выберите пункт **Параметры запроса** или щелкните правой кнопкой мыши в [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] окне запроса и выберите пункт **Параметры запроса**. На левой панели диалогового окна **Параметры запроса** в списке **Результаты**выберите пункт **Сетка**.  
  
## <a name="ui-element-list"></a>Список элементов пользовательского интерфейса  
 **Включение запроса в результирующий набор**  
 Возвращает текст запроса как часть вывода запроса.  
  
 **Включать заголовки столбцов при копировании или сохранении результатов**  
 Выберите этот флажок, чтобы включить заголовки столбца при копировании результатов в буфер обмена или сохранении в файл. Снимите этот флажок, если нужно, чтобы сохраненные или скопированные данные результатов состояли только из данных без заголовков столбцов.  
  
 **Сбросить результаты после выполнения**  
 Препятствует отображению результатов запроса на просматриваемой панели. Результаты отклоняются сразу после завершения. Использование этого параметра позволяет сэкономить память.  
  
 **Отобразить результаты на отдельной вкладке**  
 Установить этот флажок, чтобы вывести результирующий набор в новой вкладке, а не в окне документа запроса.  
  
 **Открыть вкладку результатов после выполнения запроса**  
 Нажмите для автоматической установки экранного фокуса на панели результатов после исполнения запроса.  
  
 **Максимальное число полученных символов**  
 **Данные не в формате XML**:  
  
 Введите число от 1 до 65 535, чтобы указать максимальное число символов, отображаемых в каждой ячейке.  
  
> [!NOTE]  
>  Указание слишком большого числа символов может привести к тому, что результирующий набор будет отображаться усеченным. Максимальное число символов, отображаемых в каждой ячейке, зависит от размера шрифта. Высокое значение в этом окне может привести к нехватке памяти для среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] и снижению производительности системы при возвращении больших результирующих наборов.  
  
 **XML-данные**:  
  
 Выберите **1 МБ**, **2 МБ**или **5 МБ**. Выберите пункт **Без ограничений** , чтобы вывести все символы.  
  
 **По умолчанию**  
 Позволяет вернуть исходные значения по умолчанию для всех параметров на данной странице.  
  
  
