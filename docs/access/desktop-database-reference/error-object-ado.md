---
title: Error 对象的 ActiveX 数据对象 (ADO)
TOCTitle: Error Object (ADO)
ms:assetid: 97e478bf-8b25-03a8-9358-abba5069cba3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249678(v=office.15)
ms:contentKeyID: 48546477
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ae89c4d2300b167a8e7b993ad8830838d91f0617
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877021"
---
# <a name="error-object-ado"></a><span data-ttu-id="dd75f-102">Error 对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="dd75f-102">Error Object (ADO)</span></span>


<span data-ttu-id="dd75f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="dd75f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="dd75f-104">包含有关数据访问错误的详细信息，该错误与涉及提供程序的单个操作相关。</span><span class="sxs-lookup"><span data-stu-id="dd75f-104">Contains details about data access errors that pertain to a single operation involving the provider.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd75f-105">说明</span><span class="sxs-lookup"><span data-stu-id="dd75f-105">Remarks</span></span>

<span data-ttu-id="dd75f-p101">任何涉及 ADO 对象的操作都可能生成一个或多个提供程序错误。每个错误发生时，系统会将一个或多个 **Error** 对象放在 [Connection](errors-collection-ado.md) 对象的 [Errors](connection-object-ado.md) 集合中。当另一个 ADO 操作生成错误时，系统会清空 **Errors** 集合，并在 **Errors** 集合中放入新的 **Error** 对象集。</span><span class="sxs-lookup"><span data-stu-id="dd75f-p101">Any operation involving ADO objects can generate one or more provider errors. As each error occurs, one or more **Error** objects are placed in the [Errors](errors-collection-ado.md) collection of the [Connection](connection-object-ado.md) object. When another ADO operation generates an error, the **Errors** collection is cleared, and the new set of **Error** objects is placed in the **Errors** collection.</span></span>

> [!NOTE]
> <span data-ttu-id="dd75f-p102">[!注释] 每个 **Error** 对象代表一个特定的提供程序错误，而不是 ADO 错误。ADO 错误是对运行时异常处理机制公开的。例如，在 Microsoft Visual Basic 中，出现特定于 ADO 的错误将触发一个 **On Error** 事件，该错误会显示在 **Error** 对象中。有关 ADO 错误的完整列表，请参阅 [ErrorValueEnum](errorvalueenum.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="dd75f-p102">Each **Error** object represents a specific provider error, not an ADO error. ADO errors are exposed to the run-time exception-handling mechanism. For example, in Microsoft Visual Basic, the occurrence of an ADO-specific error will trigger an **On Error** event and appear in the **Error** object. For a complete list of ADO errors, see the [ErrorValueEnum](errorvalueenum.md) topic.</span></span>

<span data-ttu-id="dd75f-113">您可以阅读 **Error** 对象的属性，以便了解有关每种错误的特定详细信息。这些属性包括：</span><span class="sxs-lookup"><span data-stu-id="dd75f-113">You can read an **Error** object's properties to obtain specific details about each error, including the following:</span></span>

- <span data-ttu-id="dd75f-p103">[Description](description-property-ado.md) 属性，其中包含有关错误的文本。这是默认属性。</span><span class="sxs-lookup"><span data-stu-id="dd75f-p103">The [Description](description-property-ado.md) property, which contains the text of the error. This is the default property.</span></span>

- <span data-ttu-id="dd75f-116">[Number](number-property-ado.md) 属性，其中包含错误常量的 **Long** 类型整数值。</span><span class="sxs-lookup"><span data-stu-id="dd75f-116">The [Number](number-property-ado.md) property, which contains the **Long** integer value of the error constant.</span></span>

- <span data-ttu-id="dd75f-p104">[Source](source-property-ado-error.md) 属性，该属性标识产生错误的对象。当对数据源发出请求后，在 **Errors** 集合中产生多个 **Error** 对象时，该属性尤其有用。</span><span class="sxs-lookup"><span data-stu-id="dd75f-p104">The [Source](source-property-ado-error.md) property, which identifies the object that raised the error. This is particularly useful when you have several **Error** objects in the **Errors** collection following a request to a data source.</span></span>

- <span data-ttu-id="dd75f-119">[SQLState](sqlstate-property-ado.md) 和 [NativeError](nativeerror-property-ado.md) 属性，这些属性从 SQL 数据源提供信息。</span><span class="sxs-lookup"><span data-stu-id="dd75f-119">The [SQLState](sqlstate-property-ado.md) and [NativeError](nativeerror-property-ado.md) properties, which provide information from SQL data sources.</span></span>

<span data-ttu-id="dd75f-p105">发生提供程序错误时，该错误会被放入 **Connection** 对象的 **Errors** 集合中。ADO 支持通过一个 ADO 操作返回多个错误，以允许特定于该提供程序的错误信息。若要获取错误处理程序中的这些丰富错误信息，可使用语言或环境的相应错误捕获功能，然后使用嵌套循环来枚举 **Errors** 集合中每个 **Error** 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="dd75f-p105">When a provider error occurs, it is placed in the **Errors** collection of the **Connection** object. ADO supports the return of multiple errors by a single ADO operation to allow for error information specific to the provider. To obtain this rich error information in an error handler, use the appropriate error-trapping features of the language or environment you are working with, then use nested loops to enumerate the properties of each **Error** object in the **Errors** collection.</span></span>

<span data-ttu-id="dd75f-123">**Microsoft Visual Basic 和 VBScript 用户**如果没有任何有效的**Connection**对象，您将需要从**Error**对象中检索错误信息。</span><span class="sxs-lookup"><span data-stu-id="dd75f-123">**Microsoft Visual Basic and VBScript Users**If there is no valid **Connection** object, you will need to retrieve error information from the **Error** object.</span></span>

<span data-ttu-id="dd75f-p106">就像提供程序一样，ADO 会在进行可能产生新提供程序错误的调用之前，会清除 **OLE Error Info** 对象。但是，只有在提供程序生成新错误时，或者调用 **Clear** 方法时，才会清空 **Connection** 对象的 [Errors](clear-method-ado.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="dd75f-p106">Just as providers do, ADO clears the **OLE Error Info** object before making a call that could potentially generate a new provider error. However, the **Errors** collection on the **Connection** object is cleared and populated only when the provider generates a new error, or when the [Clear](clear-method-ado.md) method is called.</span></span>

<span data-ttu-id="dd75f-p107">某些属性和方法会返回警告（这些警告显示为 **Errors** 集合中的 **Error** 对象），但不会停止程序的执行。在对 [Recordset](resync-method-ado.md) 对象调用 [Resync](updatebatch-method-ado.md)、[UpdateBatch](cancelbatch-method-ado.md) 或 [CancelBatch](recordset-object-ado.md) 方法，对 [Connection](open-method-ado-connection.md) 对象调用 **Open** 方法，或对 [Recordset](filter-property-ado.md) 对象设置 **Filter** 属性之前，请对 **Errors** 集合调用 **Clear** 方法。这样，便可以读取 [Errors](count-property-ado.md) 集合的 **Count** 属性，以测试返回的警告。</span><span class="sxs-lookup"><span data-stu-id="dd75f-p107">Some properties and methods return warnings that appear as **Error** objects in the **Errors** collection but do not halt a program's execution. Before you call the [Resync](resync-method-ado.md), [UpdateBatch](updatebatch-method-ado.md), or [CancelBatch](cancelbatch-method-ado.md) methods on a [Recordset](recordset-object-ado.md) object; the [Open](open-method-ado-connection.md) method on a **Connection** object; or set the [Filter](filter-property-ado.md) property on a **Recordset** object, call the **Clear** method on the **Errors** collection. That way, you can read the [Count](count-property-ado.md) property of the **Errors** collection to test for returned warnings.</span></span>

