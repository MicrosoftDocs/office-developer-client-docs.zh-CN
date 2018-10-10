---
title: Relations.Append Method (DAO)
TOCTitle: Append Method
ms:assetid: dafcc7b8-b30d-2ba2-631d-eca0f882fc2d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835334(v=office.15)
ms:contentKeyID: 48548094
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052904
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 51f365ef783fb874b269ac0490b08687ce127475
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467065"
---
# <a name="relationsappend-method-dao"></a><span data-ttu-id="68c28-102">Relations.Append Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="68c28-102">Relations.Append Method (DAO)</span></span>


<span data-ttu-id="68c28-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="68c28-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="68c28-104">将新的 **Relation** 添加到 **Relations** 集合。</span><span class="sxs-lookup"><span data-stu-id="68c28-104">Adds a new **Relation** to the **Relations** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="68c28-105">语法</span><span class="sxs-lookup"><span data-stu-id="68c28-105">Syntax</span></span>

<span data-ttu-id="68c28-106">*表达式*。追加 （***对象***）</span><span class="sxs-lookup"><span data-stu-id="68c28-106">*expression* .Append(***Object***)</span></span>

<span data-ttu-id="68c28-107">*表达式*一个代表**Relations**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="68c28-107">*expression* A variable that represents a **Relations** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="68c28-108">参数</span><span class="sxs-lookup"><span data-stu-id="68c28-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="68c28-109">名称</span><span class="sxs-lookup"><span data-stu-id="68c28-109">Name</span></span></p></th>
<th><p><span data-ttu-id="68c28-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="68c28-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="68c28-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="68c28-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="68c28-112">说明</span><span class="sxs-lookup"><span data-stu-id="68c28-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68c28-113">对象</span><span class="sxs-lookup"><span data-stu-id="68c28-113">Object</span></span></p></td>
<td><p><span data-ttu-id="68c28-114">必需</span><span class="sxs-lookup"><span data-stu-id="68c28-114">Required</span></span></p></td>
<td><p><span data-ttu-id="68c28-115"><strong>对象</strong></span><span class="sxs-lookup"><span data-stu-id="68c28-115"><strong>Object</strong></span></span></p></td>
<td><p><span data-ttu-id="68c28-116">一个对象变量，代表追加到集合的字段。</span><span class="sxs-lookup"><span data-stu-id="68c28-116">An object variable that represents the field being appended to the collection.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="68c28-117">注解</span><span class="sxs-lookup"><span data-stu-id="68c28-117">Remarks</span></span>

<span data-ttu-id="68c28-118">使用 **Delete** 方法删除追加的对象之前，该对象是存储在磁盘上的永久对象。</span><span class="sxs-lookup"><span data-stu-id="68c28-118">The appended object becomes a persistent object, stored on disk, until you delete it by using the **Delete** method.</span></span>

<span data-ttu-id="68c28-119">添加新对象会立即发生，但是，对于受数据库结构更改影响的其他任何集合，应使用 **Refresh** 方法。</span><span class="sxs-lookup"><span data-stu-id="68c28-119">The addition of a new object occurs immediately, but you should use the **Refresh** method on any other collections that may be affected by changes to the database structure.</span></span>

<span data-ttu-id="68c28-120">如果追加的对象不完整（例如，如果在将某个 **Index** 对象追加到 **Indexes** 集合之前，没有将任何 **Field** 对象追加到该对象的 **Fields** 集合），或者一个或多个从属对象中的属性集不正确，则使用 **Append** 方法会导致错误。</span><span class="sxs-lookup"><span data-stu-id="68c28-120">If the object you're appending isn't complete (such as when you haven't appended any **Field** objects to a **Fields** collection of an **Index** object before it's appended to an **Indexes** collection) or if the properties set in one or more subordinate objects are incorrect, using the **Append** method causes an error.</span></span> <span data-ttu-id="68c28-121">例如，如果没有指定字段类型，然后尝试**将 Field**对象追加到**Fields**集合中的**TableDef**对象使用**Append**方法触发一个运行时错误。</span><span class="sxs-lookup"><span data-stu-id="68c28-121">For example, if you haven’t specified a field type and then try to append the **Field** object to the **Fields** collection in a **TableDef** object, using the **Append** method triggers a run-time error.</span></span>

