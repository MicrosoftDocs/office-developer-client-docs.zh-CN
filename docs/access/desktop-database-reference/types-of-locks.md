---
title: 锁定 （访问桌面数据库引用） 的类型
TOCTitle: Types of Locks
ms:assetid: 8276edca-f603-2487-a2ca-73e618c0f11e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249565(v=office.15)
ms:contentKeyID: 48545978
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0a104b2ad452cdf8b0688dbc84ca09b90ed08c62
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944912"
---
# <a name="types-of-locks"></a>锁定的类型


**适用于**： Access 2013、 Office 2013



## <a name="adlockbatchoptimistic"></a>adLockBatchOptimistic

指示开放式批更新。这是批更新模式所必需的。

许多应用程序都一次提取大量行，然后要进行一致的更新，这些更新包括对整个行集进行插入、更新或删除。使用批处理游标，只需在服务器之间往返一次，从而改善了更新性能并减少了网络流量。使用批处理游标库，可以创建静态游标，然后断开与数据源的连接。此时，可以对行进行更改，再重新连接到数据源并成批发布对数据源进行的更改。

## <a name="adlockoptimistic"></a>adLockOptimistic

指示提供程序使用开放式锁定，只有调用 **Update** 方法时才锁定记录。这意味着，在您编辑记录到您调用 **Update** 的时间间隔内，其他用户可能会更改数据，从而导致冲突。这种锁定类型用于很少出现冲突或者冲突易于解决的情形。

## <a name="adlockpessimistic"></a>adLockPessimistic

指示以保守方式逐个锁定记录。提供程序执行必要的操作以确保成功编辑记录，通常是通过在编辑之前先在数据源锁定记录来实现。当然，这意味着在您开始编辑之后，其他用户将无法使用这些记录，直到您通过调用 **Update** 来解除锁定。这种类型的锁定用在无法承受对数据进行并发更改的系统（如预订系统）中。

## <a name="adlockreadonly"></a>adLockReadOnly

指示只读记录。您不能修改数据。只读锁定是"最快"类型的锁定，因为它不需要服务器维护对记录的锁定。

## <a name="adlockunspecified"></a>adLockUnspecified

不指定锁定类型。

