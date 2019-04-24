---
title: Refresh 方法 (ADO)
TOCTitle: Refresh method (ADO)
ms:assetid: f1c8829f-9c7d-12b6-7470-727ff38d663e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250227(v=office.15)
ms:contentKeyID: 48548631
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: bd7c47e7c3e41a7b42571043cfafc9e4e909a9f9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309253"
---
# <a name="refresh-method-ado"></a><span data-ttu-id="2e441-102">Refresh 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="2e441-102">Refresh method (ADO)</span></span>

<span data-ttu-id="2e441-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="2e441-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2e441-104">更新集合中的对象，以反映提供程序特定的可用对象。</span><span class="sxs-lookup"><span data-stu-id="2e441-104">Updates the objects in a collection to reflect objects available from, and specific to, the provider.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e441-105">语法</span><span class="sxs-lookup"><span data-stu-id="2e441-105">Syntax</span></span>

<span data-ttu-id="2e441-106">*集合*。恢复</span><span class="sxs-lookup"><span data-stu-id="2e441-106">*collection*.Refresh</span></span>

## <a name="remarks"></a><span data-ttu-id="2e441-107">注解</span><span class="sxs-lookup"><span data-stu-id="2e441-107">Remarks</span></span>

<span data-ttu-id="2e441-108">**Refresh** 方法用于完成各种不同的任务，具体取决于从中调用该方法的集合。</span><span class="sxs-lookup"><span data-stu-id="2e441-108">The **Refresh** method accomplishes different tasks depending on the collection from which you call it.</span></span>

## <a name="parameters"></a><span data-ttu-id="2e441-109">参数</span><span class="sxs-lookup"><span data-stu-id="2e441-109">Parameters</span></span>

<span data-ttu-id="2e441-p101">如果对 [Command](command-object-ado.md) 对象的 [Parameters](parameters-collection-ado.md) 集合使用 **Refresh** 方法，则会检索在 **Command** 对象中指定的存储过程或参数化查询的提供程序端参数信息。对于不支持存储过程调用或参数化查询的提供程序，该集合将为空。</span><span class="sxs-lookup"><span data-stu-id="2e441-p101">Using the **Refresh** method on a [Command](command-object-ado.md) object's [Parameters](parameters-collection-ado.md) collection retrieves provider-side parameter information for the stored procedure or parameterized query specified in the **Command** object. The collection will be empty for providers that do not support stored procedure calls or parameterized queries.</span></span>

<span data-ttu-id="2e441-112">在调用 [Refresh](activeconnection-property-ado.md) 方法之前，应当将 **Command** 对象的 [ActiveConnection](connection-object-ado.md) 属性设置为有效的 [Connection](commandtext-property-ado.md) 对象，将 [CommandText](commandtype-property-ado.md) 属性设置为有效的命令，并将 **CommandType** 属性设置为 **adCmdStoredProc** 。</span><span class="sxs-lookup"><span data-stu-id="2e441-112">You should set the [ActiveConnection](activeconnection-property-ado.md) property of the **Command** object to a valid [Connection](connection-object-ado.md) object, the [CommandText](commandtext-property-ado.md) property to a valid command, and the [CommandType](commandtype-property-ado.md) property to **adCmdStoredProc** before calling the **Refresh** method.</span></span>

<span data-ttu-id="2e441-113">如果在调用 **Refresh** 方法之前访问 **Parameters** 集合，则 ADO 将为您自动调用方法并填充集合。</span><span class="sxs-lookup"><span data-stu-id="2e441-113">If you access the **Parameters** collection before calling the **Refresh** method, ADO will automatically call the method and populate the collection for you.</span></span>

> [!NOTE]
> <span data-ttu-id="2e441-p102">如果使用 **Refresh** 方法获取提供程序的参数信息，且该方法返回一个或多个可变长度数据类型 [Parameter](parameter-object-ado.md) 对象，那么 ADO 会根据参数的最大潜在大小为参数分配内存，这将在执行过程中引发错误。在调用 [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 方法以防止出错之前，应当显式设置这些参数的 [Size](size-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="2e441-p102">If you use the **Refresh** method to obtain parameter information from the provider and it returns one or more variable-length data type [Parameter](parameter-object-ado.md) objects, ADO may allocate memory for the parameters based on their maximum potential size, which will cause an error during execution. You should explicitly set the [Size](size-property-ado.md) property for these parameters before calling the [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) method to prevent errors.</span></span>

### <a name="fields"></a><span data-ttu-id="2e441-116">Fields</span><span class="sxs-lookup"><span data-stu-id="2e441-116">Fields</span></span>

<span data-ttu-id="2e441-p103">对 **Fields** 集合使用 **Refresh** 方法没有明显的效果。若要检索基础数据库结构的更改，必须使用 [Requery](requery-method-ado.md) 方法或 [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 方法（如果 [Recordset](recordset-object-ado.md) 对象不支持书签）。</span><span class="sxs-lookup"><span data-stu-id="2e441-p103">Using the **Refresh** method on the **Fields** collection has no visible effect. To retrieve changes from the underlying database structure, you must use either the [Requery](requery-method-ado.md) method or, if the [Recordset](recordset-object-ado.md) object does not support bookmarks, the [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) method.</span></span>

### <a name="properties"></a><span data-ttu-id="2e441-119">属性</span><span class="sxs-lookup"><span data-stu-id="2e441-119">Properties</span></span>

<span data-ttu-id="2e441-p104">如果对某些对象的 **Properties** 集合使用 **Refresh** 方法，则会用提供程序公开的动态属性来填充该集合。除 ADO 支持的内置属性之外，这些属性提供了有关提供程序特定功能的信息。</span><span class="sxs-lookup"><span data-stu-id="2e441-p104">Using the **Refresh** method on a **Properties** collection of some objects populates the collection with the dynamic properties that the provider exposes. These properties provide information about functionality specific to the provider, beyond the built-in properties ADO supports.</span></span>

