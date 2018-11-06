---
title: Relations.Delete 方法 (DAO)
TOCTitle: Delete Method
ms:assetid: e95408d2-9dde-44e7-875e-8f2d4b837cf6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836064(v=office.15)
ms:contentKeyID: 48548438
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7c7a42098bcc64a58f8a004c0f1d5a35fd4f34b7
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998922"
---
# <a name="relationsdelete-method-dao"></a><span data-ttu-id="ba91e-102">Relations.Delete 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="ba91e-102">Relations.Delete method (DAO)</span></span>

<span data-ttu-id="ba91e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ba91e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ba91e-104">从 **Relations** 集合中删除指定的 **Relation**。</span><span class="sxs-lookup"><span data-stu-id="ba91e-104">Deletes the specified **Relation** from the **Relations** collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba91e-105">语法</span><span class="sxs-lookup"><span data-stu-id="ba91e-105">Syntax</span></span>

<span data-ttu-id="ba91e-106">*表达式*。删除 （***名称***）</span><span class="sxs-lookup"><span data-stu-id="ba91e-106">*expression* .Delete(***Name***)</span></span>

<span data-ttu-id="ba91e-107">*表达式*一个代表**Relations**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="ba91e-107">*expression* A variable that represents a **Relations** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="ba91e-108">参数</span><span class="sxs-lookup"><span data-stu-id="ba91e-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ba91e-109">名称</span><span class="sxs-lookup"><span data-stu-id="ba91e-109">Name</span></span></p></th>
<th><p><span data-ttu-id="ba91e-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="ba91e-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="ba91e-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="ba91e-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="ba91e-112">说明</span><span class="sxs-lookup"><span data-stu-id="ba91e-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba91e-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="ba91e-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="ba91e-114">必需</span><span class="sxs-lookup"><span data-stu-id="ba91e-114">Required</span></span></p></td>
<td><p><span data-ttu-id="ba91e-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="ba91e-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="ba91e-116">要删除的关系的名称。</span><span class="sxs-lookup"><span data-stu-id="ba91e-116">The name of the relation to delete.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="ba91e-117">注解</span><span class="sxs-lookup"><span data-stu-id="ba91e-117">Remarks</span></span>

<span data-ttu-id="ba91e-118">仅当 **Relation** 对象是新的未追加对象时，才支持 **Delete** 方法。</span><span class="sxs-lookup"><span data-stu-id="ba91e-118">The **Delete** method is supported only when the **Relation** object is a new, unappended object.</span></span>

