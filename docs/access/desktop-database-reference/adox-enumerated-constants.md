---
title: ADOX 枚举常量
TOCTitle: ADOX enumerated constants
ms:assetid: 0ad716a0-8801-50cb-024a-85c308c65c78
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248840(v=office.15)
ms:contentKeyID: 48543163
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 385a3a106c04db11b36ea646368f80fe28ffd413
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280193"
---
# <a name="adox-enumerated-constants"></a><span data-ttu-id="c8b52-102">ADOX 枚举常量</span><span class="sxs-lookup"><span data-stu-id="c8b52-102">ADOX enumerated constants</span></span>

<span data-ttu-id="c8b52-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c8b52-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c8b52-p101">为有助于进行调试，ADOX 枚举常量为每一个常量列出了一个值。但是，该值纯粹是参考性的，并且可能随不同的 ADOX 版本而变化。您的代码应依赖于枚举常量的名称，而不是实际值。</span><span class="sxs-lookup"><span data-stu-id="c8b52-p101">To assist debugging, the ADOX enumerated constants list a value for each constant. However, this value is purely advisory, and may change from one release of ADOX to another. Your code should only depend on the name, not the actual value, of enumerated constants.</span></span>

<span data-ttu-id="c8b52-107">已定义下列枚举常量。</span><span class="sxs-lookup"><span data-stu-id="c8b52-107">The following enumerated constants are defined.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c8b52-108">枚举</span><span class="sxs-lookup"><span data-stu-id="c8b52-108">Enumeration</span></span></p></th>
<th><p><span data-ttu-id="c8b52-109">说明</span><span class="sxs-lookup"><span data-stu-id="c8b52-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8b52-110"><a href="actionenum.md">ActionEnum</a></span><span class="sxs-lookup"><span data-stu-id="c8b52-110"><a href="actionenum.md">ActionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="c8b52-111">指定调用 <strong>SetPermissions</strong> 时要执行的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="c8b52-111">Specifies the type of action to be performed when <strong>SetPermissions</strong> is called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8b52-112"><a href="allownullsenum.md">AllowNullsEnum</a></span><span class="sxs-lookup"><span data-stu-id="c8b52-112"><a href="allownullsenum.md">AllowNullsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="c8b52-113">指定是否对含有 null 值的记录进行索引。</span><span class="sxs-lookup"><span data-stu-id="c8b52-113">Specifies whether records with null values are indexed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8b52-114"><a href="columnattributesenum.md">ColumnAttributesEnum</a></span><span class="sxs-lookup"><span data-stu-id="c8b52-114"><a href="columnattributesenum.md">ColumnAttributesEnum</a></span></span></p></td>
<td><p><span data-ttu-id="c8b52-115">指定 <strong>Column</strong> 的特征。</span><span class="sxs-lookup"><span data-stu-id="c8b52-115">Specifies characteristics of a <strong>Column</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8b52-116"><a href="datatypeenum.md">DataTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="c8b52-116"><a href="datatypeenum.md">DataTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="c8b52-117">指定 <strong>Field</strong>、<strong>Parameter</strong> 或 <strong>Property</strong> 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c8b52-117">Specifies the data type of a <strong>Field</strong>, <strong>Parameter</strong>, or <strong>Property</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8b52-118"><a href="inherittypeenum.md">InheritTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="c8b52-118"><a href="inherittypeenum.md">InheritTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="c8b52-119">指定对象将如何继承通过 <strong>SetPermissions</strong> 设置的权限。</span><span class="sxs-lookup"><span data-stu-id="c8b52-119">Specifies how objects will inherit permissions set with <strong>SetPermissions</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8b52-120"><a href="keytypeenum.md">KeyTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="c8b52-120"><a href="keytypeenum.md">KeyTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="c8b52-121">指定 <strong>Key</strong> 的类型：主键、外键或唯一键。</span><span class="sxs-lookup"><span data-stu-id="c8b52-121">Specifies the type of <strong>Key</strong>: primary, foreign, or unique.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8b52-122"><a href="objecttypeenum.md">ObjectTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="c8b52-122"><a href="objecttypeenum.md">ObjectTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="c8b52-123">指定设置权限和所有权所针对的数据库对象的类型。</span><span class="sxs-lookup"><span data-stu-id="c8b52-123">Specifies the type of database object for which to set permissions or ownership.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8b52-124"><a href="rightsenum.md">RightsEnum</a></span><span class="sxs-lookup"><span data-stu-id="c8b52-124"><a href="rightsenum.md">RightsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="c8b52-125">指定组或用户对某个对象的权限。</span><span class="sxs-lookup"><span data-stu-id="c8b52-125">Specifies the rights or permissions for a group or user on an object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8b52-126"><a href="ruleenum.md">RuleEnum</a></span><span class="sxs-lookup"><span data-stu-id="c8b52-126"><a href="ruleenum.md">RuleEnum</a></span></span></p></td>
<td><p><span data-ttu-id="c8b52-127">指定删除 <strong>Key</strong> 时应遵循的规则。</span><span class="sxs-lookup"><span data-stu-id="c8b52-127">Specifies the rule to follow when a <strong>Key</strong> is deleted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8b52-128"><a href="sortorderenum.md">SortOrderEnum</a></span><span class="sxs-lookup"><span data-stu-id="c8b52-128"><a href="sortorderenum.md">SortOrderEnum</a></span></span></p></td>
<td><p><span data-ttu-id="c8b52-129">指定索引列的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="c8b52-129">Specifies the sort sequence for an indexed column.</span></span></p></td>
</tr>
</tbody>
</table>

