---
title: MovePrevious 方法 (DAO) Recordset2
TOCTitle: MovePrevious Method
ms:assetid: 8c433810-4b19-e7c1-3cee-a0bc50b23e8a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197336(v=office.15)
ms:contentKeyID: 48546235
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9753d3bbb586e2c1bd44755deb529758d8eab060
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307243"
---
# <a name="recordset2moveprevious-method-dao"></a><span data-ttu-id="9c8d4-102">MovePrevious 方法 (DAO) Recordset2</span><span class="sxs-lookup"><span data-stu-id="9c8d4-102">Recordset2.MovePrevious method (DAO)</span></span>


<span data-ttu-id="9c8d4-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="9c8d4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9c8d4-104">移到指定的 **Recordset** 对象中的上一条记录，并使该记录成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="9c8d4-104">Moves to the previous record in a specified **Recordset** object and make that record the current record.</span></span>

## <a name="syntax"></a><span data-ttu-id="9c8d4-105">语法</span><span class="sxs-lookup"><span data-stu-id="9c8d4-105">Syntax</span></span>

<span data-ttu-id="9c8d4-106">*表达式*。MovePrevious</span><span class="sxs-lookup"><span data-stu-id="9c8d4-106">*expression* .MovePrevious</span></span>

<span data-ttu-id="9c8d4-107">*表达式*一个代表**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="9c8d4-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c8d4-108">注解</span><span class="sxs-lookup"><span data-stu-id="9c8d4-108">Remarks</span></span>

<span data-ttu-id="9c8d4-109">使用 **Move** 方法可以在记录间移动，而不需要应用条件。</span><span class="sxs-lookup"><span data-stu-id="9c8d4-109">Use the **Move** methods to move from record to record without applying a condition.</span></span>

<span data-ttu-id="9c8d4-p101">如果要编辑当前记录，请确保使用 **Update** 方法保存更改，然后移到另一条记录。如果在不更新的情况下移到另一条记录，则更改将会丢失，且不发出警告。</span><span class="sxs-lookup"><span data-stu-id="9c8d4-p101">If you edit the current record, be sure you use the **Update** method to save the changes before you move to another record. If you move to another record without updating, your changes are lost without warning.</span></span>

<span data-ttu-id="9c8d4-p102">在打开 **Recordset** 时，第一条记录将是当前记录，并且 **BOF** 属性为 **False**。如果 **Recordset** 不包含记录，则 **BOF** 属性为 **True**，并且不存在当前记录。</span><span class="sxs-lookup"><span data-stu-id="9c8d4-p102">When you open a **Recordset**, the first record is current and the **BOF** property is **False**. If the **Recordset** contains no records, the **BOF** property is **True**, and there is no current record.</span></span>

<span data-ttu-id="9c8d4-p103">如果第一条记录是当前记录，在使用 **MovePrevious** 时， **BOF** 属性将是 **True**，并且不会有当前记录。如果再次使用 **MovePrevious**，将发生错误，同时 **BOF** 保留为 **True**。</span><span class="sxs-lookup"><span data-stu-id="9c8d4-p103">If you use **MovePrevious** when the first record is current, the **BOF** property is **True**, and there is no current record. If you use **MovePrevious** again, an error occurs, and **BOF** remains **True**.</span></span>

<span data-ttu-id="9c8d4-116">如果 recordset 引用表类型的**recordset** (仅适用于 Microsoft Access 工作区), 则移动将遵循当前索引。</span><span class="sxs-lookup"><span data-stu-id="9c8d4-116">If recordset refers to a table-type **Recordset** (Microsoft Access workspaces only), movement follows the current index.</span></span> <span data-ttu-id="9c8d4-117">可以使用 **Index** 属性设置当前索引。</span><span class="sxs-lookup"><span data-stu-id="9c8d4-117">You can set the current index by using the **Index** property.</span></span> <span data-ttu-id="9c8d4-118">如果不设置当前索引，则返回记录的顺序将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="9c8d4-118">If you don't set the current index, the order of returned records is undefined.</span></span>

<span data-ttu-id="9c8d4-119">您不能在仅向前类型的**Recordset**对象上使用**MoveFirst**、 **MoveLast**和**MovePrevious**方法。</span><span class="sxs-lookup"><span data-stu-id="9c8d4-119">You can't use the **MoveFirst**, **MoveLast**, and **MovePrevious** methods on a forward–only–type **Recordset** object.</span></span>

<span data-ttu-id="9c8d4-120">若要将 **Recordset** 对象中的当前记录的位置向前或向后移动指定的记录数，请使用 **Move** 方法。</span><span class="sxs-lookup"><span data-stu-id="9c8d4-120">To move the position of the current record in a **Recordset** object a specific number of records forward or backward, use the **Move** method.</span></span>

