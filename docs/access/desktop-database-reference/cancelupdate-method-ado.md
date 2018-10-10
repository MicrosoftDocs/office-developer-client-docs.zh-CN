---
title: CancelUpdate 方法 (ADO)
TOCTitle: CancelUpdate Method (ADO)
ms:assetid: 2bd4d168-ba52-7786-5046-44febeda88e1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249065(v=office.15)
ms:contentKeyID: 48543938
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6aaf4a7e9c94864c5cdd43ad764a305c248718b4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468588"
---
# <a name="cancelupdate-method-ado"></a><span data-ttu-id="5f393-102">CancelUpdate 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="5f393-102">CancelUpdate Method (ADO)</span></span>


<span data-ttu-id="5f393-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5f393-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="5f393-104">在调用 [Update](recordset-object-ado.md) 方法之前，取消对 [Recordset](fields-collection-ado.md) 对象的当前行或新行，或对 [Record](record-object-ado.md) 对象的 [Fields](update-method-ado.md) 集合所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="5f393-104">Cancels any changes made to the current or new row of a [Recordset](recordset-object-ado.md) object, or the [Fields](fields-collection-ado.md) collection of a [Record](record-object-ado.md) object, before calling the [Update](update-method-ado.md) method.</span></span>

## <a name="syntax"></a><span data-ttu-id="5f393-105">语法</span><span class="sxs-lookup"><span data-stu-id="5f393-105">Syntax</span></span>

<span data-ttu-id="5f393-106">*记录集*。CancelUpdate</span><span class="sxs-lookup"><span data-stu-id="5f393-106">*recordset*.CancelUpdate</span></span>

<span data-ttu-id="5f393-107">*记录*。*字段*。CancelUpdate</span><span class="sxs-lookup"><span data-stu-id="5f393-107">*record*.*Fields*.CancelUpdate</span></span>

## <a name="remarks"></a><span data-ttu-id="5f393-108">说明</span><span class="sxs-lookup"><span data-stu-id="5f393-108">Remarks</span></span>

<span data-ttu-id="5f393-109">**Recordset**</span><span class="sxs-lookup"><span data-stu-id="5f393-109">**Recordset**</span></span>

<span data-ttu-id="5f393-p101">可以使用 **CancelUpdate** 方法取消对当前行所做的任何更改或放弃新添加的行。但调用 **Update** 方法之后，便无法取消对当前行或新行所做的更改，除非更改是可以用 [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) 方法回滚的事务的一部分或批更新的一部分。在批更新情况下，可以用 **CancelUpdate** 或 **CancelBatch** 方法取消 [Update](cancelbatch-method-ado.md) 。</span><span class="sxs-lookup"><span data-stu-id="5f393-p101">Use the **CancelUpdate** method to cancel any changes made to the current row or to discard a newly added row. You cannot cancel changes to the current row or a new row after you call the **Update** method, unless the changes are either part of a transaction that you can roll back with the [RollbackTrans](begintrans-committrans-and-rollbacktrans-methods-ado.md) method, or part of a batch update. In the case of a batch update, you can cancel the **Update** with the **CancelUpdate** or [CancelBatch](cancelbatch-method-ado.md) method.</span></span>

<span data-ttu-id="5f393-113">如果调用 **CancelUpdate** 方法时正在添加新行，则当前行将变成调用 [AddNew](addnew-method-ado.md) 之前的当前行。</span><span class="sxs-lookup"><span data-stu-id="5f393-113">If you are adding a new row when you call the **CancelUpdate** method, the current row becomes the row that was current before the [AddNew](addnew-method-ado.md) call.</span></span>

<span data-ttu-id="5f393-p102">如果正处于编辑模式下，并希望离开当前记录（例如，用 [Move](move-method-ado.md)、[NextRecordset](nextrecordset-method-ado.md) 或 [Close](close-method-ado.md)），那么可以使用 **CancelUpdate** 取消任何挂起的更改。如果更新无法成功发布到数据源，则可能需要执行以上操作（例如，如果删除尝试由于违反了参照完整性而失败，则在调用 **Delete** 之后将离开处于编辑模式下的 [Recordset](delete-method-ado-recordset.md) ）。</span><span class="sxs-lookup"><span data-stu-id="5f393-p102">If you are in edit mode and want to move off the current record (for example, with [Move](move-method-ado.md), [NextRecordset](nextrecordset-method-ado.md), or [Close](close-method-ado.md)), you can use **CancelUpdate** to cancel any pending changes. You may need to do this if the update cannot successfully be posted to the data source (for example, an attempted delete that fails due to referential integrity violations will leave the **Recordset** in edit mode after a call to [Delete](delete-method-ado-recordset.md)).</span></span>

<span data-ttu-id="5f393-116">**Record**</span><span class="sxs-lookup"><span data-stu-id="5f393-116">**Record**</span></span>

<span data-ttu-id="5f393-p103">可以使用 **CancelUpdate** 方法取消 [Field](field-object-ado.md) 对象的任何挂起的插入或删除，以及取消现有字段的挂起更新并将其还原为原来的值。 [Fields](status-property-ado-recordset.md) 集合中所有字段的 **Status** 属性均设置为 **adFieldOK** 。</span><span class="sxs-lookup"><span data-stu-id="5f393-p103">The **CancelUpdate** method cancels any pending insertions or deletions of [Field](field-object-ado.md) objects, and cancels pending updates of existing fields and restores them to their original values. The [Status](status-property-ado-recordset.md) property of all fields in the **Fields** collection is set to **adFieldOK**.</span></span>

