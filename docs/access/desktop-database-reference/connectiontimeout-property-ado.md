---
title: ConnectionTimeout 属性 (ADO)
TOCTitle: ConnectionTimeout property (ADO)
ms:assetid: efc39fd8-afce-5ac0-2fff-cbb55c1a444d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250218(v=office.15)
ms:contentKeyID: 48548589
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0526ee6a0d6cf9aa8f9263e8f3d31e66fad7da82
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295700"
---
# <a name="connectiontimeout-property-ado"></a><span data-ttu-id="09e8e-102">ConnectionTimeout 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="09e8e-102">ConnectionTimeout property (ADO)</span></span>


<span data-ttu-id="09e8e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="09e8e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="09e8e-104">指示在建立连接时要等待多长时间才终止连接尝试并生成错误。</span><span class="sxs-lookup"><span data-stu-id="09e8e-104">Indicates how long to wait while establishing a connection before terminating the attempt and generating an error.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="09e8e-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="09e8e-105">Settings and return values</span></span>

<span data-ttu-id="09e8e-106">设置或返回一个 **Long** 值，该值指示等待连接打开的时间（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="09e8e-106">Sets or returns a **Long** value that indicates, in seconds, how long to wait for the connection to open.</span></span> <span data-ttu-id="09e8e-107">默认值为 15。</span><span class="sxs-lookup"><span data-stu-id="09e8e-107">Default is 15.</span></span>

## <a name="remarks"></a><span data-ttu-id="09e8e-108">注解</span><span class="sxs-lookup"><span data-stu-id="09e8e-108">Remarks</span></span>

<span data-ttu-id="09e8e-p102">如果由于网络通信延迟或服务器负载太大而有必要放弃连接尝试，请使用 **Connection** 对象上的 [ConnectionTimeout](connection-object-ado.md) 属性。如果在打开连接前超过了 **ConnectionTimeout** 属性设置的时间，将发生错误，且 ADO 将取消连接尝试。如果将该属性设置为零，ADO 将无限期等待，直到连接打开为止。请确保您向其中写入代码的提供程序支持 **ConnectionTimeout** 功能。</span><span class="sxs-lookup"><span data-stu-id="09e8e-p102">Use the **ConnectionTimeout** property on a [Connection](connection-object-ado.md) object if delays from network traffic or heavy server use make it necessary to abandon a connection attempt. If the time from the **ConnectionTimeout** property setting elapses prior to the opening of the connection, an error occurs and ADO cancels the attempt. If you set the property to zero, ADO will wait indefinitely until the connection is opened. Make sure the provider to which you are writing code supports the **ConnectionTimeout** functionality.</span></span>

<span data-ttu-id="09e8e-113">**ConnectionTimeout** 属性在连接关闭时为可读/写属性，而在连接打开时为只读属性。</span><span class="sxs-lookup"><span data-stu-id="09e8e-113">The **ConnectionTimeout** property is read/write when the connection is closed and read-only when it is open.</span></span>

