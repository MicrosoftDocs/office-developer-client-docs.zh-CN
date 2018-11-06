---
title: Indexes.Delete 方法 (DAO)
TOCTitle: Delete Method
ms:assetid: 8d3c3221-3b2e-15ba-32ff-f2dfc592d82c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197351(v=office.15)
ms:contentKeyID: 48546252
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0c725919b6509b5c802502fc8280823c407516f6
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998824"
---
# <a name="indexesdelete-method-dao"></a><span data-ttu-id="072ff-102">Indexes.Delete 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="072ff-102">Indexes.Delete method (DAO)</span></span>

<span data-ttu-id="072ff-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="072ff-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="072ff-104">从 **Indexes** 集合中删除指定的 **Index**。</span><span class="sxs-lookup"><span data-stu-id="072ff-104">Deletes the specified **Index** from the **Indexes** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="072ff-105">语法</span><span class="sxs-lookup"><span data-stu-id="072ff-105">Syntax</span></span>

<span data-ttu-id="072ff-106">*表达式*。删除 （***名称***）</span><span class="sxs-lookup"><span data-stu-id="072ff-106">*expression* .Delete(***Name***)</span></span>

<span data-ttu-id="072ff-107">*表达式*一个代表**Indexes**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="072ff-107">*expression* A variable that represents an **Indexes** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="072ff-108">参数</span><span class="sxs-lookup"><span data-stu-id="072ff-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="072ff-109">名称</span><span class="sxs-lookup"><span data-stu-id="072ff-109">Name</span></span></p></th>
<th><p><span data-ttu-id="072ff-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="072ff-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="072ff-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="072ff-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="072ff-112">说明</span><span class="sxs-lookup"><span data-stu-id="072ff-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="072ff-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="072ff-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="072ff-114">必需</span><span class="sxs-lookup"><span data-stu-id="072ff-114">Required</span></span></p></td>
<td><p><span data-ttu-id="072ff-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="072ff-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="072ff-116">要删除的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="072ff-116">The name of the index to delete.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="072ff-117">注解</span><span class="sxs-lookup"><span data-stu-id="072ff-117">Remarks</span></span>

<span data-ttu-id="072ff-118">仅当**Index**对象的新且未被追加到数据库时，才支持**Delete**方法。</span><span class="sxs-lookup"><span data-stu-id="072ff-118">The **Delete** method is supported only when the **Index** object is new and hasn’t been appended to the database.</span></span>

