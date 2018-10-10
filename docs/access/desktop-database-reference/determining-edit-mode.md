---
title: 确定编辑模式
TOCTitle: Determining Edit Mode
ms:assetid: 45e21fa7-94e8-3449-e062-09cbcf15cba8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249215(v=office.15)
ms:contentKeyID: 48544563
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 53167d7438ecce673fed64f3c7b8d53fbbfbaa5d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468834"
---
# <a name="determining-edit-mode"></a><span data-ttu-id="385ad-102">确定编辑模式</span><span class="sxs-lookup"><span data-stu-id="385ad-102">Determining Edit Mode</span></span>


<span data-ttu-id="385ad-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="385ad-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="385ad-p101">ADO 维护一个与当前记录关联的编辑缓冲区。 **EditMode** 属性指示此缓冲区是否已发生更改，或者是否已创建新记录。使用 **EditMode** 可以确定当前记录的编辑状态。如果编辑过程已经中断则可以测试是否有挂起更改，并确定是否需要使用 **Update** 或 **CancelUpdate** 方法。</span><span class="sxs-lookup"><span data-stu-id="385ad-p101">ADO maintains an editing buffer associated with the current record. The **EditMode** property indicates whether changes have been made to this buffer or whether a new record has been created. Use **EditMode** to determine the editing status of the current record. You can test for pending changes if an editing process has been interrupted and determine whether you need to use the **Update** or **CancelUpdate** method.</span></span>

<span data-ttu-id="385ad-108">**EditMode** 返回 **EditModeEnum** 常量之一，下表列出了这些常量。</span><span class="sxs-lookup"><span data-stu-id="385ad-108">**EditMode** returns one of the **EditModeEnum** constants, which are listed in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="385ad-109">常量</span><span class="sxs-lookup"><span data-stu-id="385ad-109">Constant</span></span></p></th>
<th><p><span data-ttu-id="385ad-110">说明</span><span class="sxs-lookup"><span data-stu-id="385ad-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="385ad-111"><strong>为 adEditNone</strong></span><span class="sxs-lookup"><span data-stu-id="385ad-111"><strong>adEditNone</strong></span></span></p></td>
<td><p><span data-ttu-id="385ad-112">指示没有正在进行的编辑操作。</span><span class="sxs-lookup"><span data-stu-id="385ad-112">Indicates that no editing operation is in progress.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="385ad-113"><strong>adEditInProgress</strong></span><span class="sxs-lookup"><span data-stu-id="385ad-113"><strong>adEditInProgress</strong></span></span></p></td>
<td><p><span data-ttu-id="385ad-114">指示当前记录中的数据已经修改但未保存。</span><span class="sxs-lookup"><span data-stu-id="385ad-114">Indicates that data in the current record has been modified but not saved.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="385ad-115"><strong>adEditAdd</strong></span><span class="sxs-lookup"><span data-stu-id="385ad-115"><strong>adEditAdd</strong></span></span></p></td>
<td><p><span data-ttu-id="385ad-116">指示已调用 <strong>AddNew</strong> 方法，并且复制缓冲区中的当前记录是尚未保存到数据库的新记录。</span><span class="sxs-lookup"><span data-stu-id="385ad-116">Indicates that the <strong>AddNew</strong> method has been called, and the current record in the copy buffer is a new record that has not been saved to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="385ad-117"><strong>adEditDelete</strong></span><span class="sxs-lookup"><span data-stu-id="385ad-117"><strong>adEditDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="385ad-118">指示已删除当前记录。</span><span class="sxs-lookup"><span data-stu-id="385ad-118">Indicates that the current record has been deleted.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="385ad-p102">只有当存在当前记录时， **EditMode** 才能返回有效值。如果 **BOF** 或 **EOF** 为 **True** 或当前记录已删除， **EditMode** 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="385ad-p102">**EditMode** can return a valid value only if there is a current record. **EditMode** will return an error if **BOF** or **EOF** is **True** or if the current record has been deleted.</span></span>

