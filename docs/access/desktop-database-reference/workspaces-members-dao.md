---
title: 工作区成员 (DAO)
TOCTitle: Workspaces Members
ms:assetid: 5eaf6de5-44dc-5566-a98f-db54aecf15cb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194667(v=office.15)
ms:contentKeyID: 48545141
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1718861237e59761c337c504508c60348df2b611
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25923145"
---
# <a name="workspaces-members-dao"></a><span data-ttu-id="0db9d-102">工作区成员 (DAO)</span><span class="sxs-lookup"><span data-stu-id="0db9d-102">Workspaces members (DAO)</span></span>


<span data-ttu-id="0db9d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0db9d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0db9d-p101">Workspaces 集合包含 DBEngine 对象的所有活动、未隐藏的 Workspace 对象。（隐藏的 Workspace 对象并不追加到集合中，而是通过它们分配到的变量进行引用）。</span><span class="sxs-lookup"><span data-stu-id="0db9d-p101">A Workspaces collection contains all active, unhidden Workspace objects of the DBEngine object. (Hidden Workspace objects are not appended to the collection and referenced by the variable to which they are assigned.)</span></span>

## <a name="methods"></a><span data-ttu-id="0db9d-106">方法</span><span class="sxs-lookup"><span data-stu-id="0db9d-106">Methods</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0db9d-107">名称</span><span class="sxs-lookup"><span data-stu-id="0db9d-107">Name</span></span></p></th>
<th><p><span data-ttu-id="0db9d-108">说明</span><span class="sxs-lookup"><span data-stu-id="0db9d-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0db9d-109"><strong><a href="workspaces-append-method-dao.md">追加</a></strong></span><span class="sxs-lookup"><span data-stu-id="0db9d-109"><strong><a href="workspaces-append-method-dao.md">Append</a></strong></span></span></p></td>
<td><p><span data-ttu-id="0db9d-110">将新的 <strong>Workspace</strong> 添加到 <strong>Workspaces</strong> 集合。</span><span class="sxs-lookup"><span data-stu-id="0db9d-110">Adds a new <strong>Workspace</strong> to the <strong>Workspaces</strong> collection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0db9d-111"><strong><a href="workspaces-delete-method-dao.md">删除</a></strong></span><span class="sxs-lookup"><span data-stu-id="0db9d-111"><strong><a href="workspaces-delete-method-dao.md">Delete</a></strong></span></span></p></td>
<td><p><span data-ttu-id="0db9d-112">从 <strong>Workspaces</strong> 集合中删除指定的 <strong>Workspace</strong>。</span><span class="sxs-lookup"><span data-stu-id="0db9d-112">Deletes the specified <strong>Workspace</strong> form the <strong>Workspaces</strong> collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0db9d-113"><strong><a href="workspaces-refresh-method-dao.md">Refresh</a></strong></span><span class="sxs-lookup"><span data-stu-id="0db9d-113"><strong><a href="workspaces-refresh-method-dao.md">Refresh</a></strong></span></span></p></td>
<td><p><span data-ttu-id="0db9d-114">此对象不支持的操作。</span><span class="sxs-lookup"><span data-stu-id="0db9d-114">Not supported for this object.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="properties"></a><span data-ttu-id="0db9d-115">属性</span><span class="sxs-lookup"><span data-stu-id="0db9d-115">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0db9d-116">名称</span><span class="sxs-lookup"><span data-stu-id="0db9d-116">Name</span></span></p></th>
<th><p><span data-ttu-id="0db9d-117">说明</span><span class="sxs-lookup"><span data-stu-id="0db9d-117">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0db9d-118"><strong><a href="workspaces-count-property-dao.md">计数</a></strong></span><span class="sxs-lookup"><span data-stu-id="0db9d-118"><strong><a href="workspaces-count-property-dao.md">Count</a></strong></span></span></p></td>
<td><p><span data-ttu-id="0db9d-p102">返回指定集合中的对象数。只读。</span><span class="sxs-lookup"><span data-stu-id="0db9d-p102">Returns the number of objects in the specified collection. Read-only.</span></span></p></td>
</tr>
</tbody>
</table>

