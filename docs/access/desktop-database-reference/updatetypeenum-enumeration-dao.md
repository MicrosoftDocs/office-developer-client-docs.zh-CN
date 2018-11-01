---
title: UpdateTypeEnum Enumeration (DAO)
TOCTitle: UpdateTypeEnum Enumeration
ms:assetid: 7ac38bae-27fc-f3d0-5b75-569bce547954
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196186(v=office.15)
ms:contentKeyID: 48545800
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: bd2ef7888f511b3f1577ec5fe60ef0ef7dda614a
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873444"
---
# <a name="updatetypeenum-enumeration-dao"></a><span data-ttu-id="1439e-102">UpdateTypeEnum Enumeration (DAO)</span><span class="sxs-lookup"><span data-stu-id="1439e-102">UpdateTypeEnum Enumeration (DAO)</span></span>


<span data-ttu-id="1439e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1439e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1439e-104">与 **Update** 方法一起用来指定要写入到磁盘中的更新。</span><span class="sxs-lookup"><span data-stu-id="1439e-104">Used with the **Update** method to specify which updates to write to disk.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1439e-105">名称</span><span class="sxs-lookup"><span data-stu-id="1439e-105">Name</span></span></p></th>
<th><p><span data-ttu-id="1439e-106">值</span><span class="sxs-lookup"><span data-stu-id="1439e-106">Value</span></span></p></th>
<th><p><span data-ttu-id="1439e-107">说明</span><span class="sxs-lookup"><span data-stu-id="1439e-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1439e-108">dbUpdateBatch</span><span class="sxs-lookup"><span data-stu-id="1439e-108">dbUpdateBatch</span></span></p></td>
<td><p><span data-ttu-id="1439e-109">4</span><span class="sxs-lookup"><span data-stu-id="1439e-109">4</span></span></p></td>
<td><p><span data-ttu-id="1439e-110">将更新缓存中的所有挂起的更改写入磁盘中。</span><span class="sxs-lookup"><span data-stu-id="1439e-110">All pending changes in the update cache are written to disk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1439e-111">dbUpdateCurrentRecord</span><span class="sxs-lookup"><span data-stu-id="1439e-111">dbUpdateCurrentRecord</span></span></p></td>
<td><p><span data-ttu-id="1439e-112">2</span><span class="sxs-lookup"><span data-stu-id="1439e-112">2</span></span></p></td>
<td><p><span data-ttu-id="1439e-113">仅将当前记录的挂起更改写入磁盘中。</span><span class="sxs-lookup"><span data-stu-id="1439e-113">Only the current record's pending changes are written to disk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1439e-114">dbUpdateRegular</span><span class="sxs-lookup"><span data-stu-id="1439e-114">dbUpdateRegular</span></span></p></td>
<td><p><span data-ttu-id="1439e-115">1</span><span class="sxs-lookup"><span data-stu-id="1439e-115">1</span></span></p></td>
<td><p><span data-ttu-id="1439e-116">（默认值）挂起的更改不进行缓存，直接写入磁盘中。</span><span class="sxs-lookup"><span data-stu-id="1439e-116">(Default) Pending changes are not cached and are written to disk immediately.</span></span></p></td>
</tr>
</tbody>
</table>

