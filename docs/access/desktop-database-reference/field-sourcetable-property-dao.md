---
title: SourceTable 属性 (DAO)
TOCTitle: SourceTable Property
ms:assetid: 9564ea1c-eafd-0b72-fd68-d88fcc3ea189
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197694(v=office.15)
ms:contentKeyID: 48546429
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052900
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: a557a4941f5b4aa511489c5d057871df5fa72c08
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292984"
---
# <a name="fieldsourcetable-property-dao"></a><span data-ttu-id="2b128-102">SourceTable 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="2b128-102">Field.SourceTable property (DAO)</span></span>


<span data-ttu-id="2b128-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="2b128-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2b128-p101">返回一个值，该值指示作为 **Field** 对象的原始数据源的表的名称。只读 **String**。</span><span class="sxs-lookup"><span data-stu-id="2b128-p101">Returns a value that indicates the name of the table that is the original source of the data for a **Field** object. Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="2b128-106">语法</span><span class="sxs-lookup"><span data-stu-id="2b128-106">Syntax</span></span>

<span data-ttu-id="2b128-107">*表达式*。SourceTable</span><span class="sxs-lookup"><span data-stu-id="2b128-107">*expression* .SourceTable</span></span>

<span data-ttu-id="2b128-108">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="2b128-108">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b128-109">注解</span><span class="sxs-lookup"><span data-stu-id="2b128-109">Remarks</span></span>

<span data-ttu-id="2b128-110">对于 **Field** 对象， **SourceField** 和 **SourceTable** 属性的用法取决于包含 **Field** 对象所追加到的 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="2b128-110">For a **Field** object, use of the **SourceField** and **SourceTable** properties depends on the object that contains the **Fields** collection that the **Field** object is appended to, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2b128-111">对象追加到</span><span class="sxs-lookup"><span data-stu-id="2b128-111">Object appended to</span></span></p></th>
<th><p><span data-ttu-id="2b128-112">用法</span><span class="sxs-lookup"><span data-stu-id="2b128-112">Usage</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b128-113"><strong>索引</strong></span><span class="sxs-lookup"><span data-stu-id="2b128-113"><strong>Index</strong></span></span></p></td>
<td><p><span data-ttu-id="2b128-114">不支持</span><span class="sxs-lookup"><span data-stu-id="2b128-114">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b128-115"><strong>QueryDef</strong></span><span class="sxs-lookup"><span data-stu-id="2b128-115"><strong>QueryDef</strong></span></span></p></td>
<td><p><span data-ttu-id="2b128-116">只读</span><span class="sxs-lookup"><span data-stu-id="2b128-116">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b128-117"><strong>Recordset</strong></span><span class="sxs-lookup"><span data-stu-id="2b128-117"><strong>Recordset</strong></span></span></p></td>
<td><p><span data-ttu-id="2b128-118">只读</span><span class="sxs-lookup"><span data-stu-id="2b128-118">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b128-119"><strong>Relation</strong></span><span class="sxs-lookup"><span data-stu-id="2b128-119"><strong>Relation</strong></span></span></p></td>
<td><p><span data-ttu-id="2b128-120">不受支持</span><span class="sxs-lookup"><span data-stu-id="2b128-120">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b128-121"><strong>TableDef</strong></span><span class="sxs-lookup"><span data-stu-id="2b128-121"><strong>TableDef</strong></span></span></p></td>
<td><p><span data-ttu-id="2b128-122">只读</span><span class="sxs-lookup"><span data-stu-id="2b128-122">Read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2b128-p102">这些属性指示了与 **Field** 对象关联的原始字段和表名称。例如，可以使用这些属性确定查询字段（其名称与基础表中的字段名不相关）的原始数据源。</span><span class="sxs-lookup"><span data-stu-id="2b128-p102">These properties indicate the original field and table names associated with a **Field** object. For example, you could use these properties to determine the original source of the data in a query field whose name is unrelated to the name of the field in the underlying table.</span></span>


> [!NOTE]
> <span data-ttu-id="2b128-125">[!注释] 如果将 **SourceTable** 属性用于表类型 **Recordset** 对象的 **Fields** 集合中的 **Field** 对象，则该属性不会返回有意义的表名。</span><span class="sxs-lookup"><span data-stu-id="2b128-125">The **SourceTable** property will not return a meaningful table name if used on a **Field** object in the **Fields** collection of a table-type **Recordset** object.</span></span>


