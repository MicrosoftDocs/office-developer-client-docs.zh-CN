---
title: ObjectTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: ObjectTypeEnum
ms:assetid: b0ee2113-dea9-912d-3442-e54885397310
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249842(v=office.15)
ms:contentKeyID: 48547132
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6e3b470c8c0d0c3f04b59bd382b66117bd79c188
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711831"
---
# <a name="objecttypeenum"></a><span data-ttu-id="e7eab-102">ObjectTypeEnum</span><span class="sxs-lookup"><span data-stu-id="e7eab-102">ObjectTypeEnum</span></span>

<span data-ttu-id="e7eab-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e7eab-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e7eab-104">指定设置权限和所有权所针对的数据库对象的类型。</span><span class="sxs-lookup"><span data-stu-id="e7eab-104">Specifies the type of database object for which to set permissions or ownership.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e7eab-105">常量</span><span class="sxs-lookup"><span data-stu-id="e7eab-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="e7eab-106">值</span><span class="sxs-lookup"><span data-stu-id="e7eab-106">Value</span></span></p></th>
<th><p><span data-ttu-id="e7eab-107">说明</span><span class="sxs-lookup"><span data-stu-id="e7eab-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7eab-108"><strong>adPermObjColumn</strong></span><span class="sxs-lookup"><span data-stu-id="e7eab-108"><strong>adPermObjColumn</strong></span></span></p></td>
<td><p><span data-ttu-id="e7eab-109">2</span><span class="sxs-lookup"><span data-stu-id="e7eab-109">2</span></span></p></td>
<td><p><span data-ttu-id="e7eab-110">对象为列。</span><span class="sxs-lookup"><span data-stu-id="e7eab-110">The object is a column.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7eab-111"><strong>adPermObjDatabase</strong></span><span class="sxs-lookup"><span data-stu-id="e7eab-111"><strong>adPermObjDatabase</strong></span></span></p></td>
<td><p><span data-ttu-id="e7eab-112">3</span><span class="sxs-lookup"><span data-stu-id="e7eab-112">3</span></span></p></td>
<td><p><span data-ttu-id="e7eab-113">对象为数据库。</span><span class="sxs-lookup"><span data-stu-id="e7eab-113">The object is a database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7eab-114"><strong>adPermObjProcedure</strong></span><span class="sxs-lookup"><span data-stu-id="e7eab-114"><strong>adPermObjProcedure</strong></span></span></p></td>
<td><p><span data-ttu-id="e7eab-115">4</span><span class="sxs-lookup"><span data-stu-id="e7eab-115">4</span></span></p></td>
<td><p><span data-ttu-id="e7eab-116">对象为过程。</span><span class="sxs-lookup"><span data-stu-id="e7eab-116">The object is a procedure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7eab-117"><strong>adPermObjProviderSpecific</strong></span><span class="sxs-lookup"><span data-stu-id="e7eab-117"><strong>adPermObjProviderSpecific</strong></span></span></p></td>
<td><p><span data-ttu-id="e7eab-118">-1</span><span class="sxs-lookup"><span data-stu-id="e7eab-118">-1</span></span></p></td>
<td><p><span data-ttu-id="e7eab-p101">对象类型由提供程序定义。如果 <em>ObjectType</em> 参数为 <strong>adPermObjProviderSpecific</strong>，同时未提供 <em>ObjectTypeId</em>，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="e7eab-p101">The object is a type defined by the provider. An error will occur if the <em>ObjectType</em> parameter is <strong>adPermObjProviderSpecific</strong> and an <em>ObjectTypeId</em> is not supplied.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7eab-121"><strong>adPermObjTable</strong></span><span class="sxs-lookup"><span data-stu-id="e7eab-121"><strong>adPermObjTable</strong></span></span></p></td>
<td><p><span data-ttu-id="e7eab-122">1</span><span class="sxs-lookup"><span data-stu-id="e7eab-122">1</span></span></p></td>
<td><p><span data-ttu-id="e7eab-123">对象为表。</span><span class="sxs-lookup"><span data-stu-id="e7eab-123">The object is a table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7eab-124"><strong>adPermObjView</strong></span><span class="sxs-lookup"><span data-stu-id="e7eab-124"><strong>adPermObjView</strong></span></span></p></td>
<td><p><span data-ttu-id="e7eab-125">5</span><span class="sxs-lookup"><span data-stu-id="e7eab-125">5</span></span></p></td>
<td><p><span data-ttu-id="e7eab-126">对象为视图。</span><span class="sxs-lookup"><span data-stu-id="e7eab-126">The object is a view.</span></span></p></td>
</tr>
</tbody>
</table>

