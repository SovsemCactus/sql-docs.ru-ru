---
title: Масштабирование параллельных сценариев
description: Настройте параллельное или одновременное выполнение сценариев R и Python в пуле учетных записей пользователей для масштабирования Служб машинного обучения SQL Server.
ms.prod: sql
ms.technology: machine-learning
ms.date: 09/25/2019
ms.topic: conceptual
author: dphansen
ms.author: davidph
ms.custom: seo-lt-2019
monikerRange: =sql-server-2016||=sql-server-2017||=sqlallproducts-allversions
ms.openlocfilehash: 430af4eb1127ab5b924b2429e166f68e2dffa334
ms.sourcegitcommit: 68583d986ff5539fed73eacb7b2586a71c37b1fa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/04/2020
ms.locfileid: "81118807"
---
# <a name="scale-concurrent-execution-of-external-scripts-in-sql-server-machine-learning-services"></a>Масштабирование параллельного выполнения внешних сценариев в Службах машинного обучения SQL Server
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

Узнайте о рабочих учетных записях для Служб машинного обучения SQL Server и о том, как изменить конфигурацию по умолчанию, чтобы масштабировать количество параллельных выполнений внешних сценариев.

Чтобы *могла выполнять задачи, в процессе установки Служб машинного обучения создается новый*пул учетных записей пользователей[!INCLUDE[rsql_launchpad](../../includes/rsql-launchpad-md.md)] Windows. Эти рабочие учетные записи предназначены для того, чтобы изолировать работу пользователей SQL Server, которые одновременно выполняют внешние сценарии.

> [!Note]
> В SQL Server 2019 в группе **SQLRUserGroup** теперь содержится только один член, которым является единственная учетная запись службы панели запуска SQL Server, а не несколько рабочих учетных записей. В этой статье описываются рабочие учетные записи для SQL Server 2016 и 2017.

## <a name="worker-account-group"></a>Группа рабочих учетных записей

Группа учетных записей Windows создается при установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] для каждого экземпляра, на котором установлены и включены службы машинного обучения.

- В экземпляре по умолчанию именем группы будет **SQLRUserGroup**. Это имя не зависит от того, используется ли Python, R или они оба.
- В именованном экземпляре имя группы по умолчанию имеет в качестве суффикса имя экземпляра, например **SQLRUserGroupИмя_экземпляра**.

По умолчанию пул учетных записей пользователей содержит 20 учетных записей. В большинстве случаев 20 учетных записей более, чем достаточно для поддержки задач машинного обучения, но при необходимости это количество можно изменить. Максимальное число учетных записей — 100.

- В экземпляре по умолчанию отдельным учетным записям присваиваются имена от **MSSQLSERVER01** и до **MSSQLSERVER20**.
- Для именованного экземпляра отдельным учетным записям присваиваются имена на основе экземпляра: например, **Имя_экземпляра01** и до **Имя_экземпляра20**.

Если в нескольких экземплярах используется машинное обучение, компьютер будет иметь несколько групп пользователей. Группы не могут совместно использоваться разными экземплярами.

<a name = "HowToChangeGroup"> </a>

## <a name="number-of-worker-accounts"></a>Число рабочих учетных записей

Чтобы изменить число пользователей в пуле учетных записей, необходимо изменить свойства службы [!INCLUDE[rsql_launchpad](../../includes/rsql-launchpad-md.md)], как описано ниже.

Пароли, связанные с каждой учетной записью пользователя, генерируются случайным образом, но при необходимости после создания учетных записей их можно изменить.

1. Откройте диспетчер конфигурации SQL Server и выберите **Службы SQL Server**.
2. Дважды щелкните службу панели запуска SQL Server и остановите службу, если она запущена.
3.  Убедитесь, что на вкладке **Служба** установлен автоматический режим запуска. Внешние сценарии нельзя запустить, если панель запуска не запущена.
4.  Щелкните вкладку **Дополнительно** и при необходимости измените значение параметра **Число внешних пользователей**. Этот параметр определяет, сколько различных пользователей SQL могут запускать сеансы внешних сценариев одновременно. Значение по умолчанию — 20 учетных записей. Максимальное число пользователей — 100.
5. При необходимости можно задать для параметра **Сбросить пароль внешних пользователей** значение _Да_, если политика вашей организации требует регулярной смены паролей. Это приведет к повторному созданию зашифрованных паролей, которые хранит панель запуска для учетных записей пользователей. Дополнительные сведения см. в разделе [Применение политики паролей](../security/sql-server-launchpad-service-account.md#bkmk_EnforcePolicy).
6.  Перезапустите службу панели запуска.

## <a name="managing-workloads"></a>Управление рабочими нагрузками

Количество учетных записей в этом пуле определяет, сколько может быть одновременно активных сеансов внешних сценариев.  По умолчанию создаются 20 учетных записей. Это означает, что 20 разных пользователей могут одновременно работать в активных сеансах Python или R. Можно увеличить число рабочих учетных записей, если предполагается выполнение более 20 параллельных сценариев.

Если один и тот же пользователь одновременно выполняет несколько внешних сценариев, все сеансы будут использовать одну и ту же рабочую учетную запись. Например, один пользователь может выполнять 100 различных сценариев Python или R одновременно, пока это позволяют ресурсы, но при этом все сценарии будут использовать одну рабочую учетную запись.

Число поддерживаемых рабочих учетных записей и количество одновременных сеансов, которые могут выполнять пользователи, ограничивается только ресурсами сервера. Как правило, память является первым узким местом при использовании среды выполнения Python или R.

Ресурсами, которые могут использоваться сценариями Python или R, управляет SQL Server. Мы советуем отслеживать использование ресурсов с помощью динамических административных представлений SQL Server или следить за счетчиками производительности для связанного объекта задания Windows и соответствующим образом настраивать использование памяти сервера. При работе с SQL Server Enterprise Edition вы можете выделить ресурсы для выполнения внешних скриптов, настроив [пул внешних ресурсов](create-external-resource-pool.md).

## <a name="next-steps"></a>Дальнейшие действия

- [Мониторинг выполнения скриптов Python и R с помощью пользовательских отчетов в SQL Server Management Studio](../../machine-learning/administration/monitor-sql-server-machine-learning-services-using-custom-reports-management-studio.md)
- [Мониторинг служб машинного обучения SQL Server с помощью динамических административных представлений](../../machine-learning/administration/monitor-sql-server-machine-learning-services-using-dynamic-management-views.md)