---
title: AllowNullsEnum (Access desktop database reference)
TOCTitle: AllowNullsEnum
ms:assetid: 7bb42b38-6b3b-5930-b1d7-16323a3bdf37
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249515(v=office.15)
ms:contentKeyID: 48545819
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c184253551fa3f974de1840d47654af597881cb8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297163"
---
# <a name="allownullsenum"></a><span data-ttu-id="85b72-102">AllowNullsEnum</span><span class="sxs-lookup"><span data-stu-id="85b72-102">AllowNullsEnum</span></span>

<span data-ttu-id="85b72-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="85b72-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="85b72-104">指定是否对含有 null 值的记录进行索引。</span><span class="sxs-lookup"><span data-stu-id="85b72-104">Specifies whether records with null values are indexed.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="85b72-105">常量</span><span class="sxs-lookup"><span data-stu-id="85b72-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="85b72-106">值</span><span class="sxs-lookup"><span data-stu-id="85b72-106">Value</span></span></p></th>
<th><p><span data-ttu-id="85b72-107">说明</span><span class="sxs-lookup"><span data-stu-id="85b72-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85b72-108"><strong>adIndexNullsAllow</strong></span><span class="sxs-lookup"><span data-stu-id="85b72-108"><strong>adIndexNullsAllow</strong></span></span></p></td>
<td><p><span data-ttu-id="85b72-109">0</span><span class="sxs-lookup"><span data-stu-id="85b72-109">0</span></span></p></td>
<td><p><span data-ttu-id="85b72-p101">索引允许键列为 null 的项。如果 null 值输入键列中，则该项插入索引中。</span><span class="sxs-lookup"><span data-stu-id="85b72-p101">The index does allow entries in which the key columns are null. If a null value is entered in a key column, the entry is inserted into the index.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85b72-112"><strong>adIndexNullsDisallow</strong></span><span class="sxs-lookup"><span data-stu-id="85b72-112"><strong>adIndexNullsDisallow</strong></span></span></p></td>
<td><p><span data-ttu-id="85b72-113">1</span><span class="sxs-lookup"><span data-stu-id="85b72-113">1</span></span></p></td>
<td><p><span data-ttu-id="85b72-p102">默认值。索引不允许键列为 null 的项。如果 null 值输入键列中，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="85b72-p102">Default. The index does not allow entries in which the key columns are null. If a null value is entered in a key column, an error will occur.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85b72-117"><strong>adIndexNullsIgnore</strong></span><span class="sxs-lookup"><span data-stu-id="85b72-117"><strong>adIndexNullsIgnore</strong></span></span></p></td>
<td><p><span data-ttu-id="85b72-118">双面</span><span class="sxs-lookup"><span data-stu-id="85b72-118">2</span></span></p></td>
<td><p><span data-ttu-id="85b72-p103">索引不插入包含 null 键的项。如果 null 值输入键列中，则该项被忽略并且不会发生错误。</span><span class="sxs-lookup"><span data-stu-id="85b72-p103">The index does not insert entries containing null keys. If a null value is entered in a key column, the entry is ignored and no error occurs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85b72-121"><strong>adIndexNullsIgnoreAny</strong></span><span class="sxs-lookup"><span data-stu-id="85b72-121"><strong>adIndexNullsIgnoreAny</strong></span></span></p></td>
<td><p><span data-ttu-id="85b72-122">4</span><span class="sxs-lookup"><span data-stu-id="85b72-122">4</span></span></p></td>
<td><p><span data-ttu-id="85b72-p104">索引不插入其中某个键列含有 null 值的项。对于带有多列键的索引，如果 null 值输入某个列中，则该项被忽略并且不会发生错误。</span><span class="sxs-lookup"><span data-stu-id="85b72-p104">The index does not insert entries where some key column has a null value. For an index having a multi-column key, if a null value is entered in some column, the entry is ignored and no error occurs.</span></span></p></td>
</tr>
</tbody>
</table>

