---
title: ADOX 枚举常量
TOCTitle: ADOX enumerated constants
ms:assetid: 0ad716a0-8801-50cb-024a-85c308c65c78
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248840(v=office.15)
ms:contentKeyID: 48543163
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5ee99f8795dce4587d795b2cea4ac70a74c5eaa7
ms.sourcegitcommit: 48bfe5ab15b11105f4f52937b886c92bdc26525a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25910808"
---
# <a name="adox-enumerated-constants"></a><span data-ttu-id="fa374-102">ADOX 枚举常量</span><span class="sxs-lookup"><span data-stu-id="fa374-102">ADOX enumerated constants</span></span>

<span data-ttu-id="fa374-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fa374-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fa374-p101">为有助于进行调试，ADOX 枚举常量为每一个常量列出了一个值。但是，该值纯粹是参考性的，并且可能随不同的 ADOX 版本而变化。您的代码应依赖于枚举常量的名称，而不是实际值。</span><span class="sxs-lookup"><span data-stu-id="fa374-p101">To assist debugging, the ADOX enumerated constants list a value for each constant. However, this value is purely advisory, and may change from one release of ADOX to another. Your code should only depend on the name, not the actual value, of enumerated constants.</span></span>

<span data-ttu-id="fa374-107">已定义下列枚举常量。</span><span class="sxs-lookup"><span data-stu-id="fa374-107">The following enumerated constants are defined.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fa374-108">枚举</span><span class="sxs-lookup"><span data-stu-id="fa374-108">Enumeration</span></span></p></th>
<th><p><span data-ttu-id="fa374-109">说明</span><span class="sxs-lookup"><span data-stu-id="fa374-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa374-110"><a href="actionenum.md">ActionEnum</a></span><span class="sxs-lookup"><span data-stu-id="fa374-110"><a href="actionenum.md">ActionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="fa374-111">指定调用 <strong>SetPermissions</strong> 时要执行的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="fa374-111">Specifies the type of action to be performed when <strong>SetPermissions</strong> is called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa374-112"><a href="allownullsenum.md">AllowNullsEnum</a></span><span class="sxs-lookup"><span data-stu-id="fa374-112"><a href="allownullsenum.md">AllowNullsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="fa374-113">指定是否对含有 null 值的记录进行索引。</span><span class="sxs-lookup"><span data-stu-id="fa374-113">Specifies whether records with null values are indexed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa374-114"><a href="columnattributesenum.md">ColumnAttributesEnum</a></span><span class="sxs-lookup"><span data-stu-id="fa374-114"><a href="columnattributesenum.md">ColumnAttributesEnum</a></span></span></p></td>
<td><p><span data-ttu-id="fa374-115">指定 <strong>Column</strong> 的特征。</span><span class="sxs-lookup"><span data-stu-id="fa374-115">Specifies characteristics of a <strong>Column</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa374-116"><a href="datatypeenum.md">DataTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="fa374-116"><a href="datatypeenum.md">DataTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="fa374-117">用于指定 <strong>Field</strong>、<strong>Parameter</strong> 或 <strong>Property</strong> 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="fa374-117">Specifies the data type of a <strong>Field</strong>, <strong>Parameter</strong>, or <strong>Property</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa374-118"><a href="inherittypeenum.md">InheritTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="fa374-118"><a href="inherittypeenum.md">InheritTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="fa374-119">指定对象将如何继承通过 <strong>SetPermissions</strong> 设置的权限。</span><span class="sxs-lookup"><span data-stu-id="fa374-119">Specifies how objects will inherit permissions set with <strong>SetPermissions</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa374-120"><a href="keytypeenum.md">KeyTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="fa374-120"><a href="keytypeenum.md">KeyTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="fa374-121">指定 <strong>Key</strong> 的类型：主键、外键或唯一键。</span><span class="sxs-lookup"><span data-stu-id="fa374-121">Specifies the type of <strong>Key</strong>: primary, foreign, or unique.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa374-122"><a href="objecttypeenum.md">ObjectTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="fa374-122"><a href="objecttypeenum.md">ObjectTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="fa374-123">指定设置权限和所有权所针对的数据库对象的类型。</span><span class="sxs-lookup"><span data-stu-id="fa374-123">Specifies the type of database object for which to set permissions or ownership.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa374-124"><a href="rightsenum.md">RightsEnum</a></span><span class="sxs-lookup"><span data-stu-id="fa374-124"><a href="rightsenum.md">RightsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="fa374-125">指定组或用户对某个对象的权限。</span><span class="sxs-lookup"><span data-stu-id="fa374-125">Specifies the rights or permissions for a group or user on an object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa374-126"><a href="ruleenum.md">RuleEnum</a></span><span class="sxs-lookup"><span data-stu-id="fa374-126"><a href="ruleenum.md">RuleEnum</a></span></span></p></td>
<td><p><span data-ttu-id="fa374-127">指定删除 <strong>Key</strong> 时应遵循的规则。</span><span class="sxs-lookup"><span data-stu-id="fa374-127">Specifies the rule to follow when a <strong>Key</strong> is deleted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa374-128"><a href="sortorderenum.md">SortOrderEnum</a></span><span class="sxs-lookup"><span data-stu-id="fa374-128"><a href="sortorderenum.md">SortOrderEnum</a></span></span></p></td>
<td><p><span data-ttu-id="fa374-129">指定索引列的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="fa374-129">Specifies the sort sequence for an indexed column.</span></span></p></td>
</tr>
</tbody>
</table>

