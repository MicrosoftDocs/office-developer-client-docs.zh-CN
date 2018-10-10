---
title: CommandTimeout 属性 (ADO)
TOCTitle: CommandTimeout Property (ADO)
ms:assetid: a0b6209c-9feb-08ae-002a-15d1d20734a8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249739(v=office.15)
ms:contentKeyID: 48546714
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231124
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 58d95f6a3238d09ae10ddb3ba127a9fa68631f4f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466317"
---
# <a name="commandtimeout-property-ado"></a><span data-ttu-id="9f307-102">CommandTimeout 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="9f307-102">CommandTimeout Property (ADO)</span></span>


<span data-ttu-id="9f307-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9f307-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9f307-104">指示在执行命令时要等待多长时间才终止操作尝试并生成错误。</span><span class="sxs-lookup"><span data-stu-id="9f307-104">Indicates how long to wait while executing a command before terminating the attempt and generating an error.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="9f307-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="9f307-105">Settings and Return Values</span></span>

<span data-ttu-id="9f307-p101">设置或返回一个 **Long** 值，该值指示等待命令执行的时间（以秒为单位）。默认值为 30。</span><span class="sxs-lookup"><span data-stu-id="9f307-p101">Sets or returns a **Long** value that indicates, in seconds, how long to wait for a command to execute. Default is 30.</span></span>

## <a name="remarks"></a><span data-ttu-id="9f307-108">备注</span><span class="sxs-lookup"><span data-stu-id="9f307-108">Remarks</span></span>

<span data-ttu-id="9f307-p102">使用 **Connection** 对象或 [Command](connection-object-ado.md) 对象上的 [CommandTimeout](command-object-ado.md) 属性，可以允许在网络通信延迟或服务器负载太大的情况下取消 [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) 方法调用。如果在完成执行命令前超过了 **CommandTimeout** 属性中设置的间隔时间，则将发生错误，且 ADO 将取消该命令。如果将该属性设置为零，ADO 将无限期等待，直到完成执行为止。请确保向其中写入代码的提供程序和数据源支持 **CommandTimeout** 功能。</span><span class="sxs-lookup"><span data-stu-id="9f307-p102">Use the **CommandTimeout** property on a [Connection](connection-object-ado.md) object or [Command](command-object-ado.md) object to allow the cancellation of an [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) method call, due to delays from network traffic or heavy server use. If the interval set in the **CommandTimeout** property elapses before the command completes execution, an error occurs and ADO cancels the command. If you set the property to zero, ADO will wait indefinitely until the execution is complete. Make sure the provider and data source to which you are writing code support the **CommandTimeout** functionality.</span></span>

<span data-ttu-id="9f307-113">**Connection** 对象上的 **CommandTimeout** 设置对同一个 **Connection** 中的 **Command** 对象的 **CommandTimeout** 设置没有影响；即， **Command** 对象的 **CommandTimeout** 属性并不会继承 **Connection** 对象的 **CommandTimeout** 值。</span><span class="sxs-lookup"><span data-stu-id="9f307-113">The **CommandTimeout** setting on a **Connection** object has no effect on the **CommandTimeout** setting on a **Command** object on the same **Connection**; that is, the **Command** object's **CommandTimeout** property does not inherit the value of the **Connection** object's **CommandTimeout** value.</span></span>

<span data-ttu-id="9f307-114">在 **Connection** 对象上， **CommandTimeout** 属性会在该 **Connection** 打开后保持可读/写状态。</span><span class="sxs-lookup"><span data-stu-id="9f307-114">On a **Connection** object, the **CommandTimeout** property remains read/write after the **Connection** is opened.</span></span>

