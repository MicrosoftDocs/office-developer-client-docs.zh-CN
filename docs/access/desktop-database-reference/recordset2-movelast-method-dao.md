---
title: MoveLast 方法 (DAO) Recordset2
TOCTitle: MoveLast Method
ms:assetid: 32717786-c59c-ec22-666b-fc78e4265c5a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192306(v=office.15)
ms:contentKeyID: 48544079
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 829c4dd759bce86388cc65aa5b63276eec438ea0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307257"
---
# <a name="recordset2movelast-method-dao"></a><span data-ttu-id="feff0-102">MoveLast 方法 (DAO) Recordset2</span><span class="sxs-lookup"><span data-stu-id="feff0-102">Recordset2.MoveLast method (DAO)</span></span>

<span data-ttu-id="feff0-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="feff0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="feff0-104">移到指定的 **Recordset** 对象中的最后一条记录，并使该记录成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="feff0-104">Moves to the last record in a specified **Recordset** object and make that record the current record.</span></span>

## <a name="syntax"></a><span data-ttu-id="feff0-105">语法</span><span class="sxs-lookup"><span data-stu-id="feff0-105">Syntax</span></span>

<span data-ttu-id="feff0-106">*表达式*。MoveLast (***选项***)</span><span class="sxs-lookup"><span data-stu-id="feff0-106">*expression* .MoveLast(***Options***)</span></span>

<span data-ttu-id="feff0-107">*表达式*一个代表**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="feff0-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="feff0-108">参数</span><span class="sxs-lookup"><span data-stu-id="feff0-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="feff0-109">名称</span><span class="sxs-lookup"><span data-stu-id="feff0-109">Name</span></span></p></th>
<th><p><span data-ttu-id="feff0-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="feff0-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="feff0-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="feff0-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="feff0-112">说明</span><span class="sxs-lookup"><span data-stu-id="feff0-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="feff0-113"><em>Options</em></span><span class="sxs-lookup"><span data-stu-id="feff0-113"><em>Options</em></span></span></p></td>
<td><p><span data-ttu-id="feff0-114">可选</span><span class="sxs-lookup"><span data-stu-id="feff0-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="feff0-115"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="feff0-115"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="feff0-116">设置为 <strong>dbRunAsync</strong> 可异步运行对 <strong>MoveLast</strong> 的调用。</span><span class="sxs-lookup"><span data-stu-id="feff0-116">Set to <strong>dbRunAsync</strong> to rune the call to <strong>MoveLast</strong> asynchronously.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="feff0-117">注解</span><span class="sxs-lookup"><span data-stu-id="feff0-117">Remarks</span></span>

<span data-ttu-id="feff0-118">使用 **Move** 方法可以在记录间移动，而不需要应用条件。</span><span class="sxs-lookup"><span data-stu-id="feff0-118">Use the **Move** methods to move from record to record without applying a condition.</span></span>

<span data-ttu-id="feff0-p101">如果要编辑当前记录，请确保使用 **Update** 方法保存更改，然后移到另一条记录。如果在不更新的情况下移到另一条记录，则更改将会丢失，且不发出警告。</span><span class="sxs-lookup"><span data-stu-id="feff0-p101">If you edit the current record, be sure you use the **Update** method to save the changes before you move to another record. If you move to another record without updating, your changes are lost without warning.</span></span>

<span data-ttu-id="feff0-p102">在打开 **Recordset** 时，第一条记录将是当前记录，并且 **BOF** 属性为 **False**。如果 **Recordset** 不包含记录，则 **BOF** 属性为 **True**，并且不存在当前记录。</span><span class="sxs-lookup"><span data-stu-id="feff0-p102">When you open a **Recordset**, the first record is current and the **BOF** property is **False**. If the **Recordset** contains no records, the **BOF** property is **True**, and there is no current record.</span></span>

<span data-ttu-id="feff0-123">如果在使用 **MoveFirst** 或 **MoveLast** 时，第一条或最后一条记录已经是当前记录，则当前记录不会更改。</span><span class="sxs-lookup"><span data-stu-id="feff0-123">If the first or last record is already current when you use **MoveFirst** or **MoveLast**, the current record doesn't change.</span></span>

<span data-ttu-id="feff0-124">如果 recordset 引用表类型的**recordset** (仅适用于 Microsoft Access 工作区), 则移动将遵循当前索引。</span><span class="sxs-lookup"><span data-stu-id="feff0-124">If recordset refers to a table-type **Recordset** (Microsoft Access workspaces only), movement follows the current index.</span></span> <span data-ttu-id="feff0-125">可以使用 **Index** 属性设置当前索引。</span><span class="sxs-lookup"><span data-stu-id="feff0-125">You can set the current index by using the **Index** property.</span></span> <span data-ttu-id="feff0-126">如果不设置当前索引，则返回记录的顺序将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="feff0-126">If you don't set the current index, the order of returned records is undefined.</span></span>

> [!NOTE]
> <span data-ttu-id="feff0-127">[!注释] 可使用 **MoveLast** 方法完全填充动态集类型或快照集类型的 **Recordset**，以便在 **Recordset** 中提供当前的记录数。</span><span class="sxs-lookup"><span data-stu-id="feff0-127">You can use the **MoveLast** method to fully populate a dynaset- or snapshot-type **Recordset** to provide the current number of records in the **Recordset**.</span></span> <span data-ttu-id="feff0-128">但是，如果以这种方式使用 **MoveLast**，可能会减慢应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="feff0-128">However, if you use **MoveLast** in this way, you can slow down your application's performance.</span></span> <span data-ttu-id="feff0-129">如果绝对有必要获取有关最近打开的 **Recordset** 的准确记录计数，只应使用 **MoveLast** 获取记录计数。</span><span class="sxs-lookup"><span data-stu-id="feff0-129">You should only use **MoveLast** to get a record count if it is absolutely necessary to obtain an accurate record count on a newly opened **Recordset**.</span></span> 
>
> <span data-ttu-id="feff0-130">如果将 **dbRunAsync** 常量用于 **MoveLast**，则方法调用是异步的。</span><span class="sxs-lookup"><span data-stu-id="feff0-130">If you use the **dbRunAsync** constant with **MoveLast**, the method call is asynchronous.</span></span> <span data-ttu-id="feff0-131">可以使用 **StillExecuting** 属性确定何时完全填充了 **Recordset**，并可使用 **Cancel** 方法终止执行异步的 **MoveLast** 方法调用。</span><span class="sxs-lookup"><span data-stu-id="feff0-131">You can use the **StillExecuting** property to determine when the **Recordset** is fully populated, and you can use the **Cancel** method to terminate execution of the asynchronous **MoveLast** method call.</span></span>

<span data-ttu-id="feff0-132">您不能在仅向前类型的**Recordset**对象上使用**MoveFirst**、 **MoveLast**和**MovePrevious**方法。</span><span class="sxs-lookup"><span data-stu-id="feff0-132">You can't use the **MoveFirst**, **MoveLast**, and **MovePrevious** methods on a forward–only–type **Recordset** object.</span></span>

<span data-ttu-id="feff0-133">若要将 **Recordset** 对象中的当前记录的位置向前或向后移动指定的记录数，请使用 **Move** 方法。</span><span class="sxs-lookup"><span data-stu-id="feff0-133">To move the position of the current record in a **Recordset** object a specific number of records forward or backward, use the **Move** method.</span></span>

