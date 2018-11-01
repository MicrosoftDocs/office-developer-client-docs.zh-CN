---
title: Relations.Delete Method (DAO)
TOCTitle: Delete Method
ms:assetid: e95408d2-9dde-44e7-875e-8f2d4b837cf6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836064(v=office.15)
ms:contentKeyID: 48548438
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1a7ad2345e547232b79085ec5942ce5ca7d8b5c8
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870021"
---
# <a name="relationsdelete-method-dao"></a><span data-ttu-id="0c17b-102">Relations.Delete Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="0c17b-102">Relations.Delete Method (DAO)</span></span>


<span data-ttu-id="0c17b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0c17b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0c17b-104">从 **Relations** 集合中删除指定的 **Relation**。</span><span class="sxs-lookup"><span data-stu-id="0c17b-104">Deletes the specified **Relation** from the **Relations** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="0c17b-105">语法</span><span class="sxs-lookup"><span data-stu-id="0c17b-105">Syntax</span></span>

<span data-ttu-id="0c17b-106">*表达式*。删除 （***名称***）</span><span class="sxs-lookup"><span data-stu-id="0c17b-106">*expression* .Delete(***Name***)</span></span>

<span data-ttu-id="0c17b-107">*表达式*一个代表**Relations**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="0c17b-107">*expression* A variable that represents a **Relations** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="0c17b-108">参数</span><span class="sxs-lookup"><span data-stu-id="0c17b-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0c17b-109">名称</span><span class="sxs-lookup"><span data-stu-id="0c17b-109">Name</span></span></p></th>
<th><p><span data-ttu-id="0c17b-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="0c17b-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="0c17b-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="0c17b-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="0c17b-112">说明</span><span class="sxs-lookup"><span data-stu-id="0c17b-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c17b-113">名称</span><span class="sxs-lookup"><span data-stu-id="0c17b-113">Name</span></span></p></td>
<td><p><span data-ttu-id="0c17b-114">必需</span><span class="sxs-lookup"><span data-stu-id="0c17b-114">Required</span></span></p></td>
<td><p><span data-ttu-id="0c17b-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="0c17b-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="0c17b-116">要删除的关系的名称。</span><span class="sxs-lookup"><span data-stu-id="0c17b-116">The name of the relation to delete.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="0c17b-117">注解</span><span class="sxs-lookup"><span data-stu-id="0c17b-117">Remarks</span></span>

<span data-ttu-id="0c17b-118">仅当 **Relation** 对象是新的未追加对象时，才支持 **Delete** 方法。</span><span class="sxs-lookup"><span data-stu-id="0c17b-118">The **Delete** method is supported only when the **Relation** object is a new, unappended object.</span></span>

