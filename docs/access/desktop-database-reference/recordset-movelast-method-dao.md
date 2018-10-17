---
title: Recordset.MoveLast Method (DAO)
TOCTitle: MoveLast Method
ms:assetid: fc0f7a33-1f55-9f5b-b00d-1b81f49b1c3e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837192(v=office.15)
ms:contentKeyID: 48548881
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c154a576a4ac1aedf555ba8164bc243fe49a3841
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467726"
---
# <a name="recordsetmovelast-method-dao"></a><span data-ttu-id="9f0b9-102">Recordset.MoveLast Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="9f0b9-102">Recordset.MoveLast Method (DAO)</span></span>


<span data-ttu-id="9f0b9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9f0b9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9f0b9-104">移到指定的 **Recordset** 对象中的最后一条记录，并使该记录成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-104">Moves to the last record in a specified **Recordset** object and make that record the current record.</span></span>

## <a name="syntax"></a><span data-ttu-id="9f0b9-105">语法</span><span class="sxs-lookup"><span data-stu-id="9f0b9-105">Syntax</span></span>

<span data-ttu-id="9f0b9-106">*表达式*。MoveLast （***选项***）</span><span class="sxs-lookup"><span data-stu-id="9f0b9-106">*expression* .MoveLast(***Options***)</span></span>

<span data-ttu-id="9f0b9-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-107">*expression* A variable that represents a **Recordset** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="9f0b9-108">参数</span><span class="sxs-lookup"><span data-stu-id="9f0b9-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9f0b9-109">名称</span><span class="sxs-lookup"><span data-stu-id="9f0b9-109">Name</span></span></p></th>
<th><p><span data-ttu-id="9f0b9-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="9f0b9-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="9f0b9-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="9f0b9-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="9f0b9-112">说明</span><span class="sxs-lookup"><span data-stu-id="9f0b9-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f0b9-113">Options</span><span class="sxs-lookup"><span data-stu-id="9f0b9-113">Options</span></span></p></td>
<td><p><span data-ttu-id="9f0b9-114">可选</span><span class="sxs-lookup"><span data-stu-id="9f0b9-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="9f0b9-115"><strong>Long</strong></span><span class="sxs-lookup"><span data-stu-id="9f0b9-115"><strong>Long</strong></span></span></p></td>
<td><p><span data-ttu-id="9f0b9-116">设置为 <strong>dbRunAsync</strong> 可异步运行对 <strong>MoveLast</strong> 的调用。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-116">Set to <strong>dbRunAsync</strong> to rune the call to <strong>MoveLast</strong> asynchronously.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="9f0b9-117">注解</span><span class="sxs-lookup"><span data-stu-id="9f0b9-117">Remarks</span></span>

<span data-ttu-id="9f0b9-118">使用 **Move** 方法可以在记录间移动，而不需要应用条件。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-118">Use the **Move** methods to move from record to record without applying a condition.</span></span>

<span data-ttu-id="9f0b9-p101">如果要编辑当前记录，请确保使用 **Update** 方法保存更改，然后移到另一条记录。如果在不更新的情况下移到另一条记录，则更改将会丢失，且不发出警告。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-p101">If you edit the current record, be sure you use the **Update** method to save the changes before you move to another record. If you move to another record without updating, your changes are lost without warning.</span></span>

<span data-ttu-id="9f0b9-p102">在打开 **Recordset** 时，第一条记录将是当前记录，并且 **BOF** 属性为 **False**。如果 **Recordset** 不包含记录，则 **BOF** 属性为 **True**，并且不存在当前记录。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-p102">When you open a **Recordset**, the first record is current and the **BOF** property is **False**. If the **Recordset** contains no records, the **BOF** property is **True**, and there is no current record.</span></span>

<span data-ttu-id="9f0b9-123">如果在使用 **MoveFirst** 或 **MoveLast** 时，第一条或最后一条记录已经是当前记录，则当前记录不会更改。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-123">If the first or last record is already current when you use **MoveFirst** or **MoveLast**, the current record doesn't change.</span></span>

<span data-ttu-id="9f0b9-124">如果 recordset 引用表类型**Recordset** （仅限 Microsoft Access 工作区），则移动遵循当前索引。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-124">If recordset refers to a table-type **Recordset** (Microsoft Access workspaces only), movement follows the current index.</span></span> <span data-ttu-id="9f0b9-125">可以使用 **Index** 属性设置当前索引。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-125">You can set the current index by using the **Index** property.</span></span> <span data-ttu-id="9f0b9-126">如果不设置当前索引，则返回记录的顺序将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-126">If you don't set the current index, the order of returned records is undefined.</span></span>


> [!NOTE]
> <P><span data-ttu-id="9f0b9-p104">[!注释] 可使用 <STRONG>MoveLast</STRONG> 方法完全填充动态集类型或快照集类型的 <STRONG>Recordset</STRONG>，以便在 <STRONG>Recordset</STRONG> 中提供当前的记录数。但是，如果以这种方式使用 <STRONG>MoveLast</STRONG>，可能会减慢应用程序的性能。如果绝对有必要获取有关最近打开的 <STRONG>Recordset</STRONG> 的准确记录计数，只应使用 <STRONG>MoveLast</STRONG> 获取记录计数。如果将 <STRONG>dbRunAsync</STRONG> 常量用于 <STRONG>MoveLast</STRONG>，则方法调用是异步的。可以使用 <STRONG>StillExecuting</STRONG> 属性确定何时完全填充了 <STRONG>Recordset</STRONG>，并可使用 <STRONG>Cancel</STRONG> 方法终止执行异步的 <STRONG>MoveLast</STRONG> 方法调用。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-p104">You can use the <STRONG>MoveLast</STRONG> method to fully populate a dynaset- or snapshot-type <STRONG>Recordset</STRONG> to provide the current number of records in the <STRONG>Recordset</STRONG>. However, if you use <STRONG>MoveLast</STRONG> in this way, you can slow down your application's performance. You should only use <STRONG>MoveLast</STRONG> to get a record count if it is absolutely necessary to obtain an accurate record count on a newly opened <STRONG>Recordset</STRONG>. If you use the <STRONG>dbRunAsync</STRONG> constant with <STRONG>MoveLast</STRONG>, the method call is asynchronous. You can use the <STRONG>StillExecuting</STRONG> property to determine when the <STRONG>Recordset</STRONG> is fully populated, and you can use the <STRONG>Cancel</STRONG> method to terminate execution of the asynchronous <STRONG>MoveLast</STRONG> method call.</span></span></P>



<span data-ttu-id="9f0b9-132">不能对仅向前类型**Recordset**对象使用**MoveFirst**、 **MoveLast**和**MovePrevious**方法。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-132">You can't use the **MoveFirst**, **MoveLast**, and **MovePrevious** methods on a forward–only–type **Recordset** object.</span></span>

<span data-ttu-id="9f0b9-133">若要将 **Recordset** 对象中的当前记录的位置向前或向后移动指定的记录数，请使用 **Move** 方法。</span><span class="sxs-lookup"><span data-stu-id="9f0b9-133">To move the position of the current record in a **Recordset** object a specific number of records forward or backward, use the **Move** method.</span></span>
