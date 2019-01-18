---
title: MemberTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: MemberTypeEnum
ms:assetid: 3b6f9fff-fe54-b917-9404-927e3a627e0b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249150(v=office.15)
ms:contentKeyID: 48544286
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 82d507457d9242daa92cc0218c87bae4d82759a3
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718501"
---
# <a name="membertypeenum"></a><span data-ttu-id="678ee-102">MemberTypeEnum</span><span class="sxs-lookup"><span data-stu-id="678ee-102">MemberTypeEnum</span></span>

<span data-ttu-id="678ee-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="678ee-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="678ee-104">指定 [Member](type-property-ado-md.md) 对象的 [Type](member-object-ado-md.md) 属性的设置。</span><span class="sxs-lookup"><span data-stu-id="678ee-104">Specifies the setting for the [Type](type-property-ado-md.md) property of a [Member](member-object-ado-md.md) object.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="678ee-105">常量</span><span class="sxs-lookup"><span data-stu-id="678ee-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="678ee-106">值</span><span class="sxs-lookup"><span data-stu-id="678ee-106">Value</span></span></p></th>
<th><p><span data-ttu-id="678ee-107">说明</span><span class="sxs-lookup"><span data-stu-id="678ee-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="678ee-108"><strong>adMemberAll</strong></span><span class="sxs-lookup"><span data-stu-id="678ee-108"><strong>adMemberAll</strong></span></span></p></td>
<td><p><span data-ttu-id="678ee-109">4</span><span class="sxs-lookup"><span data-stu-id="678ee-109">4</span></span></p></td>
<td><p><span data-ttu-id="678ee-110">指示 <strong>Member</strong> 对象表示该级别的所有成员。</span><span class="sxs-lookup"><span data-stu-id="678ee-110">Indicates that the <strong>Member</strong> object represents all members of the level.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="678ee-111"><strong>adMemberFormula</strong></span><span class="sxs-lookup"><span data-stu-id="678ee-111"><strong>adMemberFormula</strong></span></span></p></td>
<td><p><span data-ttu-id="678ee-112">3</span><span class="sxs-lookup"><span data-stu-id="678ee-112">3</span></span></p></td>
<td><p><span data-ttu-id="678ee-113">指示 <strong>Member</strong> 对象是使用公式表达式计算的。</span><span class="sxs-lookup"><span data-stu-id="678ee-113">Indicates that the <strong>Member</strong> object is calculated using a formula expression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="678ee-114"><strong>adMemberMeasure</strong></span><span class="sxs-lookup"><span data-stu-id="678ee-114"><strong>adMemberMeasure</strong></span></span></p></td>
<td><p><span data-ttu-id="678ee-115">2</span><span class="sxs-lookup"><span data-stu-id="678ee-115">2</span></span></p></td>
<td><p><span data-ttu-id="678ee-116">指示 <strong>Member</strong> 对象属于“度量”维，并且表示定量属性。</span><span class="sxs-lookup"><span data-stu-id="678ee-116">Indicates that the <strong>Member</strong> object belongs to the Measures dimension and represents a quantitative attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="678ee-117"><strong>adMemberRegular</strong></span><span class="sxs-lookup"><span data-stu-id="678ee-117"><strong>adMemberRegular</strong></span></span></p></td>
<td><p><span data-ttu-id="678ee-118">1</span><span class="sxs-lookup"><span data-stu-id="678ee-118">1</span></span></p></td>
<td><p><span data-ttu-id="678ee-p101">默认值。指示 <strong>Member</strong> 对象表示业务实体的实例。</span><span class="sxs-lookup"><span data-stu-id="678ee-p101">Default. Indicates that the <strong>Member</strong> object represents an instance of a business entity.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="678ee-121"><strong>adMemberUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="678ee-121"><strong>adMemberUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="678ee-122">0</span><span class="sxs-lookup"><span data-stu-id="678ee-122">0</span></span></p></td>
<td><p><span data-ttu-id="678ee-123">无法确定成员的类型。</span><span class="sxs-lookup"><span data-stu-id="678ee-123">Cannot determine the type of the member.</span></span></p></td>
</tr>
</tbody>
</table>

