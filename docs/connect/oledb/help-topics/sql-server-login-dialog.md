---
title: Диалоговое окно "Вход в сервер SQL" (OLE DB) | Документация Майкрософт
description: Использование диалогового окна входа SQL Server
ms.custom: ''
ms.date: 10/11/2019
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
ms.author: v-beaziz
author: bazizi
ms.openlocfilehash: d35c339798b4385cb903d8a4a83f13184bbf4db3
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2020
ms.locfileid: "72381746"
---
# <a name="sql-server-login-dialog-box"></a>Диалоговое окно входа SQL Server
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

При попытке подключения без указания достаточной информации Драйвер OLE DB отображает диалоговое окно **	Вход на SQL Server**.

> [!NOTE]  
> Поведение запроса диалоговое окно входа SQL Server управляется свойством инициализации `DBPROP_INIT_PROMPT`. Дополнительные сведения см. в разделе:
> - [Свойства инициализации и авторизации](../ole-db-data-source-objects/initialization-and-authorization-properties.md)
> - [Руководство по программированию OLE DB](https://go.microsoft.com/fwlink/?linkid=2067702)

![Снимок экрана диалогового окна входа SQL Server](../media/sql-server-login-dialog.png)

## <a name="options"></a>Параметры
|Параметр|Description|
|---   |---        |
|Сервер|Имя экземпляра SQL Server в сети. Выберите имя сервера/экземпляра из списка либо введите его в поле **Server** (Сервер). Также на клиентском компьютере можно создать серверный псевдоним с помощью средства **Диспетчер конфигурации SQL Server** и ввести это имя в поле **Server** (Сервер). <br/><br/>При использовании того же компьютера, на котором установлен SQL Server, можно ввести "(локальный)". Затем вы сможете подключиться к локальному экземпляру SQL Server. Это возможно даже в том случае, если запущена несетевая версия SQL Server.<br/><br/>Дополнительные сведения об именах серверов для разных типов сетей см. в статье [Руководство по установке SQL Server](https://go.microsoft.com/fwlink/?linkid=2067541)|
|Режим проверки подлинности|Вы можете выбрать из раскрывающегося списка следующие параметры проверки подлинности:<br/><ul><li>`Windows Authentication:` проверка подлинности в SQL Server с использованием учетных данных пользователя Windows, вошедшего в систему.</li><li>`SQL Server Authentication:` проверка подлинности с помощью имени для входа и пароля.</li><li>`Active Directory - Integrated:` встроенная проверка подлинности с помощью идентификатора Azure Active Directory. Этот режим можно также использовать для проверки подлинности Windows в SQL Server.</li><li>`Active Directory - Password:` проверка подлинности по идентификатору и паролю пользователя с использованием идентификатора Azure Active Directory.</li><li>`Active Directory - Universal with MFA support:` встроенная проверка подлинности с использованием идентификатора Azure Active Directory. Этот режим поддерживает Многофакторную идентификацию Microsoft Azure (MFA).</li></ul>|
|Имя участника-службы сервера|Если используется доверительное соединение, можно указать имя участника-службы для соединения с основным сервером.|
|Идентификатор входа|Указывает имя для входа, которое будет использоваться при соединении. Текстовое поле для имени входа доступно только в том случае, если для параметра `Authentication Mode` задано значение `SQL Server Authentication`, `Active Directory - Password` или `Active Directory - Universal with MFA support`.|
|Пароль|Указывает пароль, используемый для соединения. Текстовое поле для пароля входа доступно только в том случае, если для параметра `Authentication Mode` задано значение `SQL Server Authentication` или `Active Directory - Password`.|
|Параметры|Отображает или скрывает группу **Параметры**. Кнопка **Options** (Параметры) включена, если поле **Server** (Сервер) содержит значение.|
|Изменить пароль|Установив флажок, вы включаете текстовые поля **Новый пароль** и **Подтвердить новый пароль**.|
|Новый пароль|В этом поле указывается новый пароль.|
|Подтверждение нового пароля|В этом поле новый пароль указывается второй раз, для подтверждения.|
|База данных|Выберите базу данных по умолчанию, которая будет использоваться для соединения, или введите ее имя. Данная настройка переопределяет базу данных по умолчанию, указанную для имени входа на сервере. Если база данных не была указана, соединение использует базу данных по умолчанию, указанную для имени входа на сервере.|
|Зеркальный сервер|Указывает имя партнера по обеспечению отработки отказа базы данных, для которой будет включено зеркальное отображение.|
|Имя участника-службы зеркала|Также можно указать имя участника-службы для зеркального сервера (необязательно). Имя участника-службы зеркального сервера используется для взаимной проверки подлинности клиента и сервера.|
|Язык|Указывает национальный язык, который будет использоваться в системных сообщениях SQL Server. Этот язык должен быть установлен на компьютере с SQL Server. Данная настройка переопределяет язык по умолчанию, указанный для имени входа на сервере. Если язык не указан, соединение использует язык по умолчанию, указанный для имени входа на сервере.|
|Имя приложения|Позволяет указать имя приложения, которое будет храниться в строке этого подключения в столбце **program_name** представления **sys.sysprocesses**.|
|Идентификатор рабочей станции|Позволяет указать идентификатор рабочей станции, который будет храниться в строке этого подключения в столбце **hostname** представления **sys.sysprocesses**.|
|Использовать устойчивое шифрование данных|Если этот флажок установлен, данные, передаваемые через подключение, шифруются.|
|Надежный сертификат сервера|Если этот флажок установлен, сертификат сервера будет проверен. Сертификат сервера должен иметь правильное имя узла сервера и быть выдан доверенным центром сертификации.|

> [!NOTE]  
> При использовании режимов `Windows Authentication` или `SQL Server Authentication` **Сертификат доверенного сервера** учитывается только при включенной опции **Использовать усиленное шифрование данных**.

## <a name="next-steps"></a>Дальнейшие действия
- [Проверка подлинности в Azure Active Directory](../features/using-azure-active-directory.md) с помощью драйвера OLE DB.
- Задайте сведения о соединении, используя [универсальный канал передачи данных (UDL)](data-link-pages.md).