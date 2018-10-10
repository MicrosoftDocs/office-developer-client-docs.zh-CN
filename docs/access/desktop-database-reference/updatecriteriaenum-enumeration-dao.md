---
title: UpdateCriteriaEnum Enumeration (DAO)
TOCTitle: UpdateCriteriaEnum Enumeration
ms:assetid: 1f83a0c6-bdc8-9c3e-380b-524f611f6476
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845853(v=office.15)
ms:contentKeyID: 48543644
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7dc671458d53f6e40e27ff2dd338f010c09dc5ba
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466623"
---
# <a name="updatecriteriaenum-enumeration-dao"></a><span data-ttu-id="6603e-102">UpdateCriteriaEnum Enumeration (DAO)</span><span class="sxs-lookup"><span data-stu-id="6603e-102">UpdateCriteriaEnum Enumeration (DAO)</span></span>


<span data-ttu-id="6603e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6603e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6603e-104">与 **UpdateOptions** 方法一起用来指定如何构造批更新。</span><span class="sxs-lookup"><span data-stu-id="6603e-104">Used with the **UpdateOptions** method to specify how a batch update is constructed.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6603e-105">名称</span><span class="sxs-lookup"><span data-stu-id="6603e-105">Name</span></span></p></th>
<th><p><span data-ttu-id="6603e-106">值</span><span class="sxs-lookup"><span data-stu-id="6603e-106">Value</span></span></p></th>
<th><p><span data-ttu-id="6603e-107">说明</span><span class="sxs-lookup"><span data-stu-id="6603e-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6603e-108">dbCriteriaAllCols</span><span class="sxs-lookup"><span data-stu-id="6603e-108">dbCriteriaAllCols</span></span></p></td>
<td><p><span data-ttu-id="6603e-109">4</span><span class="sxs-lookup"><span data-stu-id="6603e-109">4</span></span></p></td>
<td><p><span data-ttu-id="6603e-110">在 where 子句中使用键列和所有列。</span><span class="sxs-lookup"><span data-stu-id="6603e-110">Uses the key column(s) and all the columns in the where clause.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6603e-111">dbCriteriaDeleteInsert</span><span class="sxs-lookup"><span data-stu-id="6603e-111">dbCriteriaDeleteInsert</span></span></p></td>
<td><p><span data-ttu-id="6603e-112">16</span><span class="sxs-lookup"><span data-stu-id="6603e-112">16</span></span></p></td>
<td><p><span data-ttu-id="6603e-113">对于每个已修改行都使用一对 DELETE 和 INSERT 语句。</span><span class="sxs-lookup"><span data-stu-id="6603e-113">Uses a pair of DELETE and INSERT statements for each modified row.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6603e-114">dbCriteriaKey</span><span class="sxs-lookup"><span data-stu-id="6603e-114">dbCriteriaKey</span></span></p></td>
<td><p><span data-ttu-id="6603e-115">1</span><span class="sxs-lookup"><span data-stu-id="6603e-115">1</span></span></p></td>
<td><p><span data-ttu-id="6603e-116">仅在 where 子句中使用键列。</span><span class="sxs-lookup"><span data-stu-id="6603e-116">Uses just the key column(s) in the where clause.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6603e-117">dbCriteriaModValues</span><span class="sxs-lookup"><span data-stu-id="6603e-117">dbCriteriaModValues</span></span></p></td>
<td><p><span data-ttu-id="6603e-118">2</span><span class="sxs-lookup"><span data-stu-id="6603e-118">2</span></span></p></td>
<td><p><span data-ttu-id="6603e-119">在 where 子句中使用键列和所有已更新列。</span><span class="sxs-lookup"><span data-stu-id="6603e-119">Uses the key column(s) and all updated columns in the where clause.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6603e-120">dbCriteriaTimestamp</span><span class="sxs-lookup"><span data-stu-id="6603e-120">dbCriteriaTimestamp</span></span></p></td>
<td><p><span data-ttu-id="6603e-121">8</span><span class="sxs-lookup"><span data-stu-id="6603e-121">8</span></span></p></td>
<td><p><span data-ttu-id="6603e-122">仅使用可用的时间戳列（如果结果集内没有时间戳列，将生成运行时错误）。</span><span class="sxs-lookup"><span data-stu-id="6603e-122">Uses just the timestamp column if available (will generate a run-time error if no timestamp column is in the result set).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6603e-123">将使用 dbCriteriaUpdate</span><span class="sxs-lookup"><span data-stu-id="6603e-123">dbCriteriaUpdate</span></span></p></td>
<td><p><span data-ttu-id="6603e-124">32</span><span class="sxs-lookup"><span data-stu-id="6603e-124">32</span></span></p></td>
<td><p><span data-ttu-id="6603e-125">对于每个已修改行都使用一个 UPDATE 语句。</span><span class="sxs-lookup"><span data-stu-id="6603e-125">Uses an UPDATE statement for each modified row.</span></span></p></td>
</tr>
</tbody>
</table>

