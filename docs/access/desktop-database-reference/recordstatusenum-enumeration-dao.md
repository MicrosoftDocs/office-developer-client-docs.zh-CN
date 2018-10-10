---
title: RecordStatusEnum Enumeration (DAO)
TOCTitle: RecordStatusEnum Enumeration
ms:assetid: bf4492f2-8d8f-f10f-7a3c-d6296d2ce96b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822784(v=office.15)
ms:contentKeyID: 48547483
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 78f86e8c80a6bbc09499e9512e2daee87fc67998
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466558"
---
# <a name="recordstatusenum-enumeration-dao"></a><span data-ttu-id="32939-102">RecordStatusEnum Enumeration (DAO)</span><span class="sxs-lookup"><span data-stu-id="32939-102">RecordStatusEnum Enumeration (DAO)</span></span>


<span data-ttu-id="32939-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="32939-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="32939-104">与 **RecordStatus** 属性一起用来指示当前记录的更新状态（如果当前记录属于批更新的一部分）。</span><span class="sxs-lookup"><span data-stu-id="32939-104">Used with the **RecordStatus** property to indicate the update status of the current record if it is part of a batch update.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="32939-105">名称</span><span class="sxs-lookup"><span data-stu-id="32939-105">Name</span></span></p></th>
<th><p><span data-ttu-id="32939-106">值</span><span class="sxs-lookup"><span data-stu-id="32939-106">Value</span></span></p></th>
<th><p><span data-ttu-id="32939-107">说明</span><span class="sxs-lookup"><span data-stu-id="32939-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32939-108">dbRecordDBDeleted</span><span class="sxs-lookup"><span data-stu-id="32939-108">dbRecordDBDeleted</span></span></p></td>
<td><p><span data-ttu-id="32939-109">4</span><span class="sxs-lookup"><span data-stu-id="32939-109">4</span></span></p></td>
<td><p><span data-ttu-id="32939-110">已在本地和数据库中删除该记录。</span><span class="sxs-lookup"><span data-stu-id="32939-110">The record has been deleted locally and in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32939-111">dbRecordDeleted</span><span class="sxs-lookup"><span data-stu-id="32939-111">dbRecordDeleted</span></span></p></td>
<td><p><span data-ttu-id="32939-112">3</span><span class="sxs-lookup"><span data-stu-id="32939-112">3</span></span></p></td>
<td><p><span data-ttu-id="32939-113">已删除该记录，但是尚未在数据库中删除它。</span><span class="sxs-lookup"><span data-stu-id="32939-113">The record has been deleted, but not yet deleted in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32939-114">dbRecordModified</span><span class="sxs-lookup"><span data-stu-id="32939-114">dbRecordModified</span></span></p></td>
<td><p><span data-ttu-id="32939-115">1</span><span class="sxs-lookup"><span data-stu-id="32939-115">1</span></span></p></td>
<td><p><span data-ttu-id="32939-116">已修改该记录，但是尚未在数据库中更新它。</span><span class="sxs-lookup"><span data-stu-id="32939-116">The record has been modified and not updated in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32939-117">dbRecordNew</span><span class="sxs-lookup"><span data-stu-id="32939-117">dbRecordNew</span></span></p></td>
<td><p><span data-ttu-id="32939-118">2</span><span class="sxs-lookup"><span data-stu-id="32939-118">2</span></span></p></td>
<td><p><span data-ttu-id="32939-119">已经用 <strong>AddNew</strong> 方法插入了该记录，但是尚未将其插入到数据库中。</span><span class="sxs-lookup"><span data-stu-id="32939-119">The record has been inserted with the <strong>AddNew</strong> method, but not yet inserted into the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32939-120">dbRecordUnmodified</span><span class="sxs-lookup"><span data-stu-id="32939-120">dbRecordUnmodified</span></span></p></td>
<td><p><span data-ttu-id="32939-121">0</span><span class="sxs-lookup"><span data-stu-id="32939-121">0</span></span></p></td>
<td><p><span data-ttu-id="32939-122">（默认值）该记录尚未修改，或者已更新成功。</span><span class="sxs-lookup"><span data-stu-id="32939-122">(Default) The record has not been modified or has been updated successfully.</span></span></p></td>
</tr>
</tbody>
</table>

