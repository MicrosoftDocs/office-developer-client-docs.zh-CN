---
title: Recordset2.MoveFirst Method (DAO)
TOCTitle: MoveFirst Method
ms:assetid: 74b186d0-8f6a-d136-a563-04f58d67b122
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195879(v=office.15)
ms:contentKeyID: 48545667
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2103bc1d212900153ae7e1df7f4fbb394a033646
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466562"
---
# <a name="recordset2movefirst-method-dao"></a><span data-ttu-id="4f106-102">Recordset2.MoveFirst Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="4f106-102">Recordset2.MoveFirst Method (DAO)</span></span>


<span data-ttu-id="4f106-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4f106-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4f106-104">移到指定的 **Recordset** 对象中的第一条记录，并使该记录成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="4f106-104">Moves to the first record in a specified **Recordset** object and make that record the current record.</span></span>

## <a name="syntax"></a><span data-ttu-id="4f106-105">语法</span><span class="sxs-lookup"><span data-stu-id="4f106-105">Syntax</span></span>

<span data-ttu-id="4f106-106">*表达式*。MoveFirst</span><span class="sxs-lookup"><span data-stu-id="4f106-106">*expression* .MoveFirst</span></span>

<span data-ttu-id="4f106-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4f106-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f106-108">注解</span><span class="sxs-lookup"><span data-stu-id="4f106-108">Remarks</span></span>

<span data-ttu-id="4f106-109">使用 **Move** 方法可以在记录间移动，而不需要应用条件。</span><span class="sxs-lookup"><span data-stu-id="4f106-109">Use the **Move** methods to move from record to record without applying a condition.</span></span>

<span data-ttu-id="4f106-p101">如果要编辑当前记录，请确保使用 **Update** 方法保存更改，然后移到另一条记录。如果在不更新的情况下移到另一条记录，则更改将会丢失，且不发出警告。</span><span class="sxs-lookup"><span data-stu-id="4f106-p101">If you edit the current record, be sure you use the **Update** method to save the changes before you move to another record. If you move to another record without updating, your changes are lost without warning.</span></span>

<span data-ttu-id="4f106-p102">在打开 **Recordset** 时，第一条记录将是当前记录，并且 **BOF** 属性为 **False**。如果 **Recordset** 不包含记录，则 **BOF** 属性为 **True**，并且不存在当前记录。</span><span class="sxs-lookup"><span data-stu-id="4f106-p102">When you open a **Recordset**, the first record is current and the **BOF** property is **False**. If the **Recordset** contains no records, the **BOF** property is **True**, and there is no current record.</span></span>

<span data-ttu-id="4f106-114">如果在使用 **MoveFirst** 或 **MoveLast** 时，第一条或最后一条记录已经是当前记录，则当前记录不会更改。</span><span class="sxs-lookup"><span data-stu-id="4f106-114">If the first or last record is already current when you use **MoveFirst** or **MoveLast**, the current record doesn't change.</span></span>

<span data-ttu-id="4f106-115">如果 recordset 引用表类型**Recordset** （仅限 Microsoft Access 工作区），则移动遵循当前索引。</span><span class="sxs-lookup"><span data-stu-id="4f106-115">If recordset refers to a table-type **Recordset** (Microsoft Access workspaces only), movement follows the current index.</span></span> <span data-ttu-id="4f106-116">可以使用 **Index** 属性设置当前索引。</span><span class="sxs-lookup"><span data-stu-id="4f106-116">You can set the current index by using the **Index** property.</span></span> <span data-ttu-id="4f106-117">如果不设置当前索引，则返回记录的顺序将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="4f106-117">If you don't set the current index, the order of returned records is undefined.</span></span>

<span data-ttu-id="4f106-118">不能对仅向前类型**Recordset**对象使用**MoveFirst**、 **MoveLast**和**MovePrevious**方法。</span><span class="sxs-lookup"><span data-stu-id="4f106-118">You can't use the **MoveFirst**, **MoveLast**, and **MovePrevious** methods on a forward–only–type **Recordset** object.</span></span>

<span data-ttu-id="4f106-119">若要将 **Recordset** 对象中的当前记录的位置向前或向后移动指定的记录数，请使用 **Move** 方法。</span><span class="sxs-lookup"><span data-stu-id="4f106-119">To move the position of the current record in a **Recordset** object a specific number of records forward or backward, use the **Move** method.</span></span>

