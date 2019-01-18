---
title: Recordset.MoveNext 方法 (DAO)
TOCTitle: MoveNext Method
ms:assetid: 0a1315cf-92f8-b8ef-1542-081e8c2d5be0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845090(v=office.15)
ms:contentKeyID: 48543142
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 1b0ebe0edcfcbfac5942fc83a3ff1f99eddfea7f
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711341"
---
# <a name="recordsetmovenext-method-dao"></a><span data-ttu-id="09341-102">Recordset.MoveNext 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="09341-102">Recordset.MoveNext method (DAO)</span></span>


<span data-ttu-id="09341-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="09341-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="09341-104">移到指定的 **Recordset** 对象中的下一条记录，并使该记录成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="09341-104">Moves to the next record in a specified **Recordset** object and make that record the current record.</span></span>

## <a name="syntax"></a><span data-ttu-id="09341-105">语法</span><span class="sxs-lookup"><span data-stu-id="09341-105">Syntax</span></span>

<span data-ttu-id="09341-106">*表达式*。MoveNext</span><span class="sxs-lookup"><span data-stu-id="09341-106">*expression* .MoveNext</span></span>

<span data-ttu-id="09341-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="09341-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="09341-108">注解</span><span class="sxs-lookup"><span data-stu-id="09341-108">Remarks</span></span>

<span data-ttu-id="09341-109">使用 **Move** 方法可以在记录间移动，而不需要应用条件。</span><span class="sxs-lookup"><span data-stu-id="09341-109">Use the **Move** methods to move from record to record without applying a condition.</span></span>

<span data-ttu-id="09341-p101">如果要编辑当前记录，请确保使用 **Update** 方法保存更改，然后移到另一条记录。如果在不更新的情况下移到另一条记录，则更改将会丢失，且不发出警告。</span><span class="sxs-lookup"><span data-stu-id="09341-p101">If you edit the current record, be sure you use the **Update** method to save the changes before you move to another record. If you move to another record without updating, your changes are lost without warning.</span></span>

<span data-ttu-id="09341-p102">在打开 **Recordset** 时，第一条记录将是当前记录，并且 **BOF** 属性为 **False**。如果 **Recordset** 不包含记录，则 **BOF** 属性为 **True**，并且不存在当前记录。</span><span class="sxs-lookup"><span data-stu-id="09341-p102">When you open a **Recordset**, the first record is current and the **BOF** property is **False**. If the **Recordset** contains no records, the **BOF** property is **True**, and there is no current record.</span></span>

<span data-ttu-id="09341-p103">如果最后一条记录是当前记录，在使用 **MoveNext** 时， **EOF** 属性将是 **True**，并且不会有当前记录。如果再次使用 **MoveNext**，将发生错误，同时 **EOF** 保留为 **True**。</span><span class="sxs-lookup"><span data-stu-id="09341-p103">If you use **MoveNext** when the last record is current, the **EOF** property is **True**, and there is no current record. If you use **MoveNext** again, an error occurs, and **EOF** remains **True**.</span></span>

<span data-ttu-id="09341-116">如果 recordset 引用表类型**Recordset** （仅限 Microsoft Access 工作区），则移动遵循当前索引。</span><span class="sxs-lookup"><span data-stu-id="09341-116">If recordset refers to a table-type **Recordset** (Microsoft Access workspaces only), movement follows the current index.</span></span> <span data-ttu-id="09341-117">可以使用 **Index** 属性设置当前索引。</span><span class="sxs-lookup"><span data-stu-id="09341-117">You can set the current index by using the **Index** property.</span></span> <span data-ttu-id="09341-118">如果不设置当前索引，则返回记录的顺序将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="09341-118">If you don't set the current index, the order of returned records is undefined.</span></span>

<span data-ttu-id="09341-119">不能对仅向前类型**Recordset**对象使用**MoveFirst**、 **MoveLast**和**MovePrevious**方法。</span><span class="sxs-lookup"><span data-stu-id="09341-119">You can't use the **MoveFirst**, **MoveLast**, and **MovePrevious** methods on a forward–only–type **Recordset** object.</span></span>

<span data-ttu-id="09341-120">若要将 **Recordset** 对象中的当前记录的位置向前或向后移动指定的记录数，请使用 **Move** 方法。</span><span class="sxs-lookup"><span data-stu-id="09341-120">To move the position of the current record in a **Recordset** object a specific number of records forward or backward, use the **Move** method.</span></span>

