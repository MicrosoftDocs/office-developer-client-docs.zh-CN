---
title: Errors 集合 (ADO)
TOCTitle: Errors collection (ADO)
ms:assetid: 76c234b8-7fec-11c5-275e-864d5d880ee7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249486(v=office.15)
ms:contentKeyID: 48545706
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: db9fa4fccc4f3d13849f34c157f2ea07cc3f171d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715902"
---
# <a name="errors-collection-ado"></a><span data-ttu-id="1394b-102">Errors 集合 (ADO)</span><span class="sxs-lookup"><span data-stu-id="1394b-102">Errors collection (ADO)</span></span>


<span data-ttu-id="1394b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1394b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1394b-104">包含为了响应与单个提供程序相关的失败提供程序而创建的所有 [Error](error-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="1394b-104">Contains all the [Error](error-object-ado.md) objects created in response to a single provider-related failure provider.</span></span>

## <a name="remarks"></a><span data-ttu-id="1394b-105">说明</span><span class="sxs-lookup"><span data-stu-id="1394b-105">Remarks</span></span>

<span data-ttu-id="1394b-p101">任何涉及 ADO 对象的操作都可能生成一个或多个提供程序错误。每个错误发生时，系统会将一个或多个 **Error** 对象放在 **Connection** 对象的 [Errors](connection-object-ado.md) 集合中。当另一个 ADO 操作生成错误时，系统会清空 **Errors** 集合，并在 **Errors** 集合中放入新的 **Error** 对象集。</span><span class="sxs-lookup"><span data-stu-id="1394b-p101">Any operation involving ADO objects can generate one or more provider errors. As each error occurs, one or more **Error** objects can be placed in the **Errors** collection of the [Connection](connection-object-ado.md) object. When another ADO operation generates an error, the **Errors** collection is cleared, and the new set of **Error** objects can be placed in the **Errors** collection.</span></span>

<span data-ttu-id="1394b-p102">每个 **Error** 对象代表一个特定的提供程序错误，而不是 ADO 错误。ADO 错误是对运行时异常处理机制公开的。例如，在 Microsoft Visual Basic 中，出现特定于 ADO 的错误将触发一个 [onError](onerror-event-rds.md) 事件，该错误会显示在 **Err** 对象中。</span><span class="sxs-lookup"><span data-stu-id="1394b-p102">Each **Error** object represents a specific provider error, not an ADO error. ADO errors are exposed to the run-time exception-handling mechanism. For example, in Microsoft Visual Basic, the occurrence of an ADO-specific error will trigger an [onError](onerror-event-rds.md) event and appear in the **Err** object.</span></span>

<span data-ttu-id="1394b-p103">不生成错误的 ADO 操作对 **Errors** 集合没有影响。使用 [Clear](clear-method-ado.md) 方法可手动清空 **Errors** 集合。</span><span class="sxs-lookup"><span data-stu-id="1394b-p103">ADO operations that don't generate an error have no effect on the **Errors** collection. Use the [Clear](clear-method-ado.md) method to manually clear the **Errors** collection.</span></span>

<span data-ttu-id="1394b-p104">**Errors** 集合中的 **Error** 对象集描述在响应单个语句时生成的所有错误。通过枚举 **Errors** 集合中的特定错误，您的错误处理例程可以更精确地确定错误的原因和根源，并采取相应的步骤进行恢复。</span><span class="sxs-lookup"><span data-stu-id="1394b-p104">The set of **Error** objects in the **Errors** collection describes all errors that occurred in response to a single statement. Enumerating the specific errors in the **Errors** collection enables your error-handling routines to more precisely determine the cause and origin of an error, and take appropriate steps to recover.</span></span>

<span data-ttu-id="1394b-p105">某些属性和方法会返回警告（这些警告显示为 **Errors** 集合中的 **Error** 对象），但不会停止程序的执行。在对 [Recordset](resync-method-ado.md) 对象调用 [Resync](updatebatch-method-ado.md)、[UpdateBatch](cancelbatch-method-ado.md) 或 [CancelBatch](recordset-object-ado.md) 方法，对 [Connection](open-method-ado-connection.md) 对象调用 **Open** 方法，或对 [Recordset](filter-property-ado.md) 对象设置 **Filter** 属性之前，请对 **Errors** 集合调用 **Clear** 方法。这样，便可以读取 [Errors](count-property-ado.md) 集合的 **Count** 属性，以测试返回的警告。</span><span class="sxs-lookup"><span data-stu-id="1394b-p105">Some properties and methods return warnings that appear as **Error** objects in the **Errors** collection but do not halt a program's execution. Before you call the [Resync](resync-method-ado.md), [UpdateBatch](updatebatch-method-ado.md), or [CancelBatch](cancelbatch-method-ado.md) methods on a [Recordset](recordset-object-ado.md) object, the [Open](open-method-ado-connection.md) method on a **Connection** object, or set the [Filter](filter-property-ado.md) property on a **Recordset** object, call the **Clear** method on the **Errors** collection. That way you can read the [Count](count-property-ado.md) property of the **Errors** collection to test for returned warnings.</span></span>


> [!NOTE]
> <span data-ttu-id="1394b-119">[!注释] 有关单个 ADO 操作如何生成多个错误的更详细解释，请参阅 **Error** 对象主题。</span><span class="sxs-lookup"><span data-stu-id="1394b-119">See the **Error** object topic for a more detailed explanation of the way a single ADO operation can generate multiple errors.</span></span>


