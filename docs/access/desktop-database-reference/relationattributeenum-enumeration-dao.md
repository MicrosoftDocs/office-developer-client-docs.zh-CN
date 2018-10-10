---
title: RelationAttributeEnum Enumeration (DAO)
TOCTitle: RelationAttributeEnum Enumeration
ms:assetid: ce8d0696-66d7-052f-1313-64baee3442ed
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834499(v=office.15)
ms:contentKeyID: 48547787
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4c4d7a2b622e382461bcf1b4171a5aa85f036854
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468259"
---
# <a name="relationattributeenum-enumeration-dao"></a><span data-ttu-id="d8d65-102">RelationAttributeEnum Enumeration (DAO)</span><span class="sxs-lookup"><span data-stu-id="d8d65-102">RelationAttributeEnum Enumeration (DAO)</span></span>


<span data-ttu-id="d8d65-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d8d65-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="d8d65-104">与 **Attributes** 属性一起用来确定 **Relation** 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="d8d65-104">Used with the **Attributes** property to determine attributes of a **Relation** object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d8d65-105">名称</span><span class="sxs-lookup"><span data-stu-id="d8d65-105">Name</span></span></p></th>
<th><p><span data-ttu-id="d8d65-106">值</span><span class="sxs-lookup"><span data-stu-id="d8d65-106">Value</span></span></p></th>
<th><p><span data-ttu-id="d8d65-107">说明</span><span class="sxs-lookup"><span data-stu-id="d8d65-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8d65-108">dbRelationDeleteCascade</span><span class="sxs-lookup"><span data-stu-id="d8d65-108">dbRelationDeleteCascade</span></span></p></td>
<td><p><span data-ttu-id="d8d65-109">4096</span><span class="sxs-lookup"><span data-stu-id="d8d65-109">4096</span></span></p></td>
<td><p><span data-ttu-id="d8d65-110">级联删除</span><span class="sxs-lookup"><span data-stu-id="d8d65-110">Deletions cascade</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8d65-111">dbRelationDontEnforce</span><span class="sxs-lookup"><span data-stu-id="d8d65-111">dbRelationDontEnforce</span></span></p></td>
<td><p><span data-ttu-id="d8d65-112">2</span><span class="sxs-lookup"><span data-stu-id="d8d65-112">2</span></span></p></td>
<td><p><span data-ttu-id="d8d65-113">不实施关系（无参照完整性）</span><span class="sxs-lookup"><span data-stu-id="d8d65-113">Relationship not enforced (no referential integrity)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8d65-114">dbRelationInherited</span><span class="sxs-lookup"><span data-stu-id="d8d65-114">dbRelationInherited</span></span></p></td>
<td><p><span data-ttu-id="d8d65-115">4</span><span class="sxs-lookup"><span data-stu-id="d8d65-115">4</span></span></p></td>
<td><p><span data-ttu-id="d8d65-116">关系存在于包含两个链接表的数据库中</span><span class="sxs-lookup"><span data-stu-id="d8d65-116">Relationship exists in the database containing the two linked tables</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8d65-117">dbRelationLeft</span><span class="sxs-lookup"><span data-stu-id="d8d65-117">dbRelationLeft</span></span></p></td>
<td><p><span data-ttu-id="d8d65-118">16777216</span><span class="sxs-lookup"><span data-stu-id="d8d65-118">16777216</span></span></p></td>
<td><p><span data-ttu-id="d8d65-p101">仅适用于 Microsoft Access。在设计视图中，将“左联接”显示为默认的联接类型。</span><span class="sxs-lookup"><span data-stu-id="d8d65-p101">Microsoft Access only. In Design view, display a LEFT JOIN as the default join type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8d65-121">dbRelationRight</span><span class="sxs-lookup"><span data-stu-id="d8d65-121">dbRelationRight</span></span></p></td>
<td><p><span data-ttu-id="d8d65-122">33554432</span><span class="sxs-lookup"><span data-stu-id="d8d65-122">33554432</span></span></p></td>
<td><p><span data-ttu-id="d8d65-p102">仅适用于 Microsoft Access。在设计视图中，将“右联接”显示为默认的联接类型。</span><span class="sxs-lookup"><span data-stu-id="d8d65-p102">Microsoft Access only. In Design view, display a RIGHT JOIN as the default join type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8d65-125">dbRelationUnique</span><span class="sxs-lookup"><span data-stu-id="d8d65-125">dbRelationUnique</span></span></p></td>
<td><p><span data-ttu-id="d8d65-126">1</span><span class="sxs-lookup"><span data-stu-id="d8d65-126">1</span></span></p></td>
<td><p><span data-ttu-id="d8d65-127">一对一关系</span><span class="sxs-lookup"><span data-stu-id="d8d65-127">One-to-one relationship</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8d65-128">两</span><span class="sxs-lookup"><span data-stu-id="d8d65-128">dbRelationUpdateCascade</span></span></p></td>
<td><p><span data-ttu-id="d8d65-129">256</span><span class="sxs-lookup"><span data-stu-id="d8d65-129">256</span></span></p></td>
<td><p><span data-ttu-id="d8d65-130">级联更新</span><span class="sxs-lookup"><span data-stu-id="d8d65-130">Updates cascade</span></span></p></td>
</tr>
</tbody>
</table>

