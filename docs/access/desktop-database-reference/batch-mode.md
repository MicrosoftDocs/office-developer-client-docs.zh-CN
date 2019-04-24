---
title: 批处理模式 (Access desktop database reference)
TOCTitle: Batch mode
ms:assetid: b73921f6-5a12-9b26-ea65-99b32dd763f6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249883(v=office.15)
ms:contentKeyID: 48547294
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ac5f14d035a4e11cce67f01ca6636f3ebd39963e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296876"
---
# <a name="batch-mode"></a>批处理模式

**适用于**：Access 2013、Office 2013

当 **LockType** 属性设置为 **adLockBatchOptimistic** ，并且提供程序支持批更新时，批模式有效。根据游标位置，某些锁定类型设置不可用。例如，当 **CursorLocation** 设置为 **adUseClient** 时，保守式锁定类型不可用。反过来，当游标位置位于服务器时，提供程序可能不支持批开放式锁定。仅应将批更新用于键集游标或静态游标。

**UpdateBatch** 方法用于将复制缓冲区中保存的 **Recordset** 更改发送到服务器以更新数据源。在以下部分中，我们将以批模式打开一个 **Recordset** ，对复制缓冲区进行更改，然后调用 **UpdateBatch** 将更改发送到数据源。

本节包括下列主题：

- [发送更新：UpdateBatch](sending-the-updates-updatebatch.md)
- [筛选出更新后的记录](filtering-for-updated-records.md)
- [处理失败的更新](dealing-with-failed-updates.md)
- [检测和解决冲突](detecting-and-resolving-conflicts.md)
- [断开并重新连接记录集](disconnecting-and-reconnecting-the-recordset.md)
- [更新 JOINed 结果：唯一表](updating-joined-results-unique-table.md)

