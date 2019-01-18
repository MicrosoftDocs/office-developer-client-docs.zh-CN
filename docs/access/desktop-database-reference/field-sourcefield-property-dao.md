---
title: Field.SourceField 属性 (DAO)
TOCTitle: SourceField Property
ms:assetid: e5750d6c-4078-7bbb-9356-f9207c4e8028
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835953(v=office.15)
ms:contentKeyID: 48548360
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 249dabfa13bac6973cea4bd69e0867292c4a6967
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718208"
---
# <a name="fieldsourcefield-property-dao"></a><span data-ttu-id="4ed6e-102">Field.SourceField 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="4ed6e-102">Field.SourceField property (DAO)</span></span>


<span data-ttu-id="4ed6e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4ed6e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4ed6e-p101">返回一个值，该值指示作为 **Field** 对象的原始数据源的字段的名称。只读 **String**。</span><span class="sxs-lookup"><span data-stu-id="4ed6e-p101">Returns a value that indicates the name of the field that is the original source of the data for a **Field** object. Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="4ed6e-106">语法</span><span class="sxs-lookup"><span data-stu-id="4ed6e-106">Syntax</span></span>

<span data-ttu-id="4ed6e-107">*表达式*。SourceField</span><span class="sxs-lookup"><span data-stu-id="4ed6e-107">*expression* .SourceField</span></span>

<span data-ttu-id="4ed6e-108">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4ed6e-108">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4ed6e-109">注解</span><span class="sxs-lookup"><span data-stu-id="4ed6e-109">Remarks</span></span>

<span data-ttu-id="4ed6e-110">对于 **Field** 对象， **SourceField** 和 **SourceTable** 属性的用法取决于包含 **Field** 对象所追加到的 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="4ed6e-110">For a **Field** object, use of the **SourceField** and **SourceTable** properties depends on the object that contains the **Fields** collection that the **Field** object is appended to, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4ed6e-111">对象追加到</span><span class="sxs-lookup"><span data-stu-id="4ed6e-111">Object appended to</span></span></p></th>
<th><p><span data-ttu-id="4ed6e-112">用法</span><span class="sxs-lookup"><span data-stu-id="4ed6e-112">Usage</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ed6e-113"><strong>索引</strong></span><span class="sxs-lookup"><span data-stu-id="4ed6e-113"><strong>Index</strong></span></span></p></td>
<td><p><span data-ttu-id="4ed6e-114">不支持</span><span class="sxs-lookup"><span data-stu-id="4ed6e-114">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ed6e-115"><strong>QueryDef</strong></span><span class="sxs-lookup"><span data-stu-id="4ed6e-115"><strong>QueryDef</strong></span></span></p></td>
<td><p><span data-ttu-id="4ed6e-116">只读</span><span class="sxs-lookup"><span data-stu-id="4ed6e-116">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ed6e-117"><strong>Recordset</strong></span><span class="sxs-lookup"><span data-stu-id="4ed6e-117"><strong>Recordset</strong></span></span></p></td>
<td><p><span data-ttu-id="4ed6e-118">只读</span><span class="sxs-lookup"><span data-stu-id="4ed6e-118">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ed6e-119"><strong>Relation</strong></span><span class="sxs-lookup"><span data-stu-id="4ed6e-119"><strong>Relation</strong></span></span></p></td>
<td><p><span data-ttu-id="4ed6e-120">不支持</span><span class="sxs-lookup"><span data-stu-id="4ed6e-120">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ed6e-121"><strong>TableDef</strong></span><span class="sxs-lookup"><span data-stu-id="4ed6e-121"><strong>TableDef</strong></span></span></p></td>
<td><p><span data-ttu-id="4ed6e-122">只读</span><span class="sxs-lookup"><span data-stu-id="4ed6e-122">Read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4ed6e-p102">这些属性指示了与 **Field** 对象关联的原始字段和表名称。例如，可以使用这些属性确定查询字段（其名称与基础表中的字段名不相关）的原始数据源。</span><span class="sxs-lookup"><span data-stu-id="4ed6e-p102">These properties indicate the original field and table names associated with a **Field** object. For example, you could use these properties to determine the original source of the data in a query field whose name is unrelated to the name of the field in the underlying table.</span></span>

