---
title: 跳到记录
TOCTitle: Jumping to a record
ms:assetid: 27177bbe-066c-aeb0-6dfd-45d8c2a87487
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249033(v=office.15)
ms:contentKeyID: 48543829
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 08d8a3d7b3d6012867a91aa306f45872bfebb2e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290784"
---
# <a name="jumping-to-a-record"></a><span data-ttu-id="6de84-102">跳到记录</span><span class="sxs-lookup"><span data-stu-id="6de84-102">Jumping to a record</span></span>


<span data-ttu-id="6de84-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6de84-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6de84-104">使用 [Move](move-method-ado.md) 方法可以在 **Recordset** 中前后移动指定数量的记录，语法如下：</span><span class="sxs-lookup"><span data-stu-id="6de84-104">The [Move](move-method-ado.md) method allows you to move forward or backward in the **Recordset** a specified number of records by using the following syntax:</span></span>

```vb 
 
oRs.Move NumRecords, Start
```

<span data-ttu-id="6de84-105">所有的 **Recordset** 对象都支持 **Move** 方法。</span><span class="sxs-lookup"><span data-stu-id="6de84-105">The **Move** method is supported on all **Recordset** objects.</span></span>

<span data-ttu-id="6de84-p101">如果 *NumRecords* 参数大于零，则当前记录的位置会（朝着 **Recordset** 的末尾）向前移动；如果 *NumRecords* 小于零，则当前记录的位置会（朝着 **Recordset** 的开头）向后移动。</span><span class="sxs-lookup"><span data-stu-id="6de84-p101">If the *NumRecords* argument is greater than zero, the current record position moves forward (toward the end of the **Recordset**). If *NumRecords* is less than zero, the current record position moves backward (toward the beginning of the **Recordset**).</span></span>

<span data-ttu-id="6de84-p102">如果 **Move** 调用会将当前记录的位置移到第一个记录前面的某个点，则 ADO 会将当前的记录设置为 **Recordset** 中第一个记录前面的位置（**BOF** 为 **True**）。当 **BOF** 属性已经为 **True** 时，如果尝试向后移动，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="6de84-p102">If the **Move** call would move the current record position to a point before the first record, ADO sets the current record to the position before the first record in the **Recordset** (**BOF** is **True**). An attempt to move backward when the **BOF** property is already **True** generates an error.</span></span>

<span data-ttu-id="6de84-p103">如果 **Move** 调用会将当前记录的位置移到最后一个记录后面的某个点，则 ADO 会将当前的记录设置为 **Recordset** 中最后一个记录后面的位置（**EOF** 为 **True**）。当 **EOF** 属性已经为 **True** 时，如果尝试向前移动，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="6de84-p103">If the **Move** call would move the current record position to a point after the last record, ADO sets the current record to the position after the last record in the **Recordset** (**EOF** is **True**). An attempt to move forward when the **EOF** property is already **True** generates an error.</span></span>

<span data-ttu-id="6de84-112">从空 **Recordset** 对象调用 **Move** 方法将生成错误。</span><span class="sxs-lookup"><span data-stu-id="6de84-112">Calling the **Move** method from an empty **Recordset** object generates an error.</span></span>

<span data-ttu-id="6de84-p104">如果在 *Start* 参数中传递一个书签，则将相对于具有该书签的记录进行移动，假定 **Recordset** 对象支持书签。可使用 [Bookmark](bookmark-property-ado.md) 属性来获取书签。如果未指定书签，则将相对于当前的记录进行移动。</span><span class="sxs-lookup"><span data-stu-id="6de84-p104">If you pass a bookmark in the *Start* argument, the move is relative to the record with this bookmark, assuming the **Recordset** object supports bookmarks. A bookmark is obtained by using the [Bookmark](bookmark-property-ado.md) property. If not specified, the move is relative to the current record.</span></span>

<span data-ttu-id="6de84-p105">如果要使用 **CacheSize** 属性在本地缓存提供程序的记录，而且所传递 *NumRecords* 参数会将当前记录的位置移到缓存记录的当前组外部，则会强制 ADO 检索一组新记录（从目标记录开始）。**CacheSize** 属性确定新检索组的大小，目标记录是检索到的第一个记录。</span><span class="sxs-lookup"><span data-stu-id="6de84-p105">If you are using the **CacheSize** property to locally cache records from the provider, passing a *NumRecords* argument that moves the current record position outside the current group of cached records forces ADO to retrieve a new group of records, starting from the destination record. The **CacheSize** property determines the size of the newly retrieved group, and the destination record is the first record retrieved.</span></span>

