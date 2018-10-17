---
title: IsolationLevel 属性 (ADO)
TOCTitle: IsolationLevel Property (ADO)
ms:assetid: 19461be5-c94b-4b61-ce08-7abdf702c3dc
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248939(v=office.15)
ms:contentKeyID: 48543493
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7424258f4b5a69764189f33a902956f370a56094
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467330"
---
# <a name="isolationlevel-property-ado"></a><span data-ttu-id="4bc22-102">IsolationLevel 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="4bc22-102">IsolationLevel Property (ADO)</span></span>


<span data-ttu-id="4bc22-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4bc22-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4bc22-104">指示 [Connection](connection-object-ado.md) 对象的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="4bc22-104">Indicates the level of isolation for a [Connection](connection-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="4bc22-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="4bc22-105">Settings and Return Values</span></span>

<span data-ttu-id="4bc22-106">设置或返回一个[IsolationLevelEnum](isolationlevelenum.md)值。</span><span class="sxs-lookup"><span data-stu-id="4bc22-106">Sets or returns an [IsolationLevelEnum](isolationlevelenum.md) value.</span></span> <span data-ttu-id="4bc22-107">默认值为**adXactChaos**。</span><span class="sxs-lookup"><span data-stu-id="4bc22-107">The default is **adXactChaos**.</span></span>

## <a name="remarks"></a><span data-ttu-id="4bc22-108">备注</span><span class="sxs-lookup"><span data-stu-id="4bc22-108">Remarks</span></span>

<span data-ttu-id="4bc22-p102">使用 **IsolationLevel** 属性可设置 **Connection** 对象的隔离级别。直到下次调用 [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法时，该设置才会生效。如果请求的隔离级别不可用，则提供程序将返回下一个更高的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="4bc22-p102">Use the **IsolationLevel** property to set the isolation level of a **Connection** object. The setting does not take effect until the next time you call the [BeginTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) method. If the level of isolation you request is unavailable, the provider may return the next greater level of isolation.</span></span>

<span data-ttu-id="4bc22-112">**IsolationLevel** 属性为可读写状态。</span><span class="sxs-lookup"><span data-stu-id="4bc22-112">The **IsolationLevel** property is read/write.</span></span>

<span data-ttu-id="4bc22-113">**远程数据服务用法**当客户端 Connection 对象上使用， **IsolationLevel**属性可以设置仅为**adXactUnspecified**。</span><span class="sxs-lookup"><span data-stu-id="4bc22-113">**Remote Data Service Usage**When used on a client-side Connection object, the **IsolationLevel** property can be set only to **adXactUnspecified**.</span></span>

<span data-ttu-id="4bc22-p103">由于用户正在使用客户端缓存上的已断开连接的 **Recordset** 对象，因此可能会出现多用户问题。例如，两个不同的用户试图更新同一条记录时，远程数据服务只允许首先更新该记录的用户实现更新操作。另一个用户的更新请求将失败，并产生错误。</span><span class="sxs-lookup"><span data-stu-id="4bc22-p103">Because users are working with disconnected **Recordset** objects on a client-side cache, there may be multiuser issues. For instance, when two different users try to update the same record, Remote Data Service simply allows the user who updates the record first to "win." The second user's update request will fail with an error.</span></span>
