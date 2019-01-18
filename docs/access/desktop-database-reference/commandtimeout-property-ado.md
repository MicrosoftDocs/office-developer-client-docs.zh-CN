---
title: CommandTimeout 属性 (ADO)
TOCTitle: CommandTimeout property (ADO)
ms:assetid: a0b6209c-9feb-08ae-002a-15d1d20734a8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249739(v=office.15)
ms:contentKeyID: 48546714
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231124
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 9d44bc8fae0143b183ef54120cdaaf91337f36f8
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700113"
---
# <a name="commandtimeout-property-ado"></a><span data-ttu-id="440ea-102">CommandTimeout 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="440ea-102">CommandTimeout property (ADO)</span></span>


<span data-ttu-id="440ea-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="440ea-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="440ea-104">指示在执行命令时要等待多长时间才终止操作尝试并生成错误。</span><span class="sxs-lookup"><span data-stu-id="440ea-104">Indicates how long to wait while executing a command before terminating the attempt and generating an error.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="440ea-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="440ea-105">Settings and return values</span></span>

<span data-ttu-id="440ea-p101">设置或返回一个 **Long** 值，该值指示等待命令执行的时间（以秒为单位）。默认值为 30。</span><span class="sxs-lookup"><span data-stu-id="440ea-p101">Sets or returns a **Long** value that indicates, in seconds, how long to wait for a command to execute. Default is 30.</span></span>

## <a name="remarks"></a><span data-ttu-id="440ea-108">备注</span><span class="sxs-lookup"><span data-stu-id="440ea-108">Remarks</span></span>

<span data-ttu-id="440ea-p102">使用 **Connection** 对象或 [Command](connection-object-ado.md) 对象上的 [CommandTimeout](command-object-ado.md) 属性，可以允许在网络通信延迟或服务器负载太大的情况下取消 [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 方法调用。如果在完成执行命令前超过了 **CommandTimeout** 属性中设置的间隔时间，则将发生错误，且 ADO 将取消该命令。如果将该属性设置为零，ADO 将无限期等待，直到完成执行为止。请确保向其中写入代码的提供程序和数据源支持 **CommandTimeout** 功能。</span><span class="sxs-lookup"><span data-stu-id="440ea-p102">Use the **CommandTimeout** property on a [Connection](connection-object-ado.md) object or [Command](command-object-ado.md) object to allow the cancellation of an [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) method call, due to delays from network traffic or heavy server use. If the interval set in the **CommandTimeout** property elapses before the command completes execution, an error occurs and ADO cancels the command. If you set the property to zero, ADO will wait indefinitely until the execution is complete. Make sure the provider and data source to which you are writing code support the **CommandTimeout** functionality.</span></span>

<span data-ttu-id="440ea-113">**Connection** 对象上的 **CommandTimeout** 设置对同一个 **Connection** 中的 **Command** 对象的 **CommandTimeout** 设置没有影响；即， **Command** 对象的 **CommandTimeout** 属性并不会继承 **Connection** 对象的 **CommandTimeout** 值。</span><span class="sxs-lookup"><span data-stu-id="440ea-113">The **CommandTimeout** setting on a **Connection** object has no effect on the **CommandTimeout** setting on a **Command** object on the same **Connection**; that is, the **Command** object's **CommandTimeout** property does not inherit the value of the **Connection** object's **CommandTimeout** value.</span></span>

<span data-ttu-id="440ea-114">在 **Connection** 对象上， **CommandTimeout** 属性会在该 **Connection** 打开后保持可读/写状态。</span><span class="sxs-lookup"><span data-stu-id="440ea-114">On a **Connection** object, the **CommandTimeout** property remains read/write after the **Connection** is opened.</span></span>

