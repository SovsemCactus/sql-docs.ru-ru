---
title: Диалоговое окно "Открытие файла" | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: conceptual
f1_keywords:
- vs.openfile
- vs.openproject
ms.assetid: 3e01b9f5-2b0a-4fb3-9da8-984d27d17b8a
caps.latest.revision: 11
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: fa90faefc21d610be9431faa7e4d10a43797d3b2
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37249844"
---
# <a name="open-file-dialog-box"></a>Диалоговое окно «Открытие файла»
  Используйте диалоговое окно **Открытие файла** для открытия существующего файла. Это диалоговое окно можно также использовать для повторного открытия уже открытого файла с другими параметрами языковой кодировки.  
  
 Для доступа к этому диалоговому окну выберите пункт **Открыть** в меню **Файл** , а затем выберите **Файл**. Это диалоговое окно отображается также при открытии файлов с помощью других элементов интерфейса, например диалогового окна **Внешние средства** . В меню **Файл** выберите команду **Открыть**и пункт **Решение или проект** , чтобы открыть похожее диалоговое окно **Открытие проекта** .  
  
> [!NOTE]  
>  Прежде чем открыть проект или компонент в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], определите, заслуживает ли его код доверия. Даже само действие по открытию проекта или компонента в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] может привести к выполнению его кода в доверенном процессе на локальном компьютере.  
  
## <a name="option"></a>Параметр  
 **Папка**  
 Найти существующую папку проектов в выпадающем меню. Если выбрать папку в этом списке, в основной панели отображается содержимое папки.  
  
## <a name="my-places-bar"></a>Моя панель позиций  
 **Рабочий стол**  
 Отображает файлы и папки, находящиеся на рабочем столе.  
  
 **Мои проекты**  
 Отображает файлы и папки, находящиеся в папке **Проекты** текущего пользователя.  
  
 **Мой компьютер**  
 Отображает содержимое гибкого, жесткого дисков и дисковода для компакт-дисков.  
  
## <a name="folder-list"></a>Список папок  
 **Имя файла**  
 Используйте этот параметр для фильтрации отображаемых файлов и папок. Введите полное или частичное имя файла, которое будет использоваться фильтром. В качестве символа-шаблона можно использовать символ звездочки (*).  
  
 **Тип файлов**  
 Используйте этот параметр для фильтрации содержимого папки или каталога, выбранного в списке «Папки», по определенному типу файлов.  
  
 **Параметры диалоговых окон «Открыть с помощью» и «Кодировка»**  
 Чтобы воспользоваться диалоговым окном **Открыть с помощью** для указания редактора целевого файла, щелкните маленький прямоугольник справа от кнопки **Открыть** и выберите команду **Открыть с помощью**. В случае необходимости можно также указать схему языковой кодировки, применяемую при открытии выбранного файла. Для этого выберите одну из программ в списке, который содержит слова «**в кодировке**», и выберите команду **Открыть** , чтобы отобразить диалоговое окно **Кодировка**. Эта кнопка доступна не всегда.  
  
## <a name="toolbar"></a>Панель инструментов  
 **Назад**  
 Позволяет вернуться к последней просмотренной папке, дисководу или расположению в Интернете.  
  
 **На один уровень вверх**  
 Позволяет перейти в дереве к папке, находящейся на ближайшем вышестоящем уровне в древовидном представлении.  
  
 **Выполнить поиск на веб-узлах**  
 Эта кнопка недоступна.  
  
 **Удаление**  
 Удаляет выбранные файлы и папки из хранилища.  
  
 **Создать папку**  
 Отображает диалоговое окно **Создать папку** . Используйте этот параметр, чтобы создать новую вложенную папку в папке, выбранной в раскрывающемся списке **Папка** .  
  
## <a name="views"></a>Представления  
 Содержит варианты упорядочивания и просмотра содержимого элемента в раскрывающемся списке **Представления** .  
  
 **Эскизы страниц**  
 Отображает уменьшенные представления элементов, находящихся на панели отображения.  
  
 **Плитка**  
 Отображает файлы и папки в виде крупных значков.  
  
 **Значки**  
 Отображает файлы и папки в виде мелких значков.  
  
 **Список**  
 Отображает файлы и папки в формате списка.  
  
 **Сведения**  
 Отображает для файлов и папок имя, размер, тип и дату последнего изменения в формате списка. Чтобы отсортировать список по конкретной характеристике, щелкните заголовок относящегося к ней столбца.  
  
 **Веб-представление**  
 Эта команда недоступна.  
  
## <a name="tools"></a>Инструменты  
 Выберите действие, применяемое к элементу, выделенному на панели «Содержимое».  
  
 **Удаление**  
 Удаляет выбранные файлы или папки из хранилища.  
  
 **Подключить сетевой диск**  
 Открывает диалоговое окно **Подключить сетевой диск** .  
  
  