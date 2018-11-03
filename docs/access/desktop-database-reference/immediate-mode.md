---
title: 立即模式 （访问桌面数据库参考 （英文）
TOCTitle: Immediate mode
ms:assetid: 61bd3645-6e84-2e3a-7814-37d8c1247df0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249362(v=office.15)
ms:contentKeyID: 48545220
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b6401e7954325eded85b70b9edb5d164e857d113
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947859"
---
# <a name="immediate-mode"></a><span data-ttu-id="cb4f5-102">立即模式</span><span class="sxs-lookup"><span data-stu-id="cb4f5-102">Immediate mode</span></span>


<span data-ttu-id="cb4f5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cb4f5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cb4f5-p101">如果将 **LockType** 属性设置为 **adLockOptimistic** 或 **adLockPessimistic** ，则立即模式生效。在立即模式下，一旦通过调用 **Update** 方法声明对行的操作完成，则对记录的更改就会传播到数据源。</span><span class="sxs-lookup"><span data-stu-id="cb4f5-p101">Immediate mode is in effect when the **LockType** property is set to **adLockOptimistic** or **adLockPessimistic**. In immediate mode, changes to a record are propagated to the data source as soon as you declare the work on a row complete by calling the **Update** method.</span></span>

## <a name="calling-update"></a><span data-ttu-id="cb4f5-106">调用 Update</span><span class="sxs-lookup"><span data-stu-id="cb4f5-106">Calling Update</span></span>

<span data-ttu-id="cb4f5-p102">如果在调用 **Update** 方法之前离开了正在添加或编辑的记录，ADO 将自动调用 **Update** 以保存更改。如果要取消对当前记录的任何更改或放弃新添加的记录，则必须在导航之前调用 **CancelUpdate** 方法。</span><span class="sxs-lookup"><span data-stu-id="cb4f5-p102">If you move from the record you are adding or editing before calling the **Update** method, ADO will automatically call **Update** to save the changes. You must call the **CancelUpdate** method before navigation if you want to cancel any changes made to the current record or discard a newly added record.</span></span>

<span data-ttu-id="cb4f5-109">调用 **Update** 方法之后，当前记录仍然是当前记录。</span><span class="sxs-lookup"><span data-stu-id="cb4f5-109">The current record remains current after you call the **Update** method.</span></span>

## <a name="cancelupdate"></a><span data-ttu-id="cb4f5-110">CancelUpdate</span><span class="sxs-lookup"><span data-stu-id="cb4f5-110">CancelUpdate</span></span>

<span data-ttu-id="cb4f5-p103">使用 **CancelUpdate** 方法可以取消对当前行的任何更改或放弃新添加的行。在调用 **Update** 方法之后，不能取消对当前行或新行的更改，除非更改是可以用 **RollbackTrans** 方法回滚的事务的一部分，或者是批更新的一部分。在批更新情况下，可以用 **CancelUpdate** 或 **CancelBatch** 方法取消 **Update** 。</span><span class="sxs-lookup"><span data-stu-id="cb4f5-p103">Use the **CancelUpdate** method to cancel any changes made to the current row or to discard a newly added row. You cannot cancel changes to the current row or a new row after you call the **Update** method, unless the changes are either part of a transaction that you can roll back with the **RollbackTrans** method or part of a batch update. In the case of a batch update, you can cancel the **Update** with the **CancelUpdate** or **CancelBatch** method.</span></span>

<span data-ttu-id="cb4f5-114">如果调用 **CancelUpdate** 方法时正在添加新行，则当前行将变成调用 **AddNew** 之前的当前行。</span><span class="sxs-lookup"><span data-stu-id="cb4f5-114">If you are adding a new row when you call the **CancelUpdate** method, the current row becomes the row that was current before the **AddNew** call.</span></span>

<span data-ttu-id="cb4f5-115">如果还没有更改当前行或添加新行，则调用 **CancelUpdate** 方法会生成错误。</span><span class="sxs-lookup"><span data-stu-id="cb4f5-115">If you have not changed the current row or added a new row, calling the **CancelUpdate** method generates an error.</span></span>

