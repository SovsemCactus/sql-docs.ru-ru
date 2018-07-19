---
title: Добавление или удаление верхнего или нижнего колонтитула страницы (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 72988623-fee8-4a05-9f72-8fcb8e668576
caps.latest.revision: 5
author: maggiesMSFT
ms.author: maggies
manager: craigg
ms.openlocfilehash: 6e529c7ebba36bc7fb9c482492ba22c05aff4ce5
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37323654"
---
# <a name="add-or-remove-a-page-header-or-footer-report-builder-and-ssrs"></a>Добавление или удаление верхнего или нижнего колонтитула страницы (построитель отчетов и службы SSRS)
  К верхним или нижним колонтитулам страниц можно добавить статический текст, изображения, линии, прямоугольники и границы. Если в заголовке или нижнем колонтитуле необходимо разместить переменные или вычисляемые данные, поместите выражения и связанные с данными изображения в текстовом поле.  
  
> [!NOTE]  
>  Всякий модуль подготовки отчетов обрабатывает колонтитулы по-разному. Дополнительные сведения см. в разделах [Верхние и нижние колонтитулы страницы (построитель отчетов и службы SSRS)](page-headers-and-footers-report-builder-and-ssrs.md) и [Разбиение на страницы в службах Reporting Services (построитель отчетов и службы SSRS)](pagination-in-reporting-services-report-builder-and-ssrs.md).  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-page-header-or-footer"></a>Добавление верхнего или нижнего колонтитула  
  
1.  Откройте отчет.  
  
2.  В области конструктора щелкните правой кнопкой мыши отчет, укажите пункт **Вставить**и выберите **Верхний колонтитул** или **Нижний колонтитул**.  
  
> [!NOTE]  
>  Параметры **Верхний колонтитул** или **Нижний колонтитул** появляются, только если верхний или нижний колонтитул еще не являются частью отчета.  
  
### <a name="to-configure-a-page-header-or-footer"></a>Настройка верхнего или нижнего колонтитула  
  
1.  В области конструктора щелкните правой кнопкой мыши верхний или нижний колонтитул.  
  
2.  Укажите пункт **Вставить**, а затем выберите один из следующих элементов, чтобы добавить его в область верхнего или нижнего колонтитула:  
  
    -   **текстовое поле;**  
  
    -   **Линия**  
  
    -   **прямоугольник;**  
  
    -   **Изображение**  
  
3.  Щелкните правой кнопкой мыши верхний колонтитул и выберите пункт **Свойства верхнего колонтитула** , чтобы добавить границы, фоновое изображение и цвета либо настроить ширину верхнего колонтитула. Затем нажмите кнопку **ОК**.  
  
4.  Щелкните правой кнопкой мыши нижний колонтитул и выберите пункт **Свойства нижнего колонтитула** , чтобы добавить границы, фоновое изображение и цвета либо настроить ширину нижнего колонтитула. Затем нажмите кнопку **ОК**.  
  
### <a name="to-remove-a-page-header-or-footer"></a>Удаление верхнего или нижнего колонтитула  
  
1.  Откройте отчет.  
  
2.  В области конструктора щелкните правой кнопкой мыши верхний или нижний колонтитул и выберите команду **Удалить**.  
  
> [!NOTE]  
>  При удалении колонтитула он удаляется из отчета. Любые элементы, которые ранее добавлялись в колонтитулы, не появятся после последующего создания колонтитула.  
  
## <a name="see-also"></a>См. также  
 [И нижние колонтитулы страницы &#40;построитель отчетов и службы SSRS&#41;](page-headers-and-footers-report-builder-and-ssrs.md)  
  
  