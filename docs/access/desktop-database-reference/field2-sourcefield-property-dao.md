---
title: Field2.SourceField 属性 (DAO)
TOCTitle: SourceField Property
ms:assetid: f89146c1-d4a4-1129-636a-c22cf7921a4e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836948(v=office.15)
ms:contentKeyID: 48548784
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1d0bedd3c1f9f2af6ccf156e1cf8c0192551f582
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717403"
---
# <a name="field2sourcefield-property-dao"></a><span data-ttu-id="c6c22-102">Field2.SourceField 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="c6c22-102">Field2.SourceField property (DAO)</span></span>


<span data-ttu-id="c6c22-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c6c22-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c6c22-p101">返回一个值，该值指示作为 **Field2** 对象的原始数据源的字段的名称。只读 **String**。</span><span class="sxs-lookup"><span data-stu-id="c6c22-p101">Returns a value that indicates the name of the field that is the original source of the data for a **Field2** object. Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6c22-106">语法</span><span class="sxs-lookup"><span data-stu-id="c6c22-106">Syntax</span></span>

<span data-ttu-id="c6c22-107">*表达式*。SourceField</span><span class="sxs-lookup"><span data-stu-id="c6c22-107">*expression* .SourceField</span></span>

<span data-ttu-id="c6c22-108">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c6c22-108">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6c22-109">注解</span><span class="sxs-lookup"><span data-stu-id="c6c22-109">Remarks</span></span>

<span data-ttu-id="c6c22-110">对于 **Field2** 对象， **SourceField** 和 **SourceTable** 属性的用法取决于包含 **Field2** 对象所追加到的 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="c6c22-110">For a **Field2** object, use of the **SourceField** and **SourceTable** properties depends on the object that contains the **Fields** collection that the **Field2** object is appended to, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c6c22-111">对象追加到</span><span class="sxs-lookup"><span data-stu-id="c6c22-111">Object appended to</span></span></p></th>
<th><p><span data-ttu-id="c6c22-112">用法</span><span class="sxs-lookup"><span data-stu-id="c6c22-112">Usage</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6c22-113"><strong>索引</strong></span><span class="sxs-lookup"><span data-stu-id="c6c22-113"><strong>Index</strong></span></span></p></td>
<td><p><span data-ttu-id="c6c22-114">不支持</span><span class="sxs-lookup"><span data-stu-id="c6c22-114">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6c22-115"><strong>QueryDef</strong></span><span class="sxs-lookup"><span data-stu-id="c6c22-115"><strong>QueryDef</strong></span></span></p></td>
<td><p><span data-ttu-id="c6c22-116">只读</span><span class="sxs-lookup"><span data-stu-id="c6c22-116">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6c22-117"><strong>Recordset</strong></span><span class="sxs-lookup"><span data-stu-id="c6c22-117"><strong>Recordset</strong></span></span></p></td>
<td><p><span data-ttu-id="c6c22-118">只读</span><span class="sxs-lookup"><span data-stu-id="c6c22-118">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6c22-119"><strong>Relation</strong></span><span class="sxs-lookup"><span data-stu-id="c6c22-119"><strong>Relation</strong></span></span></p></td>
<td><p><span data-ttu-id="c6c22-120">不支持</span><span class="sxs-lookup"><span data-stu-id="c6c22-120">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6c22-121"><strong>TableDef</strong></span><span class="sxs-lookup"><span data-stu-id="c6c22-121"><strong>TableDef</strong></span></span></p></td>
<td><p><span data-ttu-id="c6c22-122">只读</span><span class="sxs-lookup"><span data-stu-id="c6c22-122">Read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6c22-p102">这些属性指示了与 **Field2** 对象关联的原始字段和表名称。例如，可以使用这些属性确定查询字段（其名称与基础表中的字段名不相关）的原始数据源。</span><span class="sxs-lookup"><span data-stu-id="c6c22-p102">These properties indicate the original field and table names associated with a **Field2** object. For example, you could use these properties to determine the original source of the data in a query field whose name is unrelated to the name of the field in the underlying table.</span></span>

