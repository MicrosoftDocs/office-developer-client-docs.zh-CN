---
title: RecordStatusEnum Enumeration (DAO)
TOCTitle: RecordStatusEnum Enumeration
ms:assetid: bf4492f2-8d8f-f10f-7a3c-d6296d2ce96b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822784(v=office.15)
ms:contentKeyID: 48547483
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c2d96c359a913660c146f4850a1846554e3b6856
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25875117"
---
# <a name="recordstatusenum-enumeration-dao"></a><span data-ttu-id="b2c18-102">RecordStatusEnum Enumeration (DAO)</span><span class="sxs-lookup"><span data-stu-id="b2c18-102">RecordStatusEnum Enumeration (DAO)</span></span>


<span data-ttu-id="b2c18-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b2c18-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b2c18-104">与 **RecordStatus** 属性一起用来指示当前记录的更新状态（如果当前记录属于批更新的一部分）。</span><span class="sxs-lookup"><span data-stu-id="b2c18-104">Used with the **RecordStatus** property to indicate the update status of the current record if it is part of a batch update.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b2c18-105">名称</span><span class="sxs-lookup"><span data-stu-id="b2c18-105">Name</span></span></p></th>
<th><p><span data-ttu-id="b2c18-106">值</span><span class="sxs-lookup"><span data-stu-id="b2c18-106">Value</span></span></p></th>
<th><p><span data-ttu-id="b2c18-107">说明</span><span class="sxs-lookup"><span data-stu-id="b2c18-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2c18-108">dbRecordDBDeleted</span><span class="sxs-lookup"><span data-stu-id="b2c18-108">dbRecordDBDeleted</span></span></p></td>
<td><p><span data-ttu-id="b2c18-109">4</span><span class="sxs-lookup"><span data-stu-id="b2c18-109">4</span></span></p></td>
<td><p><span data-ttu-id="b2c18-110">已在本地和数据库中删除该记录。</span><span class="sxs-lookup"><span data-stu-id="b2c18-110">The record has been deleted locally and in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2c18-111">dbRecordDeleted</span><span class="sxs-lookup"><span data-stu-id="b2c18-111">dbRecordDeleted</span></span></p></td>
<td><p><span data-ttu-id="b2c18-112">3</span><span class="sxs-lookup"><span data-stu-id="b2c18-112">3</span></span></p></td>
<td><p><span data-ttu-id="b2c18-113">已删除该记录，但是尚未在数据库中删除它。</span><span class="sxs-lookup"><span data-stu-id="b2c18-113">The record has been deleted, but not yet deleted in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2c18-114">dbRecordModified</span><span class="sxs-lookup"><span data-stu-id="b2c18-114">dbRecordModified</span></span></p></td>
<td><p><span data-ttu-id="b2c18-115">1</span><span class="sxs-lookup"><span data-stu-id="b2c18-115">1</span></span></p></td>
<td><p><span data-ttu-id="b2c18-116">已修改该记录，但是尚未在数据库中更新它。</span><span class="sxs-lookup"><span data-stu-id="b2c18-116">The record has been modified and not updated in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2c18-117">dbRecordNew</span><span class="sxs-lookup"><span data-stu-id="b2c18-117">dbRecordNew</span></span></p></td>
<td><p><span data-ttu-id="b2c18-118">2</span><span class="sxs-lookup"><span data-stu-id="b2c18-118">2</span></span></p></td>
<td><p><span data-ttu-id="b2c18-119">已经用 <strong>AddNew</strong> 方法插入了该记录，但是尚未将其插入到数据库中。</span><span class="sxs-lookup"><span data-stu-id="b2c18-119">The record has been inserted with the <strong>AddNew</strong> method, but not yet inserted into the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2c18-120">dbRecordUnmodified</span><span class="sxs-lookup"><span data-stu-id="b2c18-120">dbRecordUnmodified</span></span></p></td>
<td><p><span data-ttu-id="b2c18-121">0</span><span class="sxs-lookup"><span data-stu-id="b2c18-121">0</span></span></p></td>
<td><p><span data-ttu-id="b2c18-122">（默认值）该记录尚未修改，或者已更新成功。</span><span class="sxs-lookup"><span data-stu-id="b2c18-122">(Default) The record has not been modified or has been updated successfully.</span></span></p></td>
</tr>
</tbody>
</table>

