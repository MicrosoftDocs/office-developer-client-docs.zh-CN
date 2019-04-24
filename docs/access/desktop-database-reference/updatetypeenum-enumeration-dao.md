---
title: UpdateTypeEnum 枚举 (DAO)
TOCTitle: UpdateTypeEnum Enumeration
ms:assetid: 7ac38bae-27fc-f3d0-5b75-569bce547954
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196186(v=office.15)
ms:contentKeyID: 48545800
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d1e4ecbc216ab4a00dabd85f623bc134772dfd4c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306186"
---
# <a name="updatetypeenum-enumeration-dao"></a><span data-ttu-id="94319-102">UpdateTypeEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="94319-102">UpdateTypeEnum enumeration (DAO)</span></span>


<span data-ttu-id="94319-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="94319-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="94319-104">与 **Update** 方法一起用来指定要写入到磁盘中的更新。</span><span class="sxs-lookup"><span data-stu-id="94319-104">Used with the **Update** method to specify which updates to write to disk.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="94319-105">名称</span><span class="sxs-lookup"><span data-stu-id="94319-105">Name</span></span></p></th>
<th><p><span data-ttu-id="94319-106">值</span><span class="sxs-lookup"><span data-stu-id="94319-106">Value</span></span></p></th>
<th><p><span data-ttu-id="94319-107">说明</span><span class="sxs-lookup"><span data-stu-id="94319-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94319-108">dbUpdateBatch</span><span class="sxs-lookup"><span data-stu-id="94319-108">dbUpdateBatch</span></span></p></td>
<td><p><span data-ttu-id="94319-109">4</span><span class="sxs-lookup"><span data-stu-id="94319-109">4</span></span></p></td>
<td><p><span data-ttu-id="94319-110">将更新缓存中的所有挂起的更改写入磁盘中。</span><span class="sxs-lookup"><span data-stu-id="94319-110">All pending changes in the update cache are written to disk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94319-111">dbUpdateCurrentRecord</span><span class="sxs-lookup"><span data-stu-id="94319-111">dbUpdateCurrentRecord</span></span></p></td>
<td><p><span data-ttu-id="94319-112">双面</span><span class="sxs-lookup"><span data-stu-id="94319-112">2</span></span></p></td>
<td><p><span data-ttu-id="94319-113">仅将当前记录的挂起更改写入磁盘中。</span><span class="sxs-lookup"><span data-stu-id="94319-113">Only the current record's pending changes are written to disk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94319-114">dbUpdateRegular</span><span class="sxs-lookup"><span data-stu-id="94319-114">dbUpdateRegular</span></span></p></td>
<td><p><span data-ttu-id="94319-115">1</span><span class="sxs-lookup"><span data-stu-id="94319-115">1</span></span></p></td>
<td><p><span data-ttu-id="94319-116">（默认值）挂起的更改不进行缓存，直接写入磁盘中。</span><span class="sxs-lookup"><span data-stu-id="94319-116">(Default) Pending changes are not cached and are written to disk immediately.</span></span></p></td>
</tr>
</tbody>
</table>

