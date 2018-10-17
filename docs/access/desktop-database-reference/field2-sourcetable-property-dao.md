---
title: Field2.SourceTable Property (DAO)
TOCTitle: SourceTable Property
ms:assetid: 24d2fdda-d924-d95e-8458-063dd1d36d5d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191839(v=office.15)
ms:contentKeyID: 48543768
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: af404f3b741445ef434c4f3266f89aa318e13ad2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467069"
---
# <a name="field2sourcetable-property-dao"></a><span data-ttu-id="6c2df-102">Field2.SourceTable Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="6c2df-102">Field2.SourceTable Property (DAO)</span></span>


<span data-ttu-id="6c2df-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6c2df-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6c2df-p101">返回一个值，该值指示作为 **Field2** 对象的原始数据源的表的名称。只读 **String**。</span><span class="sxs-lookup"><span data-stu-id="6c2df-p101">Returns a value that indicates the name of the table that is the original source of the data for a **Field2** object. Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c2df-106">语法</span><span class="sxs-lookup"><span data-stu-id="6c2df-106">Syntax</span></span>

<span data-ttu-id="6c2df-107">*表达式*。SourceTable</span><span class="sxs-lookup"><span data-stu-id="6c2df-107">*expression* .SourceTable</span></span>

<span data-ttu-id="6c2df-108">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6c2df-108">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c2df-109">注解</span><span class="sxs-lookup"><span data-stu-id="6c2df-109">Remarks</span></span>

<span data-ttu-id="6c2df-110">对于 **Field2** 对象， **SourceField** 和 **SourceTable** 属性的用法取决于包含 **Field2** 对象所追加到的 **Fields** 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="6c2df-110">For a **Field2** object, use of the **SourceField** and **SourceTable** properties depends on the object that contains the **Fields** collection that the **Field2** object is appended to, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6c2df-111">对象追加到</span><span class="sxs-lookup"><span data-stu-id="6c2df-111">Object appended to</span></span></p></th>
<th><p><span data-ttu-id="6c2df-112">用法</span><span class="sxs-lookup"><span data-stu-id="6c2df-112">Usage</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6c2df-113"><strong>Index</strong></span><span class="sxs-lookup"><span data-stu-id="6c2df-113"><strong>Index</strong></span></span></p></td>
<td><p><span data-ttu-id="6c2df-114">不支持</span><span class="sxs-lookup"><span data-stu-id="6c2df-114">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c2df-115"><strong>QueryDef</strong></span><span class="sxs-lookup"><span data-stu-id="6c2df-115"><strong>QueryDef</strong></span></span></p></td>
<td><p><span data-ttu-id="6c2df-116">只读</span><span class="sxs-lookup"><span data-stu-id="6c2df-116">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c2df-117"><strong>Recordset</strong></span><span class="sxs-lookup"><span data-stu-id="6c2df-117"><strong>Recordset</strong></span></span></p></td>
<td><p><span data-ttu-id="6c2df-118">只读</span><span class="sxs-lookup"><span data-stu-id="6c2df-118">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6c2df-119"><strong>Relation</strong></span><span class="sxs-lookup"><span data-stu-id="6c2df-119"><strong>Relation</strong></span></span></p></td>
<td><p><span data-ttu-id="6c2df-120">不支持</span><span class="sxs-lookup"><span data-stu-id="6c2df-120">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6c2df-121"><strong>TableDef</strong></span><span class="sxs-lookup"><span data-stu-id="6c2df-121"><strong>TableDef</strong></span></span></p></td>
<td><p><span data-ttu-id="6c2df-122">只读</span><span class="sxs-lookup"><span data-stu-id="6c2df-122">Read-only</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6c2df-p102">这些属性指示了与 **Field2** 对象关联的原始字段和表名称。例如，可以使用这些属性确定查询字段（其名称与基础表中的字段名不相关）的原始数据源。</span><span class="sxs-lookup"><span data-stu-id="6c2df-p102">These properties indicate the original field and table names associated with a **Field2** object. For example, you could use these properties to determine the original source of the data in a query field whose name is unrelated to the name of the field in the underlying table.</span></span>


> [!NOTE]
> <P><span data-ttu-id="6c2df-125">[!注释] 如果将 <STRONG>SourceTable</STRONG> 属性用于表类型 <STRONG>Recordset</STRONG> 对象的 <STRONG>Fields</STRONG> 集合中的 <STRONG>Field2</STRONG> 对象，则该属性不会返回有意义的表名。</span><span class="sxs-lookup"><span data-stu-id="6c2df-125">The <STRONG>SourceTable</STRONG> property will not return a meaningful table name if used on a <STRONG>Field2</STRONG> object in the <STRONG>Fields</STRONG> collection of a table-type <STRONG>Recordset</STRONG> object.</span></span></P>

