---
title: UpdateCriteriaEnum 枚举 (DAO)
TOCTitle: UpdateCriteriaEnum Enumeration
ms:assetid: 1f83a0c6-bdc8-9c3e-380b-524f611f6476
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845853(v=office.15)
ms:contentKeyID: 48543644
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d6160c53dd1cab26b2b92ec023f28158635d7081
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944464"
---
# <a name="updatecriteriaenum-enumeration-dao"></a><span data-ttu-id="eb3c4-102">UpdateCriteriaEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="eb3c4-102">UpdateCriteriaEnum enumeration (DAO)</span></span>


<span data-ttu-id="eb3c4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="eb3c4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="eb3c4-104">与 **UpdateOptions** 方法一起用来指定如何构造批更新。</span><span class="sxs-lookup"><span data-stu-id="eb3c4-104">Used with the **UpdateOptions** method to specify how a batch update is constructed.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="eb3c4-105">名称</span><span class="sxs-lookup"><span data-stu-id="eb3c4-105">Name</span></span></p></th>
<th><p><span data-ttu-id="eb3c4-106">值</span><span class="sxs-lookup"><span data-stu-id="eb3c4-106">Value</span></span></p></th>
<th><p><span data-ttu-id="eb3c4-107">说明</span><span class="sxs-lookup"><span data-stu-id="eb3c4-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb3c4-108">dbCriteriaAllCols</span><span class="sxs-lookup"><span data-stu-id="eb3c4-108">dbCriteriaAllCols</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-109">4</span><span class="sxs-lookup"><span data-stu-id="eb3c4-109">4</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-110">在 where 子句中使用键列和所有列。</span><span class="sxs-lookup"><span data-stu-id="eb3c4-110">Uses the key column(s) and all the columns in the where clause.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb3c4-111">dbCriteriaDeleteInsert</span><span class="sxs-lookup"><span data-stu-id="eb3c4-111">dbCriteriaDeleteInsert</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-112">16</span><span class="sxs-lookup"><span data-stu-id="eb3c4-112">16</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-113">对于每个已修改行都使用一对 DELETE 和 INSERT 语句。</span><span class="sxs-lookup"><span data-stu-id="eb3c4-113">Uses a pair of DELETE and INSERT statements for each modified row.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb3c4-114">dbCriteriaKey</span><span class="sxs-lookup"><span data-stu-id="eb3c4-114">dbCriteriaKey</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-115">1</span><span class="sxs-lookup"><span data-stu-id="eb3c4-115">1</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-116">仅在 where 子句中使用键列。</span><span class="sxs-lookup"><span data-stu-id="eb3c4-116">Uses just the key column(s) in the where clause.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb3c4-117">dbCriteriaModValues</span><span class="sxs-lookup"><span data-stu-id="eb3c4-117">dbCriteriaModValues</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-118">2</span><span class="sxs-lookup"><span data-stu-id="eb3c4-118">2</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-119">在 where 子句中使用键列和所有已更新列。</span><span class="sxs-lookup"><span data-stu-id="eb3c4-119">Uses the key column(s) and all updated columns in the where clause.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eb3c4-120">dbCriteriaTimestamp</span><span class="sxs-lookup"><span data-stu-id="eb3c4-120">dbCriteriaTimestamp</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-121">8</span><span class="sxs-lookup"><span data-stu-id="eb3c4-121">8</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-122">仅使用可用的时间戳列（如果结果集内没有时间戳列，将生成运行时错误）。</span><span class="sxs-lookup"><span data-stu-id="eb3c4-122">Uses just the timestamp column if available (will generate a run-time error if no timestamp column is in the result set).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eb3c4-123">将使用 dbCriteriaUpdate</span><span class="sxs-lookup"><span data-stu-id="eb3c4-123">dbCriteriaUpdate</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-124">32</span><span class="sxs-lookup"><span data-stu-id="eb3c4-124">32</span></span></p></td>
<td><p><span data-ttu-id="eb3c4-125">对于每个已修改行都使用一个 UPDATE 语句。</span><span class="sxs-lookup"><span data-stu-id="eb3c4-125">Uses an UPDATE statement for each modified row.</span></span></p></td>
</tr>
</tbody>
</table>

