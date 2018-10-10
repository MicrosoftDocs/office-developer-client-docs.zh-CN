---
title: 批模式 （访问桌面数据库参考 （英文）
TOCTitle: Batch Mode
ms:assetid: b73921f6-5a12-9b26-ea65-99b32dd763f6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249883(v=office.15)
ms:contentKeyID: 48547294
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6e72997d2484bdfcec91542b0b8de6bbbb23e3fa
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465694"
---
# <a name="batch-mode"></a><span data-ttu-id="4e18b-102">批模式</span><span class="sxs-lookup"><span data-stu-id="4e18b-102">Batch Mode</span></span>


<span data-ttu-id="4e18b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4e18b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4e18b-p101">当 **LockType** 属性设置为 **adLockBatchOptimistic** ，并且提供程序支持批更新时，批模式有效。根据游标位置，某些锁定类型设置不可用。例如，当 **CursorLocation** 设置为 **adUseClient** 时，保守式锁定类型不可用。反过来，当游标位置位于服务器时，提供程序可能不支持批开放式锁定。仅应将批更新用于键集游标或静态游标。</span><span class="sxs-lookup"><span data-stu-id="4e18b-p101">Batch mode is in effect when the **LockType** property is set to **adLockBatchOptimistic** and batch updating is supported by the provider. Certain lock type settings are not available depending on cursor location. For instance, a pessimistic lock type is not available when the **CursorLocation** is set to **adUseClient**. Conversely, a provider may not support a batch optimistic lock when the cursor location is on the server. You should use batch updating with either a keyset or static cursor only.</span></span>

<span data-ttu-id="4e18b-p102">**UpdateBatch** 方法用于将复制缓冲区中保存的 **Recordset** 更改发送到服务器以更新数据源。在以下部分中，我们将以批模式打开一个 **Recordset** ，对复制缓冲区进行更改，然后调用 **UpdateBatch** 将更改发送到数据源。</span><span class="sxs-lookup"><span data-stu-id="4e18b-p102">The **UpdateBatch** method is used to send **Recordset** changes held in the copy buffer to the server to update the data source. In the following section, we will open a **Recordset** in batch mode, make changes to the copy buffer, and then send our changes to the data source using a call to **UpdateBatch**.</span></span>

