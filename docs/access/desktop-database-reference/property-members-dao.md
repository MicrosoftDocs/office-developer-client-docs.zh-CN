---
title: 属性成员 (DAO)
TOCTitle: Property Members
ms:assetid: 32658adb-f153-148d-a216-eb97b996579a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192303(v=office.15)
ms:contentKeyID: 48544076
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: fe60c12a85eff0dd8f796f9affeef71979dac580
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301209"
---
# <a name="property-members-dao"></a><span data-ttu-id="ca7ca-102">属性成员 (DAO)</span><span class="sxs-lookup"><span data-stu-id="ca7ca-102">Property members (DAO)</span></span>


<span data-ttu-id="ca7ca-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ca7ca-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ca7ca-104">Property 对象代表 DAO 对象的内部特征或用户定义特征。</span><span class="sxs-lookup"><span data-stu-id="ca7ca-104">A Property object represents a built-in or user-defined characteristic of a DAO object.</span></span>

## <a name="properties"></a><span data-ttu-id="ca7ca-105">属性</span><span class="sxs-lookup"><span data-stu-id="ca7ca-105">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ca7ca-106">名称</span><span class="sxs-lookup"><span data-stu-id="ca7ca-106">Name</span></span></p></th>
<th><p><span data-ttu-id="ca7ca-107">说明</span><span class="sxs-lookup"><span data-stu-id="ca7ca-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca7ca-108"><strong><a href="property-inherited-property-dao.md">继承</a></strong></span><span class="sxs-lookup"><span data-stu-id="ca7ca-108"><strong><a href="property-inherited-property-dao.md">Inherited</a></strong></span></span></p></td>
<td><p><span data-ttu-id="ca7ca-109">返回一个值，该值指示某个 <strong><a href="property-object-dao.md">Property</a></strong> 对象是否是从基础对象中继承的。</span><span class="sxs-lookup"><span data-stu-id="ca7ca-109">Returns a value that indicates whether a <strong><a href="property-object-dao.md">Property</a></strong> object is inherited from an underlying object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca7ca-110"><strong><a href="property-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="ca7ca-110"><strong><a href="property-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="ca7ca-p101">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 <strong>String</strong> 类型；对于已追加到集合中的对象，该属性为只读 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="ca7ca-p101">Returns or sets the name of the specified object. Read/write <strong>String</strong> if the object has not been appended to a collection. Read-only <strong>String</strong> if the object has been appended to a collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca7ca-114"><strong><a href="property-properties-property-dao.md">属性</a></strong></span><span class="sxs-lookup"><span data-stu-id="ca7ca-114"><strong><a href="property-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="ca7ca-115">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。</span><span class="sxs-lookup"><span data-stu-id="ca7ca-115">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object.</span></span> <span data-ttu-id="ca7ca-116">只读。</span><span class="sxs-lookup"><span data-stu-id="ca7ca-116">Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca7ca-117"><strong><a href="property-type-property-dao.md">Type</a></strong></span><span class="sxs-lookup"><span data-stu-id="ca7ca-117"><strong><a href="property-type-property-dao.md">Type</a></strong></span></span></p></td>
<td><p><span data-ttu-id="ca7ca-118">设置或返回一个值，该值指示对象的操作类型或数据类型。</span><span class="sxs-lookup"><span data-stu-id="ca7ca-118">Sets or returns a value that indicates the operational type or data type of an object.</span></span> <span data-ttu-id="ca7ca-119">可读/写 <strong>Integer</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="ca7ca-119">Read/write <strong>Integer</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca7ca-120"><strong><a href="property-value-property-dao.md">值</a></strong></span><span class="sxs-lookup"><span data-stu-id="ca7ca-120"><strong><a href="property-value-property-dao.md">Value</a></strong></span></span></p></td>
<td><p><span data-ttu-id="ca7ca-121">设置或返回对象的值。</span><span class="sxs-lookup"><span data-stu-id="ca7ca-121">Sets or returns the value of an object.</span></span> <span data-ttu-id="ca7ca-122"><strong>Variant</strong> 类型，可读写。</span><span class="sxs-lookup"><span data-stu-id="ca7ca-122">Read/write <strong>Variant</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

