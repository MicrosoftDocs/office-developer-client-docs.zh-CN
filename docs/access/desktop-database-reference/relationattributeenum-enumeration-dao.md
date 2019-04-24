---
title: RelationAttributeEnum 枚举 (DAO)
TOCTitle: RelationAttributeEnum Enumeration
ms:assetid: ce8d0696-66d7-052f-1313-64baee3442ed
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834499(v=office.15)
ms:contentKeyID: 48547787
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: dbb8ca2e1a63154f17bd814a26fe79ed405765cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306977"
---
# <a name="relationattributeenum-enumeration-dao"></a><span data-ttu-id="e5fc7-102">RelationAttributeEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="e5fc7-102">RelationAttributeEnum enumeration (DAO)</span></span>


<span data-ttu-id="e5fc7-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="e5fc7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e5fc7-104">与 **Attributes** 属性一起用来确定 **Relation** 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="e5fc7-104">Used with the **Attributes** property to determine attributes of a **Relation** object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e5fc7-105">名称</span><span class="sxs-lookup"><span data-stu-id="e5fc7-105">Name</span></span></p></th>
<th><p><span data-ttu-id="e5fc7-106">值</span><span class="sxs-lookup"><span data-stu-id="e5fc7-106">Value</span></span></p></th>
<th><p><span data-ttu-id="e5fc7-107">说明</span><span class="sxs-lookup"><span data-stu-id="e5fc7-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5fc7-108">dbRelationDeleteCascade</span><span class="sxs-lookup"><span data-stu-id="e5fc7-108">dbRelationDeleteCascade</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-109">4096</span><span class="sxs-lookup"><span data-stu-id="e5fc7-109">4096</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-110">级联删除</span><span class="sxs-lookup"><span data-stu-id="e5fc7-110">Deletions cascade</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5fc7-111">dbRelationDontEnforce</span><span class="sxs-lookup"><span data-stu-id="e5fc7-111">dbRelationDontEnforce</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-112">双面</span><span class="sxs-lookup"><span data-stu-id="e5fc7-112">2</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-113">不实施关系（无参照完整性）</span><span class="sxs-lookup"><span data-stu-id="e5fc7-113">Relationship not enforced (no referential integrity)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5fc7-114">dbRelationInherited</span><span class="sxs-lookup"><span data-stu-id="e5fc7-114">dbRelationInherited</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-115">4</span><span class="sxs-lookup"><span data-stu-id="e5fc7-115">4</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-116">关系存在于包含两个链接表的数据库中</span><span class="sxs-lookup"><span data-stu-id="e5fc7-116">Relationship exists in the database containing the two linked tables</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5fc7-117">dbRelationLeft</span><span class="sxs-lookup"><span data-stu-id="e5fc7-117">dbRelationLeft</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-118">16777216</span><span class="sxs-lookup"><span data-stu-id="e5fc7-118">16777216</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-p101">仅适用于 Microsoft Access。在设计视图中，将“左联接”显示为默认的联接类型。</span><span class="sxs-lookup"><span data-stu-id="e5fc7-p101">Microsoft Access only. In Design view, display a LEFT JOIN as the default join type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5fc7-121">dbRelationRight</span><span class="sxs-lookup"><span data-stu-id="e5fc7-121">dbRelationRight</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-122">33554432</span><span class="sxs-lookup"><span data-stu-id="e5fc7-122">33554432</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-p102">仅适用于 Microsoft Access。在设计视图中，将“右联接”显示为默认的联接类型。</span><span class="sxs-lookup"><span data-stu-id="e5fc7-p102">Microsoft Access only. In Design view, display a RIGHT JOIN as the default join type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5fc7-125">dbRelationUnique</span><span class="sxs-lookup"><span data-stu-id="e5fc7-125">dbRelationUnique</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-126">1</span><span class="sxs-lookup"><span data-stu-id="e5fc7-126">1</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-127">一对一关系</span><span class="sxs-lookup"><span data-stu-id="e5fc7-127">One-to-one relationship</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5fc7-128">dbRelationUpdateCascade</span><span class="sxs-lookup"><span data-stu-id="e5fc7-128">dbRelationUpdateCascade</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-129">256</span><span class="sxs-lookup"><span data-stu-id="e5fc7-129">256</span></span></p></td>
<td><p><span data-ttu-id="e5fc7-130">级联更新</span><span class="sxs-lookup"><span data-stu-id="e5fc7-130">Updates cascade</span></span></p></td>
</tr>
</tbody>
</table>

