---
title: Parameter 对象 (ADO)
TOCTitle: Parameter Object (ADO)
ms:assetid: 7577598e-3d0c-30c6-5f24-1cfe98791798
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249481(v=office.15)
ms:contentKeyID: 48545676
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 382945e1f2ff37eb2155b2bc0db9f521ca85d2de
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25878274"
---
# <a name="parameter-object-ado"></a><span data-ttu-id="8510c-102">Parameter 对象 (ADO)</span><span class="sxs-lookup"><span data-stu-id="8510c-102">Parameter Object (ADO)</span></span>


<span data-ttu-id="8510c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8510c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8510c-104">表示与基于参数化查询或存储过程的 [Command](command-object-ado.md) 对象关联的参数或变量。</span><span class="sxs-lookup"><span data-stu-id="8510c-104">Represents a parameter or argument associated with a [Command](command-object-ado.md) object based on a parameterized query or stored procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="8510c-105">说明</span><span class="sxs-lookup"><span data-stu-id="8510c-105">Remarks</span></span>

<span data-ttu-id="8510c-p101">很多提供程序支持参数化命令。在这些命令中，对期望操作进行了一次定义，但使用变量（或参数）更改命令的某些细节。例如，SQL SELECT statement 可以使用某个参数定义 WHERE 子句的匹配条件，使用另一个参数定义 SORT BY 子句的列名。</span><span class="sxs-lookup"><span data-stu-id="8510c-p101">Many providers support parameterized commands. These are commands in which the desired action is defined once, but variables (or parameters) are used to alter some details of the command. For example, an SQL SELECT statement could use a parameter to define the matching criteria of a WHERE clause, and another to define the column name for a SORT BY clause.</span></span>

<span data-ttu-id="8510c-p102">**Parameter** 对象代表与参数化查询关联的参数，或存储过程的 In/Out 参数和返回值。取决于提供程序所公开的功能， **Parameter** 对象的某些集合、方法或属性可能不可用。</span><span class="sxs-lookup"><span data-stu-id="8510c-p102">**Parameter** objects represent parameters associated with parameterized queries, or the in/out arguments and the return values of stored procedures. Depending on the functionality of the provider, some collections, methods, or properties of a **Parameter** object may not be available.</span></span>

<span data-ttu-id="8510c-111">使用 **Parameter** 对象的集合、方法和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8510c-111">With the collections, methods, and properties of a **Parameter** object, you can do the following:</span></span>

  - <span data-ttu-id="8510c-112">使用 [Name](name-property-ado.md) 属性设置或返回参数名称。</span><span class="sxs-lookup"><span data-stu-id="8510c-112">Set or return the name of a parameter with the [Name](name-property-ado.md) property.</span></span>

  - <span data-ttu-id="8510c-p103">使用 [Value](value-property-ado.md) 属性设置或返回参数值。 **Value** 是 **Parameter** 对象的默认属性。</span><span class="sxs-lookup"><span data-stu-id="8510c-p103">Set or return the value of a parameter with the [Value](value-property-ado.md) property. **Value** is the default property of the **Parameter** object.</span></span>

  - <span data-ttu-id="8510c-115">使用 [Attributes](attributes-property-ado.md)、[Direction](direction-property-ado.md)、[Precision](precision-property-ado.md)、[NumericScale](numericscale-property-ado.md)、[Size](size-property-ado.md) 和 [Type](type-property-ado.md) 属性设置或返回参数特征。</span><span class="sxs-lookup"><span data-stu-id="8510c-115">Set or return parameter characteristics with the [Attributes](attributes-property-ado.md), [Direction](direction-property-ado.md), [Precision](precision-property-ado.md), [NumericScale](numericscale-property-ado.md), [Size](size-property-ado.md), and [Type](type-property-ado.md) properties.</span></span>

  - <span data-ttu-id="8510c-116">使用 [AppendChunk](appendchunk-method-ado.md) 方法向参数传递长二进制数据或字符数据。</span><span class="sxs-lookup"><span data-stu-id="8510c-116">Pass long binary or character data to a parameter with the [AppendChunk](appendchunk-method-ado.md) method.</span></span>

  - <span data-ttu-id="8510c-117">使用 [Properties](properties-collection-ado.md) 集合访问特定于提供程序的属性。</span><span class="sxs-lookup"><span data-stu-id="8510c-117">Access provider-specific attributes with the [Properties](properties-collection-ado.md) collection.</span></span>

<span data-ttu-id="8510c-p104">如果知道与要调用的存储过程或结构化查询关联的参数的名称和属性，可以使用 [CreateParameter](createparameter-method-ado.md) 方法创建具有相应属性设置的 **Parameter** 对象，并使用 [Append](append-method-ado.md) 方法将它们添加到 [Parameters](parameters-collection-ado.md) 集合中。这样，您即可设置和返回参数值，而不必调用 [Parameters](refresh-method-ado.md) 集合的 **Refresh** 方法从提供程序检索参数信息 - 这种操作会占用大量资源。</span><span class="sxs-lookup"><span data-stu-id="8510c-p104">If you know the names and properties of the parameters associated with the stored procedure or parameterized query you wish to call, you can use the [CreateParameter](createparameter-method-ado.md) method to create **Parameter** objects with the appropriate property settings and use the [Append](append-method-ado.md) method to add them to the [Parameters](parameters-collection-ado.md) collection. This lets you set and return parameter values without having to call the [Refresh](refresh-method-ado.md) method on the **Parameters** collection to retrieve the parameter information from the provider, a potentially resource-intensive operation.</span></span>

