---
title: Parameters 集合 (ADO)
TOCTitle: Parameters collection (ADO)
ms:assetid: 554387c3-3572-5391-3b24-c7d3443844cd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249283(v=office.15)
ms:contentKeyID: 48544923
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231103
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 3a838819b2bac097d3f2fb704ef42c9d2329e51c
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929900"
---
# <a name="parameters-collection-ado"></a><span data-ttu-id="c8561-102">Parameters 集合 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c8561-102">Parameters collection (ADO)</span></span>


<span data-ttu-id="c8561-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c8561-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c8561-104">包含 [Command](parameter-object-ado.md) 对象的所有 [Parameter](command-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="c8561-104">Contains all the [Parameter](parameter-object-ado.md) objects of a [Command](command-object-ado.md) object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8561-105">说明</span><span class="sxs-lookup"><span data-stu-id="c8561-105">Remarks</span></span>

<span data-ttu-id="c8561-106">**Command** 对象具有一个由 **Parameter** 对象组成的 **Parameters** 集合。</span><span class="sxs-lookup"><span data-stu-id="c8561-106">A **Command** object has a **Parameters** collection made up of **Parameter** objects.</span></span>

<span data-ttu-id="c8561-p101">如果对 [Command](refresh-method-ado.md) 对象的 **Parameters** 集合使用 **Refresh** 方法，则会检索在 **Command** 对象中指定的存储过程或参数化查询的提供程序参数信息。某些提供程序不支持存储过程调用或参数化查询；使用这种提供程序时，对 **Parameters** 集合调用 **Refresh** 方法将返回错误。</span><span class="sxs-lookup"><span data-stu-id="c8561-p101">Using the [Refresh](refresh-method-ado.md) method on a **Command** object's **Parameters** collection retrieves provider parameter information for the stored procedure or parameterized query specified in the **Command** object. Some providers do not support stored procedure calls or parameterized queries; calling the **Refresh** method on the **Parameters** collection when using such a provider will return an error.</span></span>

<span data-ttu-id="c8561-109">如果尚未定义自己的 **Parameter** 对象，当您在调用 **Refresh** 方法之前访问 **Parameters** 集合时，ADO 将为您自动调用该方法并填充集合。</span><span class="sxs-lookup"><span data-stu-id="c8561-109">If you have not defined your own **Parameter** objects and you access the **Parameters** collection before calling the **Refresh** method, ADO will automatically call the method and populate the collection for you.</span></span>

<span data-ttu-id="c8561-p102">如果您知道与要调用的存储过程或参数化查询关联的参数的属性，可以最大限度地减少对提供程序的调用以改进性能。可以使用 [CreateParameter](createparameter-method-ado.md) 方法创建具适当属性设置的 **Parameter** 对象，并用 [Append](append-method-ado.md) 方法将对象添加到 **Parameters** 集合。这样一来，无需调用参数信息的提供程序，即可设置和返回参数值。如果正在写入不提供参数信息的提供程序，则必须使用此方法手动填充 **Parameters** 集合，才能使用参数。如果必要，可使用 [Delete](delete-method-ado-parameters-collection.md) 方法从 **Parameters** 集合中删除 **Parameter** 对象。</span><span class="sxs-lookup"><span data-stu-id="c8561-p102">You can minimize calls to the provider to improve performance if you know the properties of the parameters associated with the stored procedure or parameterized query you wish to call. Use the [CreateParameter](createparameter-method-ado.md) method to create **Parameter** objects with the appropriate property settings and use the [Append](append-method-ado.md) method to add them to the **Parameters** collection. This lets you set and return parameter values without having to call the provider for the parameter information. If you are writing to a provider that does not supply parameter information, you must manually populate the **Parameters** collection using this method to be able to use parameters at all. Use the [Delete](delete-method-ado-parameters-collection.md) method to remove **Parameter** objects from the **Parameters** collection if necessary.</span></span>

<span data-ttu-id="c8561-115">**Recordset** 关闭时， **Recordset** 的 **Parameters** 集合中的对象超出范围（不可用）。</span><span class="sxs-lookup"><span data-stu-id="c8561-115">The objects in the **Parameters** collection of a **Recordset** go out of scope (therefore becoming unavailable) when the **Recordset** is closed.</span></span>

