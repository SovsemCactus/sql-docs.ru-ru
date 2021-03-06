---
title: Страница "Общие свойства", элементы отчета (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 93ddce72-31f1-42f7-abd5-8191acbb00c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: aa3f8b6ec0cd81f1a29ea3262bd3ec52dd8158ae
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2020
ms.locfileid: "66109089"
---
# <a name="general-properties-page-report-parts-report-manager"></a>Страница «Общие свойства» — «элементы отчета» (диспетчер отчетов)
  Страница «Свойства» используется для просмотра и управления общими свойствами элемента отчета.  
  
 Диспетчер отчетов не позволяет просматривать или изменять внешний вид и функциональные возможности элемента отчета. Чтобы изменить проект, необходимо использовать средство разработки для открытия и изменения проекта и повторно опубликовать его на сервере.  
  
## <a name="navigation"></a>Навигации  
 Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.  
  
###### <a name="to-open-the-properties-page-for-a-report-part"></a>Открытие страницы свойств для элемента отчета  
  
1.  Откройте диспетчер отчетов и найдите элемент отчета, для которого необходимо настроить свойства.  
  
2.  Подведите курсор к элементу отчета и щелкните стрелку раскрывающегося списка.  
  
3.  В раскрывающемся списке выберите **Управление**. Откроется страница «Общие свойства».  
  
## <a name="options"></a>Параметры  
 **Дата изменения**  
 Дата и время последнего изменения свойств элемента отчета на сервере или публикации на сервере новой версии элемента отчета. Только для чтения.  
  
 **Кем изменено**  
 Имя пользователя, который последним изменил элемент отчета. Только для чтения.  
  
 **Дата создания**  
 Дата и время первоначальной публикации элемента отчета на сервере. Только для чтения.  
  
 **Кем создано**  
 Имя пользователя, который первоначально создал элемент отчета. Только для чтения.  
  
 **Размер**  
 Размер файла элемента отчета. Только для чтения.  
  
 **Имя**  
 Имя, введенное для обозначения элемента отчета.  
  
 **Описание**  
 Введите сведения об элементе отчета. Это описание отображается на странице «Содержимое» диспетчера отчетов. По тексту описания может выполняться поиск, если необходимо найти элементы отчета из средства разработки отчета.  
  
 **Скрыть при отображении в виде списка**  
 Выберите этот параметр, чтобы скрыть элемент отчета от пользователей, которые работают в диспетчере отчетов в режиме списка. Режим списка — формат представления по умолчанию при просмотре иерархии папок сервера отчетов. Элементы можно скрывать в формате списка, но нельзя скрывать в формате таблицы. Чтобы ограничить доступ к элементу, необходимо создать назначение ролей.  
  
 **Type**  
 Тип элемента отчета. Только для чтения.  
  
 **Применить**  
 Сохраните изменения.  
  
 **Удаление**  
 Нажмите, чтобы удалить элемент отчета из базы данных сервера отчетов. Удаление элемента отчета с сервера не является препятствием для подготовки к просмотру существующих отчетов, к которым был добавлен этот элемент отчета.  
  
 **Переместить**  
 Нажмите эту кнопку, чтобы открыть страницу «Перемещение элементов» для перемещения элемента отчета в иерархии папок сервера отчетов. Дополнительные сведения см. в разделе [Страница "перемещение элементов" &#40;диспетчер отчетов&#41;](../../2014/reporting-services/move-items-page-report-manager.md).  
  
 **Скачать**  
 Извлечение копии определения элемента отчета, чтобы сохранить ее в виде RSC-файла. RSC-файл может передаваться в папку сервера отчетов или использоваться для замены существующего элемента отчета в папке сервера отчетов.  
  
 **Восстановить**  
 Замена одного определения элемента отчета другим из RSC-файла.  
  
## <a name="see-also"></a>См. также  
 [Управление элементами отчета](report-design/managing-report-parts.md)   
 [Диспетчер отчетов (службы Reporting Services в основном режиме)](../../2014/reporting-services/report-manager-ssrs-native-mode.md)   
 [Страница "содержимое" &#40;диспетчер отчетов&#41;](../../2014/reporting-services/contents-page-report-manager.md)   
 [Элементы отчета &#40;построитель отчетов и службы SSRS&#41;](report-parts-report-builder-and-ssrs.md)   
 [Справка F1 диспетчер отчетов](../../2014/reporting-services/report-manager-f1-help.md)   
 [Элементы отчета и наборы данных в построителе отчетов](report-data/report-parts-and-datasets-in-report-builder.md)  
  
  
