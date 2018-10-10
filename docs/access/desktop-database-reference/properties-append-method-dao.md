---
title: Properties.Append Method (DAO)
TOCTitle: Append Method
ms:assetid: 47f1e24f-975c-3fdc-5c3c-8c91f2920c81
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193232(v=office.15)
ms:contentKeyID: 48544609
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6b9f9c2bdd36f1fc197a22c8866776da6aefe267
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466771"
---
# <a name="propertiesappend-method-dao"></a><span data-ttu-id="313b9-102">Properties.Append Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="313b9-102">Properties.Append Method (DAO)</span></span>


<span data-ttu-id="313b9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="313b9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="313b9-104">将新的 **Property** 添加到 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="313b9-104">Adds a new **Property** to the **Properties** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="313b9-105">语法</span><span class="sxs-lookup"><span data-stu-id="313b9-105">Syntax</span></span>

<span data-ttu-id="313b9-106">*表达式*。追加 （***对象***）</span><span class="sxs-lookup"><span data-stu-id="313b9-106">*expression* .Append(***Object***)</span></span>

<span data-ttu-id="313b9-107">*表达式*一个代表**Properties**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="313b9-107">*expression* A variable that represents a **Properties** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="313b9-108">参数</span><span class="sxs-lookup"><span data-stu-id="313b9-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="313b9-109">名称</span><span class="sxs-lookup"><span data-stu-id="313b9-109">Name</span></span></p></th>
<th><p><span data-ttu-id="313b9-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="313b9-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="313b9-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="313b9-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="313b9-112">说明</span><span class="sxs-lookup"><span data-stu-id="313b9-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="313b9-113">对象</span><span class="sxs-lookup"><span data-stu-id="313b9-113">Object</span></span></p></td>
<td><p><span data-ttu-id="313b9-114">必需</span><span class="sxs-lookup"><span data-stu-id="313b9-114">Required</span></span></p></td>
<td><p><span data-ttu-id="313b9-115"><strong>对象</strong></span><span class="sxs-lookup"><span data-stu-id="313b9-115"><strong>Object</strong></span></span></p></td>
<td><p><span data-ttu-id="313b9-116">一个对象变量，代表追加到集合的字段。</span><span class="sxs-lookup"><span data-stu-id="313b9-116">An object variable that represents the field being appended to the collection.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="313b9-117">注解</span><span class="sxs-lookup"><span data-stu-id="313b9-117">Remarks</span></span>

<span data-ttu-id="313b9-118">使用 **Delete** 方法删除追加的对象之前，该对象是存储在磁盘上的永久对象。</span><span class="sxs-lookup"><span data-stu-id="313b9-118">The appended object becomes a persistent object, stored on disk, until you delete it by using the **Delete** method.</span></span>

<span data-ttu-id="313b9-119">添加新对象会立即发生，但是，对于受数据库结构更改影响的其他任何集合，应使用 **Refresh** 方法。</span><span class="sxs-lookup"><span data-stu-id="313b9-119">The addition of a new object occurs immediately, but you should use the **Refresh** method on any other collections that may be affected by changes to the database structure.</span></span>

<span data-ttu-id="313b9-120">如果追加的对象不完整（例如，如果在将某个 **Index** 对象追加到 **Indexes** 集合之前，没有将任何 **Field** 对象追加到该对象的 **Fields** 集合），或者一个或多个从属对象中的属性集不正确，则使用 **Append** 方法会导致错误。</span><span class="sxs-lookup"><span data-stu-id="313b9-120">If the object you're appending isn't complete (such as when you haven't appended any **Field** objects to a **Fields** collection of an **Index** object before it's appended to an **Indexes** collection) or if the properties set in one or more subordinate objects are incorrect, using the **Append** method causes an error.</span></span> <span data-ttu-id="313b9-121">例如，如果没有指定字段类型，然后尝试**将 Field**对象追加到**Fields**集合中的**TableDef**对象使用**Append**方法触发一个运行时错误。</span><span class="sxs-lookup"><span data-stu-id="313b9-121">For example, if you haven’t specified a field type and then try to append the **Field** object to the **Fields** collection in a **TableDef** object, using the **Append** method triggers a run-time error.</span></span>

