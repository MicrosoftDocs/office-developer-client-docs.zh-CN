---
title: Relations.Delete 方法 (DAO)
TOCTitle: Delete Method
ms:assetid: e95408d2-9dde-44e7-875e-8f2d4b837cf6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836064(v=office.15)
ms:contentKeyID: 48548438
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e0b7fbf20a8732e8f4db525fd32bf4e5737b4d79
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716429"
---
# <a name="relationsdelete-method-dao"></a><span data-ttu-id="5cade-102">Relations.Delete 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="5cade-102">Relations.Delete method (DAO)</span></span>

<span data-ttu-id="5cade-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5cade-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="5cade-104">从 **Relations** 集合中删除指定的 **Relation**。</span><span class="sxs-lookup"><span data-stu-id="5cade-104">Deletes the specified **Relation** from the **Relations** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="5cade-105">语法</span><span class="sxs-lookup"><span data-stu-id="5cade-105">Syntax</span></span>

<span data-ttu-id="5cade-106">*表达式*。删除 （***名称***）</span><span class="sxs-lookup"><span data-stu-id="5cade-106">*expression* .Delete(***Name***)</span></span>

<span data-ttu-id="5cade-107">*表达式*一个代表**Relations**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="5cade-107">*expression* A variable that represents a **Relations** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="5cade-108">Parameters</span><span class="sxs-lookup"><span data-stu-id="5cade-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5cade-109">Name</span><span class="sxs-lookup"><span data-stu-id="5cade-109">Name</span></span></p></th>
<th><p><span data-ttu-id="5cade-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="5cade-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="5cade-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="5cade-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="5cade-112">说明</span><span class="sxs-lookup"><span data-stu-id="5cade-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cade-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="5cade-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="5cade-114">必需</span><span class="sxs-lookup"><span data-stu-id="5cade-114">Required</span></span></p></td>
<td><p><span data-ttu-id="5cade-115"><strong>String</strong></span><span class="sxs-lookup"><span data-stu-id="5cade-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="5cade-116">要删除的关系的名称。</span><span class="sxs-lookup"><span data-stu-id="5cade-116">The name of the relation to delete.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="5cade-117">注解</span><span class="sxs-lookup"><span data-stu-id="5cade-117">Remarks</span></span>

<span data-ttu-id="5cade-118">仅当 **Relation** 对象是新的未追加对象时，才支持 **Delete** 方法。</span><span class="sxs-lookup"><span data-stu-id="5cade-118">The **Delete** method is supported only when the **Relation** object is a new, unappended object.</span></span>

