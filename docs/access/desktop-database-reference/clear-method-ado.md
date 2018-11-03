---
title: Clear 方法-ActiveX 数据对象 (ADO)
TOCTitle: Clear method (ADO)
ms:assetid: 5d51f42c-147b-1fcf-d05b-123e5714ecb7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249329(v=office.15)
ms:contentKeyID: 48545110
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2cb522a0b70517e81f086f544b1b1e366c166087
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947397"
---
# <a name="clear-method-ado"></a><span data-ttu-id="a86c7-102">Clear 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a86c7-102">Clear method (ADO)</span></span>


<span data-ttu-id="a86c7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a86c7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a86c7-104">用于从 **Errors** 集合中删除所有 **Error** 对象。</span><span class="sxs-lookup"><span data-stu-id="a86c7-104">Removes all the **Error** objects from the **Errors** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="a86c7-105">语法</span><span class="sxs-lookup"><span data-stu-id="a86c7-105">Syntax</span></span>

<span data-ttu-id="a86c7-106">*错误*。清除</span><span class="sxs-lookup"><span data-stu-id="a86c7-106">*Errors*.Clear</span></span>

## <a name="remarks"></a><span data-ttu-id="a86c7-107">备注</span><span class="sxs-lookup"><span data-stu-id="a86c7-107">Remarks</span></span>

<span data-ttu-id="a86c7-p101">可以对 **Errors** 集合使用 [Clear](errors-collection-ado.md) 方法，以从集合中删除所有现有 [Error](error-object-ado.md) 对象。如果发生错误，ADO 将自动清除 **Errors** 集合，并基于新的错误用 **Error** 对象填充集合。</span><span class="sxs-lookup"><span data-stu-id="a86c7-p101">Use the **Clear** method on the [Errors](errors-collection-ado.md) collection to remove all existing [Error](error-object-ado.md) objects from the collection. When an error occurs, ADO automatically clears the **Errors** collection and fills it with **Error** objects based on the new error.</span></span>

<span data-ttu-id="a86c7-p102">某些属性和方法会返回警告，显示为 **Errors** 集合中的 **Error** 对象，但不会停止程序的执行。在对 [Recordset](resync-method-ado.md) 对象调用 [Resync](updatebatch-method-ado.md)、[UpdateBatch](cancelbatch-method-ado.md) 或 [CancelBatch](recordset-object-ado.md) 方法，对 [Connection](open-method-ado-connection.md) 对象调用 [Open](connection-object-ado.md) 方法，或对 [Recordset](filter-property-ado.md) 对象设置 **Filter** 属性之前，请对 **Errors** 集合调用 **Clear** 方法。这样，便可以读取 [Errors](count-property-ado.md) 集合的 **Count** 属性，以测试返回的警告。</span><span class="sxs-lookup"><span data-stu-id="a86c7-p102">Some properties and methods return warnings that appear as **Error** objects in the **Errors** collection but do not halt a program's execution. Before you call the [Resync](resync-method-ado.md), [UpdateBatch](updatebatch-method-ado.md), or [CancelBatch](cancelbatch-method-ado.md) methods on a [Recordset](recordset-object-ado.md) object; the [Open](open-method-ado-connection.md) method on a [Connection](connection-object-ado.md) object; or set the [Filter](filter-property-ado.md) property on a **Recordset** object, call the **Clear** method on the **Errors** collection. That way, you can read the [Count](count-property-ado.md) property of the **Errors** collection to test for returned warnings.</span></span>

