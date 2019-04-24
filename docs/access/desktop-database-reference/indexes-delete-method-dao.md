---
title: '索引: Delete 方法 (DAO)'
TOCTitle: Delete Method
ms:assetid: 8d3c3221-3b2e-15ba-32ff-f2dfc592d82c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197351(v=office.15)
ms:contentKeyID: 48546252
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6ab52f353b7a3e636f64ff2ad6ad5354d62bed48
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291550"
---
# <a name="indexesdelete-method-dao"></a><span data-ttu-id="99fac-102">索引: Delete 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="99fac-102">Indexes.Delete method (DAO)</span></span>

<span data-ttu-id="99fac-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="99fac-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="99fac-104">从 **Indexes** 集合中删除指定的 **Index**。</span><span class="sxs-lookup"><span data-stu-id="99fac-104">Deletes the specified **Index** from the **Indexes** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="99fac-105">语法</span><span class="sxs-lookup"><span data-stu-id="99fac-105">Syntax</span></span>

<span data-ttu-id="99fac-106">*表达式*。Delete (***Name***)</span><span class="sxs-lookup"><span data-stu-id="99fac-106">*expression* .Delete(***Name***)</span></span>

<span data-ttu-id="99fac-107">*表达式*一个代表**索引**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="99fac-107">*expression* A variable that represents an **Indexes** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="99fac-108">参数</span><span class="sxs-lookup"><span data-stu-id="99fac-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="99fac-109">名称</span><span class="sxs-lookup"><span data-stu-id="99fac-109">Name</span></span></p></th>
<th><p><span data-ttu-id="99fac-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="99fac-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="99fac-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="99fac-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="99fac-112">说明</span><span class="sxs-lookup"><span data-stu-id="99fac-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99fac-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="99fac-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="99fac-114">必需</span><span class="sxs-lookup"><span data-stu-id="99fac-114">Required</span></span></p></td>
<td><p><span data-ttu-id="99fac-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="99fac-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="99fac-116">要删除的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="99fac-116">The name of the index to delete.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="99fac-117">注解</span><span class="sxs-lookup"><span data-stu-id="99fac-117">Remarks</span></span>

<span data-ttu-id="99fac-118">仅当 **Index** 是新的，并且未追加到数据库时，才支持 **Delete** 方法。</span><span class="sxs-lookup"><span data-stu-id="99fac-118">The **Delete** method is supported only when the **Index** object is new and hasn’t been appended to the database.</span></span>

