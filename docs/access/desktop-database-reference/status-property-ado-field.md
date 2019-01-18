---
title: Status 属性（ADO 字段）
TOCTitle: Status property (ADO Field)
ms:assetid: 7a7b45e8-2934-2e8e-77fa-a4f38272548d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249507(v=office.15)
ms:contentKeyID: 48545795
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9c5f9d73a1081bb27c88541ac99307165222ab65
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712237"
---
# <a name="status-property-ado-field"></a><span data-ttu-id="5786d-102">Status 属性（ADO 字段）</span><span class="sxs-lookup"><span data-stu-id="5786d-102">Status property (ADO Field)</span></span>


<span data-ttu-id="5786d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5786d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="5786d-104">指示 [Field](field-object-ado.md) 对象的状态。</span><span class="sxs-lookup"><span data-stu-id="5786d-104">Indicates the status of a [Field](field-object-ado.md) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="5786d-105">返回值</span><span class="sxs-lookup"><span data-stu-id="5786d-105">Return value</span></span>

<span data-ttu-id="5786d-p101">返回一个 [FieldStatusEnum](fieldstatusenum.md) 值。默认值是 **adFieldOK** 。</span><span class="sxs-lookup"><span data-stu-id="5786d-p101">Returns a [FieldStatusEnum](fieldstatusenum.md) value. The default value is **adFieldOK**.</span></span>

## <a name="remarks"></a><span data-ttu-id="5786d-108">备注</span><span class="sxs-lookup"><span data-stu-id="5786d-108">Remarks</span></span>

<span data-ttu-id="5786d-109">对于 **Recordset** 对象的字段，此属性通常返回 [adFieldOK](recordset-object-ado.md) 。</span><span class="sxs-lookup"><span data-stu-id="5786d-109">This property always returns **adFieldOK** for fields of a [Recordset](recordset-object-ado.md) object.</span></span>

<span data-ttu-id="5786d-p102">对 [Record](fields-collection-ado.md) 对象的 [Fields](record-object-ado.md) 集合所做的添加和删除均保存在缓存中，直到调用 [Update](update-method-ado.md) 方法时才生效。通过 **Status** 属性可确定成功添加或删除的字段。</span><span class="sxs-lookup"><span data-stu-id="5786d-p102">Additions and deletions to the [Fields](fields-collection-ado.md) collections of the [Record](record-object-ado.md) object are cached until the [Update](update-method-ado.md) method is called. The **Status** property enables you to determine which fields have been successfully added or deleted.</span></span>

<span data-ttu-id="5786d-112">为了提高性能，架构更改均保存在缓存中，直到调用 **Update** 时才生效，然后在批量优化更新中进行更改。</span><span class="sxs-lookup"><span data-stu-id="5786d-112">To enhance performance, schema changes are cached until **Update** is called, and then the changes are made in a batch optimistic update.</span></span> <span data-ttu-id="5786d-113">如果未调用 **Update** 方法，则不会更新服务器。</span><span class="sxs-lookup"><span data-stu-id="5786d-113">If the **Update** method is not called, the server is not updated.</span></span> <span data-ttu-id="5786d-114">如果任何更新失败，则返回错误，并且 **Status** 属性将指示操作和错误状态代码的组合值。</span><span class="sxs-lookup"><span data-stu-id="5786d-114">If any updates fail then an error is returned and the **Status** property indicates the combined values of the operation and error status code.</span></span> <span data-ttu-id="5786d-115">例如， **adFieldPendingInsert** **或** **adFieldPermissionDenied** 。</span><span class="sxs-lookup"><span data-stu-id="5786d-115">For example, **adFieldPendingInsert** **OR** **adFieldPermissionDenied**.</span></span> <span data-ttu-id="5786d-116">每个 **Field** 的 **Status** 属性均可用于确定未添加、修改或删除 **Field** 的原因。</span><span class="sxs-lookup"><span data-stu-id="5786d-116">The **Status** property for each **Field** can be used to determine why the **Field** was not added, modified, or deleted.</span></span> <span data-ttu-id="5786d-117">仅有意义地对**记录**公开**状态**。**Fields**集合并不**记录集**。**Fields**集合。</span><span class="sxs-lookup"><span data-stu-id="5786d-117">**Status** is only meaningfully exposed on the **Record**.**Fields** collection and not the **Recordset**.**Fields** collection.</span></span>

<span data-ttu-id="5786d-p104">添加、修改或删除 **Field** 时会出现两个问题。如果用户要删除一个 **Field** ，则在 **Fields** 集合中标识该字段以便删除。如果随后由于用户试图删除不具权限的 **Field** 而导致 **Update** 返回错误，则 **Field** 的状态将为 **adFieldPermissionDenied** **或** **adFieldPendingDelete** 。调用 [CancelUpdate](cancelupdate-method-ado.md) 方法可还原原始值并将 **Status** 设置为 **adFieldOK** 。同样，添加新的 **Field** 并提供不恰当的值也会导致 **Update** 方法返回错误。此时，新的 **Field** 将位于 **Fields** 集合中，其状态为 **adFieldPendingInsert** （或 **adFieldCantCreate** ）。可以为该新 **Field** 提供一个恰当的值并再次调用 **Update** 。注意，调用 **Resync** 则需要请求提供程序。</span><span class="sxs-lookup"><span data-stu-id="5786d-p104">Two problems can arise when adding, modifying, or deleting a **Field**. If the user deletes a **Field**, it is marked for deletion from the **Fields** collection. If the subsequent **Update** returns an error because the user tried to delete a **Field** for which they do not have permission, the **Field** will have a status of **adFieldPermissionDenied** **OR** **adFieldPendingDelete**. Calling the [CancelUpdate](cancelupdate-method-ado.md) method restores original values and sets the **Status** to **adFieldOK**. Similarly, the **Update** method may return an error because a new **Field** was added and given an inappropriate value. In that case the new **Field** will be in the **Fields** collection and have a status of **adFieldPendingInsert** and perhaps **adFieldCantCreate**. You can supply an appropriate value for the new **Field** and call **Update** again. Note that calling **Resync** instead requeries the provider.</span></span>

