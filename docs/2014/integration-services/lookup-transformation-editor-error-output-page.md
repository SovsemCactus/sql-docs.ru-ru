---
title: Редактор преобразования "Уточняющий запрос" (страница "вывод ошибок") | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.erroroutput.f1
ms.assetid: 15d53bb0-8be1-46fb-b459-04a397e75fac
author: janinezhang
ms.author: janinez
ms.openlocfilehash: b1dab84084c612c73bf993ece66646a5b28cf48d
ms.sourcegitcommit: f71e523da72019de81a8bd5a0394a62f7f76ea20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84951214"
---
# <a name="lookup-transformation-editor-error-output-page"></a>Редактор преобразования «Уточняющий запрос» (страница «Вывод ошибок»)
  Страница **Вывод ошибок** диалогового окна **Редактор преобразования «Уточняющий запрос»** используется для задания параметров обработки ошибок.  
  
 Дополнительные сведения о преобразовании «Уточняющий запрос» см. в разделе [Lookup Transformation](data-flow/transformations/lookup-transformation.md).  
  
## <a name="options"></a>Варианты  
 **Ввод-вывод**  
 Просмотрите имя входных данных.  
  
 **Столбец**  
 Не используется.  
  
 **Error**  
 Укажите, какой тип ошибки должен появляться при обработке строк, не имеющих совпадающих записей в эталонном наборе данных:  
  
-   не учитывать сбой и направить строки на выход;  
  
-   перенаправлять строки в вывод ошибок;  
  
-   завершить работу компонента с ошибкой.  
  
 Этот параметр недоступен при выборе параметра **Перенаправлять строки в выход несовпадающих строк** в списке **Укажите метод обработки строк без совпадающих элементов** . Этот список находится на странице **Общие** диалогового окна **Редактор преобразования «Уточняющий запрос»** .  
  
 **См. также:** [Обработка ошибок в данных](data-flow/error-handling-in-data.md)  
  
 **Усечение**  
 Задайте действие при усечении данных:  
  
-   пропустить ошибку;  
  
-   перенаправить строку;  
  
-   завершить работу компонента с ошибкой.  
  
 **Описание**  
 Просмотрите описание операции.  
  
 **Присвоить указанное значение выбранным ячейкам**  
 Укажите действие, которое необходимо применить ко всем выбранным ячейкам при возникновении ошибки или усечения:  
  
-   пропустить ошибку;  
  
-   перенаправить строку;  
  
-   завершить работу компонента с ошибкой.  
  
 **Применить**  
 Применить параметр обработки ошибок к выбранным ячейкам.  
  
## <a name="see-also"></a>См. также:  
 [Справочник по сообщениям об ошибках служб Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
