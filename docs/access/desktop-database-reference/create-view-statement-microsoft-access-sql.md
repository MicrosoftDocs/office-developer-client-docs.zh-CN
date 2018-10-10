---
title: CREATE VIEW 语句 (Microsoft Access SQL)
TOCTitle: CREATE VIEW Statement (Microsoft Access SQL)
ms:assetid: ecaabd75-3081-fd35-830d-5a59b0a51922
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836312(v=office.15)
ms:contentKeyID: 48548519
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 292dddeab15c71fb188a928ac0e491063930214d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466688"
---
# <a name="create-view-statement-microsoft-access-sql"></a><span data-ttu-id="effe4-102">CREATE VIEW 语句 (Microsoft Access SQL)</span><span class="sxs-lookup"><span data-stu-id="effe4-102">CREATE VIEW Statement (Microsoft Access SQL)</span></span>


<span data-ttu-id="effe4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="effe4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="effe4-104">创建新视图。</span><span class="sxs-lookup"><span data-stu-id="effe4-104">Creates a new view.</span></span>


> [!NOTE]
> <P><span data-ttu-id="effe4-105">[!注释] Microsoft Access 数据库引擎不支持对非 Microsoft Access 数据库引擎数据库使用 CREATE VIEW 语句或任何 DDL 语句。</span><span class="sxs-lookup"><span data-stu-id="effe4-105">The Microsoft Access database engine does not support the use of CREATE VIEW, or any of the DDL statements, with non-Microsoft Access database engine databases.</span></span></P>



## <a name="syntax"></a><span data-ttu-id="effe4-106">语法</span><span class="sxs-lookup"><span data-stu-id="effe4-106">Syntax</span></span>

<span data-ttu-id="effe4-107">CREATE VIEW*视图* \[(*field1*\[， *field2*\[，...\] \])\]作为*selectstatement*</span><span class="sxs-lookup"><span data-stu-id="effe4-107">CREATE VIEW *view* \[(*field1*\[, *field2*\[, …\]\])\] AS *selectstatement*</span></span>

<span data-ttu-id="effe4-108">CREATE VIEW 语句包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="effe4-108">The CREATE VIEW statement has these parts:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="effe4-109">部分</span><span class="sxs-lookup"><span data-stu-id="effe4-109">Part</span></span></p></th>
<th><p><span data-ttu-id="effe4-110">说明</span><span class="sxs-lookup"><span data-stu-id="effe4-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="effe4-111"><em>view</em></span><span class="sxs-lookup"><span data-stu-id="effe4-111"><em>view</em></span></span></p></td>
<td><p><span data-ttu-id="effe4-112">要新建的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="effe4-112">The name of the view to be created.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="effe4-113"><em>field1</em>、<em>field2</em></span><span class="sxs-lookup"><span data-stu-id="effe4-113"><em>field1</em>, <em>field2</em></span></span></p></td>
<td><p><span data-ttu-id="effe4-114"><em>selectstatement</em> 中所指定的相应字段的字段名称。</span><span class="sxs-lookup"><span data-stu-id="effe4-114">The name of field or fields for the corresponding fields specified in <em>selectstatement</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="effe4-115"><em>selectstatement</em></span><span class="sxs-lookup"><span data-stu-id="effe4-115"><em>selectstatement</em></span></span></p></td>
<td><p><span data-ttu-id="effe4-p101">SQL SELECT 语句。有关详细信息，请参阅 <a href="select-statement-microsoft-access-sql.md">SELECT 语句</a>。</span><span class="sxs-lookup"><span data-stu-id="effe4-p101">A SQL SELECT statement. For more information, see <a href="select-statement-microsoft-access-sql.md">SELECT Statement</a>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="effe4-118">注解</span><span class="sxs-lookup"><span data-stu-id="effe4-118">Remarks</span></span>

<span data-ttu-id="effe4-119">定义视图的 SELECT 语句不能是 [SELECT INTO](select-into-statement-microsoft-access-sql.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="effe4-119">The SELECT statement that defines the view cannot be a [SELECT INTO](select-into-statement-microsoft-access-sql.md) statement.</span></span>

<span data-ttu-id="effe4-120">定义视图的 SELECT 语句不能包含任何参数。</span><span class="sxs-lookup"><span data-stu-id="effe4-120">The SELECT statement that defines the view cannot contain any parameters.</span></span>

<span data-ttu-id="effe4-121">视图的名称不能和现有表的名称相同。</span><span class="sxs-lookup"><span data-stu-id="effe4-121">The name of the view cannot be the same as the name of an existing table.</span></span>

<span data-ttu-id="effe4-p102">如果 SELECT 语句所定义的查询是可更新的，那么视图也是可更新的。否则，视图是只读的。</span><span class="sxs-lookup"><span data-stu-id="effe4-p102">If the query defined by the SELECT statement is updatable, then the view is also updatable. Otherwise, the view is read-only.</span></span>

<span data-ttu-id="effe4-124">如果 SELECT 语句定义的查询中有任何两个字段同名，那么视图定义必须包括一个字段列表来为查询中的每个字段指定唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="effe4-124">If any two fields in the query defined by the SELECT statement have the same name, the view definition must include a field list specifying unique names for each of the fields in the query.</span></span>

