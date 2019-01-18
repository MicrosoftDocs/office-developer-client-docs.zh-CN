---
title: Recordset.MoveLast 方法 (DAO)
TOCTitle: MoveLast method
ms:assetid: fc0f7a33-1f55-9f5b-b00d-1b81f49b1c3e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837192(v=office.15)
ms:contentKeyID: 48548881
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 79799742499e163a43d51a2d8553adcadf27b36d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715268"
---
# <a name="recordsetmovelast-method-dao"></a><span data-ttu-id="6e674-102">Recordset.MoveLast 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="6e674-102">Recordset.MoveLast method (DAO)</span></span>

<span data-ttu-id="6e674-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6e674-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6e674-104">移到指定的 **Recordset** 对象中的最后一条记录，并使该记录成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="6e674-104">Moves to the last record in a specified **Recordset** object and make that record the current record.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e674-105">语法</span><span class="sxs-lookup"><span data-stu-id="6e674-105">Syntax</span></span>

<span data-ttu-id="6e674-106">*表达式*。MoveLast （***选项***）</span><span class="sxs-lookup"><span data-stu-id="6e674-106">*expression* .MoveLast(***Options***)</span></span>

<span data-ttu-id="6e674-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6e674-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="6e674-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="6e674-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6e674-109">Name</span><span class="sxs-lookup"><span data-stu-id="6e674-109">Name</span></span></p></th>
<th><p><span data-ttu-id="6e674-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="6e674-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="6e674-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="6e674-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="6e674-112">说明</span><span class="sxs-lookup"><span data-stu-id="6e674-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e674-113"><em>Options</em></span><span class="sxs-lookup"><span data-stu-id="6e674-113"><em>Options</em></span></span></p></td>
<td><p><span data-ttu-id="6e674-114">可选</span><span class="sxs-lookup"><span data-stu-id="6e674-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="6e674-115"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="6e674-115"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="6e674-116">设置为 <strong>dbRunAsync</strong> 可异步运行对 <strong>MoveLast</strong> 的调用。</span><span class="sxs-lookup"><span data-stu-id="6e674-116">Set to <strong>dbRunAsync</strong> to rune the call to <strong>MoveLast</strong> asynchronously.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="6e674-117">注解</span><span class="sxs-lookup"><span data-stu-id="6e674-117">Remarks</span></span>

<span data-ttu-id="6e674-118">使用 **Move** 方法可以在记录间移动，而不需要应用条件。</span><span class="sxs-lookup"><span data-stu-id="6e674-118">Use the **Move** methods to move from record to record without applying a condition.</span></span>

<span data-ttu-id="6e674-p101">如果要编辑当前记录，请确保使用 **Update** 方法保存更改，然后移到另一条记录。如果在不更新的情况下移到另一条记录，则更改将会丢失，且不发出警告。</span><span class="sxs-lookup"><span data-stu-id="6e674-p101">If you edit the current record, be sure you use the **Update** method to save the changes before you move to another record. If you move to another record without updating, your changes are lost without warning.</span></span>

<span data-ttu-id="6e674-p102">在打开 **Recordset** 时，第一条记录将是当前记录，并且 **BOF** 属性为 **False**。如果 **Recordset** 不包含记录，则 **BOF** 属性为 **True**，并且不存在当前记录。</span><span class="sxs-lookup"><span data-stu-id="6e674-p102">When you open a **Recordset**, the first record is current and the **BOF** property is **False**. If the **Recordset** contains no records, the **BOF** property is **True**, and there is no current record.</span></span>

<span data-ttu-id="6e674-123">如果在使用 **MoveFirst** 或 **MoveLast** 时，第一条或最后一条记录已经是当前记录，则当前记录不会更改。</span><span class="sxs-lookup"><span data-stu-id="6e674-123">If the first or last record is already current when you use **MoveFirst** or **MoveLast**, the current record doesn't change.</span></span>

<span data-ttu-id="6e674-124">如果 recordset 引用表类型**Recordset** （仅限 Microsoft Access 工作区），则移动遵循当前索引。</span><span class="sxs-lookup"><span data-stu-id="6e674-124">If recordset refers to a table-type **Recordset** (Microsoft Access workspaces only), movement follows the current index.</span></span> <span data-ttu-id="6e674-125">可以使用 **Index** 属性设置当前索引。</span><span class="sxs-lookup"><span data-stu-id="6e674-125">You can set the current index by using the **Index** property.</span></span> <span data-ttu-id="6e674-126">如果不设置当前索引，则返回记录的顺序将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="6e674-126">If you don't set the current index, the order of returned records is undefined.</span></span>

> [!NOTE]
> <span data-ttu-id="6e674-127">[!注释] 可使用 **MoveLast** 方法完全填充动态集类型或快照集类型的 **Recordset**，以便在 **Recordset** 中提供当前的记录数。</span><span class="sxs-lookup"><span data-stu-id="6e674-127">You can use the **MoveLast** method to fully populate a dynaset- or snapshot-type **Recordset** to provide the current number of records in the **Recordset**.</span></span> <span data-ttu-id="6e674-128">但是，如果以这种方式使用 **MoveLast**，可能会减慢应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="6e674-128">However, if you use **MoveLast** in this way, you can slow down your application's performance.</span></span> <span data-ttu-id="6e674-129">如果绝对有必要获取有关最近打开的 **Recordset** 的准确记录计数，只应使用 **MoveLast** 获取记录计数。</span><span class="sxs-lookup"><span data-stu-id="6e674-129">You should only use **MoveLast** to get a record count if it is absolutely necessary to obtain an accurate record count on a newly opened **Recordset**.</span></span> 
> 
> <span data-ttu-id="6e674-130">如果将 **dbRunAsync** 常量用于 **MoveLast**，则方法调用是异步的。</span><span class="sxs-lookup"><span data-stu-id="6e674-130">If you use the **dbRunAsync** constant with **MoveLast**, the method call is asynchronous.</span></span> <span data-ttu-id="6e674-131">可以使用 **StillExecuting** 属性确定何时完全填充了 **Recordset**，并可使用 **Cancel** 方法终止执行异步的 **MoveLast** 方法调用。</span><span class="sxs-lookup"><span data-stu-id="6e674-131">You can use the **StillExecuting** property to determine when the **Recordset** is fully populated, and you can use the **Cancel** method to terminate execution of the asynchronous **MoveLast** method call.</span></span>

<span data-ttu-id="6e674-132">不能对仅向前类型**Recordset**对象使用**MoveFirst**、 **MoveLast**和**MovePrevious**方法。</span><span class="sxs-lookup"><span data-stu-id="6e674-132">You can't use the **MoveFirst**, **MoveLast**, and **MovePrevious** methods on a forward–only–type **Recordset** object.</span></span>

<span data-ttu-id="6e674-133">若要将 **Recordset** 对象中的当前记录的位置向前或向后移动指定的记录数，请使用 **Move** 方法。</span><span class="sxs-lookup"><span data-stu-id="6e674-133">To move the position of the current record in a **Recordset** object a specific number of records forward or backward, use the **Move** method.</span></span>

