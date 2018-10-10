---
title: 在记录集中进行移动的其他方法
TOCTitle: More Ways to Move in a Recordset
ms:assetid: ae49b20e-0050-c44b-67e9-7e39de5098c4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249822(v=office.15)
ms:contentKeyID: 48547067
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3a9a98471a73f5e3471d55ba6e81689dd39a5934
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466098"
---
# <a name="more-ways-to-move-in-a-recordset"></a><span data-ttu-id="8b611-102">在记录集中进行移动的其他方法</span><span class="sxs-lookup"><span data-stu-id="8b611-102">More Ways to Move in a Recordset</span></span>

<span data-ttu-id="8b611-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8b611-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8b611-p101">可以使用以下四种方法在 **Recordset** 中移动和滚动： [MoveFirst、MoveLast、MoveNext 和 MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)。（其中的某些方法对于仅向前型游标不可用。）</span><span class="sxs-lookup"><span data-stu-id="8b611-p101">The following four methods are used to move around, or scroll, in the **Recordset**: [MoveFirst, MoveLast, MoveNext, and MovePrevious](movefirst-movelast-movenext-and-moveprevious-methods-ado.md). (Some of these methods are unavailable on forward-only cursors.)</span></span>

<span data-ttu-id="8b611-p102">**MoveFirst** 将当前记录的位置更改到 **Recordset** 中的第一个记录。 **MoveLast** 将当前记录的位置更改到 **Recordset** 中的最后一个记录。若要使用 **MoveFirst** 或 **MoveLast** ， **Recordset** 对象必须支持书签或向后游标运动；否则，在调用该方法时将生成错误。</span><span class="sxs-lookup"><span data-stu-id="8b611-p102">**MoveFirst** changes the current record position to the first record in the **Recordset**. **MoveLast** changes the current record position to the last record in the **Recordset**. To use **MoveFirst** or **MoveLast**, the **Recordset** object must support bookmarks or backward cursor movement; otherwise, the method call will generate an error.</span></span>

<span data-ttu-id="8b611-p103">**MoveNext** 将当前记录向前移动一个位置。如果在调用 **MoveNext** 时位于最后一个记录， **EOF** 将设置为 **True** 。 **MovePrevious** 将当前记录向后移动一个位置。如果在调用 **MovePrevious** 时位于第一个记录， **BOF** 将设置为 **True** 。在使用这些方法时最好检查 **EOF** 和 **BOF** 属性，如果您将游标移出了 **Recordset** 两端的范围，请将游标移回到有效的当前记录位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b611-p103">**MoveNext** moves the current record position one place forward. If you are on the last record when you call **MoveNext**, **EOF** will be set to **True**. **MovePrevious** moves the current record position one place backward. If you are on the first record when you call **MovePrevious**, **BOF** will be set to **True**. It is wise to check the **EOF** and **BOF** properties when using these methods and to move the cursor back to a valid current record position if you move off either end of the **Recordset**, as shown here:</span></span>

```vb
. . . 
oRs.MoveNext 
If oRs.EOF Then oRs.MoveLast 
. . . 
```

<span data-ttu-id="8b611-114">或者，对于 **MovePrevious** 方法：</span><span class="sxs-lookup"><span data-stu-id="8b611-114">Or, in the case of the **MovePrevious** method:</span></span>

```vb
. . . 
oRs.MovePrevious 
If oRs.BOF Then oRs.MoveFirst 
. . . 
```

<span data-ttu-id="8b611-115">如果已经对 **Recordset** 进行了筛选或排序，如果当前记录中的数据发生了更改，则记录的位置也可能会改变。</span><span class="sxs-lookup"><span data-stu-id="8b611-115">In cases where the **Recordset** has been filtered or sorted and the current record's data is changed, the position may also change.</span></span> <span data-ttu-id="8b611-116">在这种情况下， **MoveNext** 方法通常会正常工作，但是，请注意，记录的位置会从新位置（而非旧位置）向前移动一个记录。</span><span class="sxs-lookup"><span data-stu-id="8b611-116">In such cases the **MoveNext** method works normally, but be aware that the position is moved one record forward from the new position, not the old position.</span></span> <span data-ttu-id="8b611-117">例如，更改成为当前记录中的数据，以便记录会移至排序**Recordset**的末尾意味着，调用**MoveNext**导致 ADO 设置后**中的最后一个记录成为当前记录位置Recordset** (**EOF** = **True**)。</span><span class="sxs-lookup"><span data-stu-id="8b611-117">For example, changing the data in the current record, such that the record is moved to the end of the sorted **Recordset**, would mean that calling **MoveNext** results in ADO setting the current record to the position after the last record in the **Recordset** (**EOF** = **True**).</span></span>

<span data-ttu-id="8b611-p105">**Recordset** 对象的各种 Move 方法的行为在某种程度上取决于 **Recordset** 中的数据。添加到 **Recordset** 中的新记录最初按照特定的顺序添加，该顺序由数据源定义，并且可能隐式或显式依赖于新记录中的数据。例如，如果排序或联接是在用来填充 **Recordset** 的查询内完成的，则新记录将插入到 **Recordset** 中的相应位置。如果在创建 **Recordset** 时未显式指定排序，则在实现数据源中的更改时可能会在无意中改变返回行的排序。另外， **Recordset** 的排序、筛选和编辑功能可能会影响排序，还有可能会影响记录集内的哪些行将可见。</span><span class="sxs-lookup"><span data-stu-id="8b611-p105">The behavior of the various Move methods of the **Recordset** object depends, to some extent, on the data within the **Recordset**. New records added to the **Recordset** are initially added in a particular order, which is defined by the data source and may be dependent implicitly or explicitly on the data in the new record. For example, if a sort or a join is done within the query that populates the **Recordset**, the new record will be inserted in the appropriate place within the **Recordset**. If ordering is not explicitly specified when creating the **Recordset**, changes in the data source implementation may cause the ordering of the returned rows to change inadvertently. In addition, the sorting, filtering, and editing functions of the **Recordset** can affect the order and possibly which rows in the recordset will be visible.</span></span>

<span data-ttu-id="8b611-p106">因此， **MoveNext** 、 **MovePrevious** 、 **MoveFirst** 、 **MoveLast** 和 **Move** 对在同一个 **Recordset** 上执行的其他操作都非常敏感。ADO 将总是尝试保持当前的位置，直到您显式移动它，但是，如果中间更改将很难了解后续移动的影响。例如，如果调用 **MoveFirst** 以定位到已排序的 **Recordset** 的第一行，然后将排序次序从升序更改为降序，那么，您将仍位于同一行上，但是，现在它是 **Recordset** 中的最后一行。 **MoveFirst** 会将您带到另一行（新的第一行）。</span><span class="sxs-lookup"><span data-stu-id="8b611-p106">Therefore, **MoveNext**, **MovePrevious**, **MoveFirst**, **MoveLast**, and **Move** are all sensitive to other operations performed on the same **Recordset**. ADO will always try to maintain your current position until you explicitly move it, but sometimes intervening changes make it difficult to understand the effects of a subsequent move. For example, if you call **MoveFirst** to position on the first row of a sorted **Recordset** and you change the sort from ascending order to descending order, you are still on the same row — but now it is the last row in the **Recordset**. **MoveFirst** will take you to a different row (the new first row).</span></span>

<span data-ttu-id="8b611-p107">另一个示例是，如果您位于 **Recordset** 中间的某一行，调用 **Delete** ，然后调用 **MoveNext** ，那么，您将位于紧跟在所删除记录后面的记录。但是，调用 **MovePrevious** 会使所删除记录前面的记录成为当前记录，因为所删除的记录不再作为 **Recordset** 的活动成员。</span><span class="sxs-lookup"><span data-stu-id="8b611-p107">As another example, if you are positioned on a particular row in the middle of a **Recordset** and you call **Delete** and then call **MoveNext**, you are now on the record immediately following the deleted record. But calling **MovePrevious** makes the record preceding the one you deleted the current record, because the deleted record is no longer counted in the active membership of the **Recordset**.</span></span>

<span data-ttu-id="8b611-p108">如果当前记录中数据发生更改，对于相对当前记录进行移动的方法（**MovePrevious**、**MoveNext** 和 **Move**），很难在它们的全部提供程序之间定义一致的移动语义。例如，如果要处理经过排序和筛选的 **Recordset**，而且要更改当前记录中的数据，以便它将位于所有其他记录之前，但是已更改的数据也不再与筛选器匹配，那么，**MoveNext** 操作应当将您带到哪个位置将是不明确的。最安全的结论是，当对记录进行编辑、添加或删除时，如果数据会发生更改，那么，在 **Recordset** 中进行相对移动比进行绝对移动（如使用 **MoveFirst** 或 **MoveLast**）所面临的风险大。应当基于主键或 ID 进行排序和筛选，因为这种类型的值不会在排序和筛选过程中改变。</span><span class="sxs-lookup"><span data-stu-id="8b611-p108">It is particularly difficult to define consistent move semantics across all providers for methods that move relative to the current record — **MovePrevious**, **MoveNext**, and **Move** — in the face of changing data in the current record. For example, if you are working with a sorted, filtered **Recordset**, and you change the data in the current record so that it would precede all other records, but your changed data also no longer matches the filter, it is not clear where a **MoveNext** operation should take you. The safest conclusion is that relative movement within a **Recordset** is riskier than absolute movement (such as using **MoveFirst** or **MoveLast**) when the data is changing while records are being edited, added, or deleted. Sorting and filtering should be based on a primary key or ID, because this type of value should not change.</span></span>

