---
title: Status 属性 (ADO Recordset)
TOCTitle: Status Property (ADO Recordset)
ms:assetid: bf3ccb36-c985-5fae-4f76-c48a0e20e6f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249930(v=office.15)
ms:contentKeyID: 48547482
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c053ec9f84de4aa56513081144e23f044c72effc
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876629"
---
# <a name="status-property-ado-recordset"></a><span data-ttu-id="9fa09-102">Status 属性 (ADO Recordset)</span><span class="sxs-lookup"><span data-stu-id="9fa09-102">Status Property (ADO Recordset)</span></span>


<span data-ttu-id="9fa09-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9fa09-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9fa09-104">指示与批更新或其他批量操作相关的当前记录的状态。</span><span class="sxs-lookup"><span data-stu-id="9fa09-104">Indicates the status of the current record with respect to batch updates or other bulk operations.</span></span>

## <a name="return-value"></a><span data-ttu-id="9fa09-105">返回值</span><span class="sxs-lookup"><span data-stu-id="9fa09-105">Return value</span></span>

<span data-ttu-id="9fa09-106">返回一个或多个 [RecordStatusEnum](recordstatusenum.md) 值的总和。</span><span class="sxs-lookup"><span data-stu-id="9fa09-106">Returns a sum of one or more [RecordStatusEnum](recordstatusenum.md) values.</span></span>

## <a name="remarks"></a><span data-ttu-id="9fa09-107">备注</span><span class="sxs-lookup"><span data-stu-id="9fa09-107">Remarks</span></span>

<span data-ttu-id="9fa09-p101">使用 **Status** 属性可查看在批更新期间修改的记录有哪些更改被挂起。也可使用 **Status** 属性查看执行大量操作时失败的记录的状态。例如，调用 [Recordset](resync-method-ado.md) 对象的 [Resync](updatebatch-method-ado.md)、[UpdateBatch](cancelbatch-method-ado.md) 或 [CancelBatch](recordset-object-ado.md) 方法，或者将 [Recordset](filter-property-ado.md) 对象的 **Filter** 属性设置为书签数组。使用此属性，可确定指定记录失败的原因，并据此将问题解决。</span><span class="sxs-lookup"><span data-stu-id="9fa09-p101">Use the **Status** property to see what changes are pending for records modified during batch updating. You can also use the **Status** property to view the status of records that fail during bulk operations, such as when you call the [Resync](resync-method-ado.md), [UpdateBatch](updatebatch-method-ado.md), or [CancelBatch](cancelbatch-method-ado.md) methods on a [Recordset](recordset-object-ado.md) object, or set the [Filter](filter-property-ado.md) property on a **Recordset** object to an array of bookmarks. With this property, you can determine how a given record failed and resolve it accordingly.</span></span>

