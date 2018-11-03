---
title: MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (ADO)
TOCTitle: MoveFirst, MoveLast, MoveNext, and MovePrevious methods (ADO)
ms:assetid: d04ce41c-77c9-df42-115a-65c50a38518a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250039(v=office.15)
ms:contentKeyID: 48547836
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2bbc9998102356622b1a31a8411fd9e502436a8f
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25947063"
---
# <a name="movefirst-movelast-movenext-and-moveprevious-methods-ado"></a><span data-ttu-id="6b917-102">MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="6b917-102">MoveFirst, MoveLast, MoveNext, and MovePrevious methods (ADO)</span></span>


<span data-ttu-id="6b917-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6b917-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6b917-104">用于移动到指定的 [Recordset](recordset-object-ado.md) 对象中的第一个、最后一个、下一个或上一个记录，并使该记录成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="6b917-104">Moves to the first, last, next, or previous record in a specified [Recordset](recordset-object-ado.md) object and makes that record the current record.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b917-105">语法</span><span class="sxs-lookup"><span data-stu-id="6b917-105">Syntax</span></span>

<span data-ttu-id="6b917-106">*记录集*。{</span><span class="sxs-lookup"><span data-stu-id="6b917-106">*recordset*.{</span></span> <span data-ttu-id="6b917-107">MoveFirst |MoveLast |MoveNext |MovePrevious}</span><span class="sxs-lookup"><span data-stu-id="6b917-107">MoveFirst | MoveLast | MoveNext | MovePrevious}</span></span>

## <a name="remarks"></a><span data-ttu-id="6b917-108">备注</span><span class="sxs-lookup"><span data-stu-id="6b917-108">Remarks</span></span>

<span data-ttu-id="6b917-109">使用 **MoveFirst** 方法可以将当前记录位置移动到 **Recordset** 中的第一个记录。</span><span class="sxs-lookup"><span data-stu-id="6b917-109">Use the **MoveFirst** method to move the current record position to the first record in the **Recordset**.</span></span>

<span data-ttu-id="6b917-p102">使用 **MoveLast** 方法可以将当前记录位置移动到 **Recordset** 中的最后一个记录。 **Recordset** 对象必须支持书签或向后游标移动；否则，该方法调用将生成错误。</span><span class="sxs-lookup"><span data-stu-id="6b917-p102">Use the **MoveLast** method to move the current record position to the last record in the **Recordset**. The **Recordset** object must support bookmarks or backward cursor movement; otherwise, the method call will generate an error.</span></span>

<span data-ttu-id="6b917-112">当 **Recordset** 为空（ **BOF** 和 **EOF** 均为 True）时，调用 **MoveFirst** 或 **MoveLast** 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="6b917-112">A call to either **MoveFirst** or **MoveLast** when the **Recordset** is empty (both **BOF** and **EOF** are True) generates an error.</span></span>

<span data-ttu-id="6b917-p103">使用 **MoveNext** 方法可以将当前记录位置向前（朝着 **Recordset** 的末部）移动一个记录。如果最后一个记录就是当前记录，则调用 **MoveNext** 方法时，ADO 将把当前记录设置为 **Recordset** 中最后一个记录之后的位置（[EOF](bof-eof-properties-ado.md) 为 **True**）。当 **EOF** 属性已经为 **True** 时尝试向前移动，将生成错误。</span><span class="sxs-lookup"><span data-stu-id="6b917-p103">Use the **MoveNext** method to move the current record position one record forward (toward the bottom of the **Recordset**). If the last record is the current record and you call the **MoveNext** method, ADO sets the current record to the position after the last record in the **Recordset** ([EOF](bof-eof-properties-ado.md) is **True**). An attempt to move forward when the **EOF** property is already **True** generates an error.</span></span>

<span data-ttu-id="6b917-116">如果已经对 **Recordset** 进行了筛选或排序，且当前记录的数据已更改，则记录的位置也可能会更改。</span><span class="sxs-lookup"><span data-stu-id="6b917-116">In cases where the **Recordset** has been filtered or sorted and the current record's data is changed, the position may also change.</span></span> <span data-ttu-id="6b917-117">在这种情况下， **MoveNext** 方法仍正常工作，但您应注意，记录的位置是从新位置（而不是旧位置）向前移动一个记录。</span><span class="sxs-lookup"><span data-stu-id="6b917-117">In such cases the **MoveNext** method works normally, but you should be aware that the position is moved one record forward from the new position, not the old position.</span></span> <span data-ttu-id="6b917-118">例如，更改成为当前记录中的数据，以便记录移动到已排序的**Recordset**的末尾意味着，调用**MoveNext**导致 ADO 设置后**中的最后一个记录成为当前记录位置Recordset** (**EOF** = **True**)。</span><span class="sxs-lookup"><span data-stu-id="6b917-118">For example, changing the data in the current record, such that the record is moved to the end of the sorted **Recordset,** would mean that calling **MoveNext** results in ADO setting the current record to the position after the last record in the **Recordset** (**EOF** = **True**).</span></span>

<span data-ttu-id="6b917-p105">使用 **MovePrevious** 方法可以将当前记录位置向后（朝着 **Recordset** 的顶部）移动一个记录。**Recordset** 对象必须支持书签或向后的游标移动；否则，该方法将生成错误。如果第一个记录就是当前记录，则调用 **MovePrevious** 方法时，ADO 将把当前记录设置为 **Recordset** 中第一个记录之前的位置（[BOF](bof-eof-properties-ado.md) 为 **True**）。当 **BOF** 属性已经为 **True** 时，尝试向后移动将生成错误。如果 **Recordset** 对象不支持书签或向后的游标移动，**MovePrevious** 方法将生成错误。</span><span class="sxs-lookup"><span data-stu-id="6b917-p105">Use the **MovePrevious** method to move the current record position one record backward (toward the top of the **Recordset**). The **Recordset** object must support bookmarks or backward cursor movement; otherwise, the method call will generate an error. If the first record is the current record and you call the **MovePrevious** method, ADO sets the current record to the position before the first record in the **Recordset** ([BOF](bof-eof-properties-ado.md) is **True**). An attempt to move backward when the **BOF** property is already **True** generates an error. If the **Recordset** object does not support either bookmarks or backward cursor movement, the **MovePrevious** method will generate an error.</span></span>

<span data-ttu-id="6b917-p106">如果 **Recordset** 是仅向前的，并且您想要同时支持向前和向后滚动，则可以使用 [CacheSize](cachesize-property-ado.md) 属性来创建记录缓存，后者通过 [Move](move-method-ado.md) 方法支持向后游标移动。由于缓存的记录被加载到内存中，因此，您应该避免缓存超过所需数目的记录。可以在仅向前的 **Recordset** 对象中调用 **MoveFirst** 方法；这样做可能会导致提供程序重新执行生成 **Recordset** 对象的命令。</span><span class="sxs-lookup"><span data-stu-id="6b917-p106">If the **Recordset** is forward only and you want to support both forward and backward scrolling, you can use the [CacheSize](cachesize-property-ado.md) property to create a record cache that will support backward cursor movement through the [Move](move-method-ado.md) method. Because cached records are loaded into memory, you should avoid caching more records than is necessary. You can call the **MoveFirst** method in a forward-only **Recordset** object; doing so may cause the provider to re-execute the command that generated the **Recordset** object.</span></span>

