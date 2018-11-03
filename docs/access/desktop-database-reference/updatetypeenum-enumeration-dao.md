---
title: UpdateTypeEnum 枚举 (DAO)
TOCTitle: UpdateTypeEnum Enumeration
ms:assetid: 7ac38bae-27fc-f3d0-5b75-569bce547954
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196186(v=office.15)
ms:contentKeyID: 48545800
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d38cf4554837c9c6434b7607746f2c40836ac950
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944618"
---
# <a name="updatetypeenum-enumeration-dao"></a><span data-ttu-id="f7262-102">UpdateTypeEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="f7262-102">UpdateTypeEnum enumeration (DAO)</span></span>


<span data-ttu-id="f7262-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f7262-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f7262-104">与 **Update** 方法一起用来指定要写入到磁盘中的更新。</span><span class="sxs-lookup"><span data-stu-id="f7262-104">Used with the **Update** method to specify which updates to write to disk.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f7262-105">名称</span><span class="sxs-lookup"><span data-stu-id="f7262-105">Name</span></span></p></th>
<th><p><span data-ttu-id="f7262-106">值</span><span class="sxs-lookup"><span data-stu-id="f7262-106">Value</span></span></p></th>
<th><p><span data-ttu-id="f7262-107">说明</span><span class="sxs-lookup"><span data-stu-id="f7262-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7262-108">dbUpdateBatch</span><span class="sxs-lookup"><span data-stu-id="f7262-108">dbUpdateBatch</span></span></p></td>
<td><p><span data-ttu-id="f7262-109">4</span><span class="sxs-lookup"><span data-stu-id="f7262-109">4</span></span></p></td>
<td><p><span data-ttu-id="f7262-110">将更新缓存中的所有挂起的更改写入磁盘中。</span><span class="sxs-lookup"><span data-stu-id="f7262-110">All pending changes in the update cache are written to disk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7262-111">dbUpdateCurrentRecord</span><span class="sxs-lookup"><span data-stu-id="f7262-111">dbUpdateCurrentRecord</span></span></p></td>
<td><p><span data-ttu-id="f7262-112">2</span><span class="sxs-lookup"><span data-stu-id="f7262-112">2</span></span></p></td>
<td><p><span data-ttu-id="f7262-113">仅将当前记录的挂起更改写入磁盘中。</span><span class="sxs-lookup"><span data-stu-id="f7262-113">Only the current record's pending changes are written to disk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7262-114">dbUpdateRegular</span><span class="sxs-lookup"><span data-stu-id="f7262-114">dbUpdateRegular</span></span></p></td>
<td><p><span data-ttu-id="f7262-115">1</span><span class="sxs-lookup"><span data-stu-id="f7262-115">1</span></span></p></td>
<td><p><span data-ttu-id="f7262-116">（默认值）挂起的更改不进行缓存，直接写入磁盘中。</span><span class="sxs-lookup"><span data-stu-id="f7262-116">(Default) Pending changes are not cached and are written to disk immediately.</span></span></p></td>
</tr>
</tbody>
</table>

