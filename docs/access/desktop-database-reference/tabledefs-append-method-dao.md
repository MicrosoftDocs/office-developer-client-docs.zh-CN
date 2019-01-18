---
title: TableDefs.Append 方法 (DAO)
TOCTitle: Append Method
ms:assetid: f951a3c4-dade-c1ef-3bfc-6b2a60e12adc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837001(v=office.15)
ms:contentKeyID: 48548811
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 31eca3f4ca5993a401bd85a4b04299a8697c16e2
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28702787"
---
# <a name="tabledefsappend-method-dao"></a><span data-ttu-id="5120c-102">TableDefs.Append 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="5120c-102">TableDefs.Append method (DAO)</span></span>

<span data-ttu-id="5120c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5120c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="5120c-104">将新的 **TableDef** 添加到 **TableDefs** 集合。</span><span class="sxs-lookup"><span data-stu-id="5120c-104">Adds a new **TableDef** to the **TableDefs** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="5120c-105">语法</span><span class="sxs-lookup"><span data-stu-id="5120c-105">Syntax</span></span>

<span data-ttu-id="5120c-106">*表达式*。追加 （***对象***）</span><span class="sxs-lookup"><span data-stu-id="5120c-106">*expression* .Append(***Object***)</span></span>

<span data-ttu-id="5120c-107">*表达式*一个代表**TableDefs**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="5120c-107">*expression* A variable that represents a **TableDefs** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="5120c-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="5120c-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5120c-109">Name</span><span class="sxs-lookup"><span data-stu-id="5120c-109">Name</span></span></p></th>
<th><p><span data-ttu-id="5120c-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="5120c-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="5120c-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="5120c-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="5120c-112">说明</span><span class="sxs-lookup"><span data-stu-id="5120c-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5120c-113"><em>Object</em></span><span class="sxs-lookup"><span data-stu-id="5120c-113"><em>Object</em></span></span></p></td>
<td><p><span data-ttu-id="5120c-114">必需</span><span class="sxs-lookup"><span data-stu-id="5120c-114">Required</span></span></p></td>
<td><p><span data-ttu-id="5120c-115"><strong>Object</strong></span><span class="sxs-lookup"><span data-stu-id="5120c-115"><strong>Object</strong></span></span></p></td>
<td><p><span data-ttu-id="5120c-116">一个对象变量，代表追加到集合的字段。</span><span class="sxs-lookup"><span data-stu-id="5120c-116">An object variable that represents the field being appended to the collection.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="5120c-117">注解</span><span class="sxs-lookup"><span data-stu-id="5120c-117">Remarks</span></span>

<span data-ttu-id="5120c-118">使用 **Delete** 方法删除追加的对象之前，该对象是存储在磁盘上的永久对象。</span><span class="sxs-lookup"><span data-stu-id="5120c-118">The appended object becomes a persistent object, stored on disk, until you delete it by using the **Delete** method.</span></span>

<span data-ttu-id="5120c-119">添加新对象会立即发生，但是，对于受数据库结构更改影响的其他任何集合，应使用 **Refresh** 方法。</span><span class="sxs-lookup"><span data-stu-id="5120c-119">The addition of a new object occurs immediately, but you should use the **Refresh** method on any other collections that may be affected by changes to the database structure.</span></span>

<span data-ttu-id="5120c-120">如果追加的对象不完整（例如，如果在将某个 **Index** 对象追加到 **Indexes** 集合之前，没有将任何 **Field** 对象追加到该对象的 **Fields** 集合），或者一个或多个从属对象中的属性集不正确，则使用 **Append** 方法会导致错误。</span><span class="sxs-lookup"><span data-stu-id="5120c-120">If the object you're appending isn't complete (such as when you haven't appended any **Field** objects to a **Fields** collection of an **Index** object before it's appended to an **Indexes** collection) or if the properties set in one or more subordinate objects are incorrect, using the **Append** method causes an error.</span></span> <span data-ttu-id="5120c-121">例如，如果没有指定字段类型，然后尝试**将 Field**对象追加到**Fields**集合中的**TableDef**对象使用**Append**方法触发一个运行时错误。</span><span class="sxs-lookup"><span data-stu-id="5120c-121">For example, if you haven’t specified a field type and then try to append the **Field** object to the **Fields** collection in a **TableDef** object, using the **Append** method triggers a run-time error.</span></span>

