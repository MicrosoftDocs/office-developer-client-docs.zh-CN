---
title: CancelBatch 方法 (ADO)
TOCTitle: CancelBatch Method (ADO)
ms:assetid: be7bf073-ed0b-e24c-7ec0-b7379236782a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249925(v=office.15)
ms:contentKeyID: 48547463
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cbc16d01e04bbcff7ff28ccc8e7cb4f3fd6f3dec
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467903"
---
# <a name="cancelbatch-method-ado"></a><span data-ttu-id="42fde-102">CancelBatch 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="42fde-102">CancelBatch Method (ADO)</span></span>


<span data-ttu-id="42fde-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="42fde-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="42fde-104">用于取消挂起的批更新。</span><span class="sxs-lookup"><span data-stu-id="42fde-104">Cancels a pending batch update.</span></span>

## <a name="syntax"></a><span data-ttu-id="42fde-105">语法</span><span class="sxs-lookup"><span data-stu-id="42fde-105">Syntax</span></span>

<span data-ttu-id="42fde-106">*记录集*。CancelBatch *AffectRecords*</span><span class="sxs-lookup"><span data-stu-id="42fde-106">*recordset*.CancelBatch *AffectRecords*</span></span>

## <a name="parameters"></a><span data-ttu-id="42fde-107">参数</span><span class="sxs-lookup"><span data-stu-id="42fde-107">Parameters</span></span>

  - <span data-ttu-id="42fde-108">*AffectRecords*</span><span class="sxs-lookup"><span data-stu-id="42fde-108">*AffectRecords*</span></span>

  - <span data-ttu-id="42fde-p101">可选。[AffectEnum](affectenum.md) 值，用于指示 **CancelBatch** 方法将影响的记录数。</span><span class="sxs-lookup"><span data-stu-id="42fde-p101">Optional. An [AffectEnum](affectenum.md) value that indicates how many records the **CancelBatch** method will affect.</span></span>

## <a name="remarks"></a><span data-ttu-id="42fde-111">备注</span><span class="sxs-lookup"><span data-stu-id="42fde-111">Remarks</span></span>

<span data-ttu-id="42fde-p102">**CancelBatch** 方法用于取消处于批更新模式下的 [Recordset](recordset-object-ado.md) 中的任何挂起的更新。如果 **Recordset** 处于即时更新模式下，则调用无 **adAffectCurrent** 的 **CancelBatch** 将产生错误。</span><span class="sxs-lookup"><span data-stu-id="42fde-p102">Use the **CancelBatch** method to cancel any pending updates in a [Recordset](recordset-object-ado.md) in batch update mode. If the **Recordset** is in immediate update mode, calling **CancelBatch** without **adAffectCurrent** generates an error.</span></span>

<span data-ttu-id="42fde-p103">如果当调用 **CancelBatch** 时正在编辑当前记录或添加新记录，那么 ADO 首先会调用 [CancelUpdate](cancelupdate-method-ado.md) 方法取消缓存的所有更改。之后，将取消 **Recordset** 中所有挂起的更改。</span><span class="sxs-lookup"><span data-stu-id="42fde-p103">If you are editing the current record or are adding a new record when you call **CancelBatch**, ADO first calls the [CancelUpdate](cancelupdate-method-ado.md) method to cancel any cached changes. After that, all pending changes in the **Recordset** are canceled.</span></span>

<span data-ttu-id="42fde-p104">在调用 **CancelBatch** 之后，有可能无法确定当前记录，尤其是如果当时正在添加新记录。因此，在调用 **CancelBatch** 之后，最好将当前记录位置设置为 **Recordset** 中的已知位置。例如，调用 [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="42fde-p104">It's possible that the current record will be indeterminable after a **CancelBatch** call, especially if you were in the process of adding a new record. For this reason, it is prudent to set the current record position to a known location in the **Recordset** after the **CancelBatch** call. For example, call the [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) method.</span></span>

<span data-ttu-id="42fde-p105">如果由于与基础数据冲突（例如，记录已被其他用户删除）使得取消挂起更新的尝试失败，则提供程序将向 [Errors](errors-collection-ado.md) 集合返回警告，但不会停止程序的执行。只有当请求的所有记录都存在冲突时，才会发生运行时错误。可以使用 [Filter](filter-property-ado.md) 属性 (**adFilterAffectedRecords**) 和 [Status](status-property-ado-recordset.md) 属性查找存在冲突的记录。</span><span class="sxs-lookup"><span data-stu-id="42fde-p105">If the attempt to cancel the pending updates fails because of a conflict with the underlying data (for example, a record has been deleted by another user), the provider returns warnings to the [Errors](errors-collection-ado.md) collection but does not halt program execution. A run-time error occurs only if there are conflicts on all the requested records. Use the [Filter](filter-property-ado.md) property (**adFilterAffectedRecords**) and the [Status](status-property-ado-recordset.md) property to locate records with conflicts.</span></span>
