---
title: Indexes.Delete Method (DAO)
TOCTitle: Delete Method
ms:assetid: 8d3c3221-3b2e-15ba-32ff-f2dfc592d82c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197351(v=office.15)
ms:contentKeyID: 48546252
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b30748c0a1388a1175512e3b8d3fd1970795b821
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466396"
---
# <a name="indexesdelete-method-dao"></a><span data-ttu-id="6e061-102">Indexes.Delete Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="6e061-102">Indexes.Delete Method (DAO)</span></span>


<span data-ttu-id="6e061-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6e061-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6e061-104">从 **Indexes** 集合中删除指定的 **Index**。</span><span class="sxs-lookup"><span data-stu-id="6e061-104">Deletes the specified **Index** from the **Indexes** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e061-105">语法</span><span class="sxs-lookup"><span data-stu-id="6e061-105">Syntax</span></span>

<span data-ttu-id="6e061-106">*表达式*。删除 （***名称***）</span><span class="sxs-lookup"><span data-stu-id="6e061-106">*expression* .Delete(***Name***)</span></span>

<span data-ttu-id="6e061-107">*表达式*一个代表**Indexes**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6e061-107">*expression* A variable that represents an **Indexes** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="6e061-108">参数</span><span class="sxs-lookup"><span data-stu-id="6e061-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6e061-109">名称</span><span class="sxs-lookup"><span data-stu-id="6e061-109">Name</span></span></p></th>
<th><p><span data-ttu-id="6e061-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="6e061-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="6e061-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="6e061-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="6e061-112">说明</span><span class="sxs-lookup"><span data-stu-id="6e061-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e061-113">名称</span><span class="sxs-lookup"><span data-stu-id="6e061-113">Name</span></span></p></td>
<td><p><span data-ttu-id="6e061-114">必需</span><span class="sxs-lookup"><span data-stu-id="6e061-114">Required</span></span></p></td>
<td><p><span data-ttu-id="6e061-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="6e061-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="6e061-116">要删除的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="6e061-116">The name of the index to delete.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="6e061-117">注解</span><span class="sxs-lookup"><span data-stu-id="6e061-117">Remarks</span></span>

<span data-ttu-id="6e061-118">仅当**Index**对象的新且未被追加到数据库时，才支持**Delete**方法。</span><span class="sxs-lookup"><span data-stu-id="6e061-118">The **Delete** method is supported only when the **Index** object is new and hasn’t been appended to the database.</span></span>

