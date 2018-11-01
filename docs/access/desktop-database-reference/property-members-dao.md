---
title: Property Members (DAO)
TOCTitle: Property Members
ms:assetid: 32658adb-f153-148d-a216-eb97b996579a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192303(v=office.15)
ms:contentKeyID: 48544076
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 07e9aa4ec5305b79dc3e48442cf6b76b2ce78fb7
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25888277"
---
# <a name="property-members-dao"></a><span data-ttu-id="23788-102">Property Members (DAO)</span><span class="sxs-lookup"><span data-stu-id="23788-102">Property Members (DAO)</span></span>


<span data-ttu-id="23788-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="23788-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="23788-104">Property 对象代表 DAO 对象的内部特征或用户定义特征。</span><span class="sxs-lookup"><span data-stu-id="23788-104">A Property object represents a built-in or user-defined characteristic of a DAO object.</span></span>

## <a name="properties"></a><span data-ttu-id="23788-105">属性</span><span class="sxs-lookup"><span data-stu-id="23788-105">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="23788-106">名称</span><span class="sxs-lookup"><span data-stu-id="23788-106">Name</span></span></p></th>
<th><p><span data-ttu-id="23788-107">说明</span><span class="sxs-lookup"><span data-stu-id="23788-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23788-108"><strong><a href="property-inherited-property-dao.md">Inherited</a></strong></span><span class="sxs-lookup"><span data-stu-id="23788-108"><strong><a href="property-inherited-property-dao.md">Inherited</a></strong></span></span></p></td>
<td><p><span data-ttu-id="23788-109">返回一个值，该值指示某个 <strong><a href="property-object-dao.md">Property</a></strong> 对象是否是从基础对象中继承的。</span><span class="sxs-lookup"><span data-stu-id="23788-109">Returns a value that indicates whether a <strong><a href="property-object-dao.md">Property</a></strong> object is inherited from an underlying object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23788-110"><strong><a href="property-name-property-dao.md">Name</a></strong></span><span class="sxs-lookup"><span data-stu-id="23788-110"><strong><a href="property-name-property-dao.md">Name</a></strong></span></span></p></td>
<td><p><span data-ttu-id="23788-p101">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 <strong>String</strong> 类型；对于已追加到集合中的对象，该属性为只读 <strong>String</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="23788-p101">Returns or sets the name of the specified object. Read/write <strong>String</strong> if the object has not been appended to a collection. Read-only <strong>String</strong> if the object has been appended to a collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23788-114"><strong><a href="property-properties-property-dao.md">属性</a></strong></span><span class="sxs-lookup"><span data-stu-id="23788-114"><strong><a href="property-properties-property-dao.md">Properties</a></strong></span></span></p></td>
<td><p><span data-ttu-id="23788-p102">返回指定对象的 <strong><a href="properties-collection-dao.md">Properties</a></strong> 集合。只读。</span><span class="sxs-lookup"><span data-stu-id="23788-p102">Returns the <strong><a href="properties-collection-dao.md">Properties</a></strong> collection of the specified object. Read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23788-117"><strong><a href="property-type-property-dao.md">类型</a></strong></span><span class="sxs-lookup"><span data-stu-id="23788-117"><strong><a href="property-type-property-dao.md">Type</a></strong></span></span></p></td>
<td><p><span data-ttu-id="23788-p103">设置或返回一个值，该值指示对象的操作类型或数据类型。可读写 <strong>Integer</strong>。</span><span class="sxs-lookup"><span data-stu-id="23788-p103">Sets or returns a value that indicates the operational type or data type of an object. Read/write <strong>Integer</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23788-120"><strong><a href="property-value-property-dao.md">值</a></strong></span><span class="sxs-lookup"><span data-stu-id="23788-120"><strong><a href="property-value-property-dao.md">Value</a></strong></span></span></p></td>
<td><p><span data-ttu-id="23788-p104">设置或返回对象的值。可读/写 <strong>Variant</strong> 类型。</span><span class="sxs-lookup"><span data-stu-id="23788-p104">Sets or returns the value of an object. Read/write <strong>Variant</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

