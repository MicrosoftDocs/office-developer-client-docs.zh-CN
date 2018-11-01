---
title: CREATE VIEW 语句 (Microsoft Access SQL)
TOCTitle: CREATE VIEW statement (Microsoft Access SQL)
ms:assetid: ecaabd75-3081-fd35-830d-5a59b0a51922
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836312(v=office.15)
ms:contentKeyID: 48548519
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 5a25327aa81979a81f3410a383c06a0eda9d3113
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873738"
---
# <a name="create-view-statement-microsoft-access-sql"></a><span data-ttu-id="8680e-102">CREATE VIEW 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="8680e-102">CREATE VIEW statement (Microsoft Access SQL)</span></span>

<span data-ttu-id="8680e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8680e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8680e-104">创建新视图。</span><span class="sxs-lookup"><span data-stu-id="8680e-104">Creates a new view.</span></span>

> [!NOTE]
> <span data-ttu-id="8680e-105">[!注释] Microsoft Access 数据库引擎不支持对非 Microsoft Access 数据库引擎数据库使用 CREATE VIEW 语句或任何 DDL 语句。</span><span class="sxs-lookup"><span data-stu-id="8680e-105">The Microsoft Access database engine does not support the use of CREATE VIEW, or any of the DDL statements, with non-Microsoft Access database engine databases.</span></span>

## <a name="syntax"></a><span data-ttu-id="8680e-106">语法</span><span class="sxs-lookup"><span data-stu-id="8680e-106">Syntax</span></span>

<span data-ttu-id="8680e-107">CREATE VIEW*视图* \[(*field1*\[， *field2*\[，...\] \])\]作为*selectstatement*</span><span class="sxs-lookup"><span data-stu-id="8680e-107">CREATE VIEW *view* \[(*field1*\[, *field2*\[, …\]\])\] AS *selectstatement*</span></span>

<span data-ttu-id="8680e-108">CREATE VIEW 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="8680e-108">The CREATE VIEW statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8680e-109">部分</span><span class="sxs-lookup"><span data-stu-id="8680e-109">Part</span></span></p></th>
<th><p><span data-ttu-id="8680e-110">说明</span><span class="sxs-lookup"><span data-stu-id="8680e-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8680e-111"><em>view</em></span><span class="sxs-lookup"><span data-stu-id="8680e-111"><em>view</em></span></span></p></td>
<td><p><span data-ttu-id="8680e-112">要新建的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="8680e-112">The name of the view to be created.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8680e-113"><em>field1</em>、<em>field2</em></span><span class="sxs-lookup"><span data-stu-id="8680e-113"><em>field1</em>, <em>field2</em></span></span></p></td>
<td><p><span data-ttu-id="8680e-114"><em>selectstatement</em> 中所指定的相应字段的字段名称。</span><span class="sxs-lookup"><span data-stu-id="8680e-114">The name of field or fields for the corresponding fields specified in <em>selectstatement</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8680e-115"><em>selectstatement</em></span><span class="sxs-lookup"><span data-stu-id="8680e-115"><em>selectstatement</em></span></span></p></td>
<td><p><span data-ttu-id="8680e-116">SQL SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="8680e-116">A SQL SELECT statement.</span></span> <span data-ttu-id="8680e-117">有关详细信息，请参阅<a href="select-statement-microsoft-access-sql.md">SELECT 语句</a>。</span><span class="sxs-lookup"><span data-stu-id="8680e-117">For more information, see <a href="select-statement-microsoft-access-sql.md">SELECT statement</a>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="8680e-118">注解</span><span class="sxs-lookup"><span data-stu-id="8680e-118">Remarks</span></span>

<span data-ttu-id="8680e-119">定义视图的 SELECT 语句不能是 [SELECT INTO](select-into-statement-microsoft-access-sql.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="8680e-119">The SELECT statement that defines the view cannot be a [SELECT INTO](select-into-statement-microsoft-access-sql.md) statement.</span></span>

<span data-ttu-id="8680e-120">定义视图的 SELECT 语句不能包含任何参数。</span><span class="sxs-lookup"><span data-stu-id="8680e-120">The SELECT statement that defines the view cannot contain any parameters.</span></span>

<span data-ttu-id="8680e-121">视图的名称不能和现有表的名称相同。</span><span class="sxs-lookup"><span data-stu-id="8680e-121">The name of the view cannot be the same as the name of an existing table.</span></span>

<span data-ttu-id="8680e-122">如果可更新的 SELECT 语句定义的查询，视图还会可更新。</span><span class="sxs-lookup"><span data-stu-id="8680e-122">If the query defined by the SELECT statement is updatable, the view is also updatable.</span></span> <span data-ttu-id="8680e-123">否则，视图是只读的。</span><span class="sxs-lookup"><span data-stu-id="8680e-123">Otherwise, the view is read-only.</span></span>

<span data-ttu-id="8680e-124">如果 SELECT 语句定义的查询中有任何两个字段同名，那么视图定义必须包括一个字段列表来为查询中的每个字段指定唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="8680e-124">If any two fields in the query defined by the SELECT statement have the same name, the view definition must include a field list specifying unique names for each of the fields in the query.</span></span>

