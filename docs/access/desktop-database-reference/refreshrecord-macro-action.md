---
title: RefreshRecord 宏操作
TOCTitle: RefreshRecord Macro Action
ms:assetid: 68c90d7d-f59c-9e83-bc30-8f37cf5a3696
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195261(v=office.15)
ms:contentKeyID: 48545396
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm62122
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 91c49ca4d453418a02d55163a023e853fadd5773
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467003"
---
# <a name="refreshrecord-macro-action"></a><span data-ttu-id="c81db-102">RefreshRecord 宏操作</span><span class="sxs-lookup"><span data-stu-id="c81db-102">RefreshRecord Macro Action</span></span>


<span data-ttu-id="c81db-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c81db-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c81db-104">您可以使用 **RefreshRecord** 操作更新活动窗体或数据表的基础记录源，以反映对当前集合中的记录所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c81db-104">You can use the **RefreshRecord** action to update the underlying record source for the active form or datasheet to reflect changes made to the records in the current set.</span></span>

## <a name="remarks"></a><span data-ttu-id="c81db-105">注释</span><span class="sxs-lookup"><span data-stu-id="c81db-105">Remarks</span></span>

<span data-ttu-id="c81db-p101">**RefreshRecord** 操作只显示对当前集合中的记录所做的更改。由于 **RefreshRecord** 操作实际上并不再次查询数据库，因此当前集合将不包括自上次再次查询数据库以来添加的记录，也不排除这段时间内删除的记录；当前集合也不排除不再满足查询或筛选条件的记录。若要再次查询数据库，请使用 **[Requery](requery-macro-action.md)** 方法。再次查询窗体的记录源时，当前记录集将准确反映该记录源中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="c81db-p101">the **RefreshRecord** action shows only changes made to records in the current set. Because the **RefreshRecord** action does not actually requery the database, the current set will not include records that have been added or exclude records that have been deleted since the database was last requeried; Nor will it exclude records that no longer satisfy the criteria of the query or filter. To requery the database, use the **[Requery](requery-macro-action.md)** method. When the record source for a form is requeried, the current set of records will accurately reflect all data in the record source.</span></span>

<span data-ttu-id="c81db-110">此宏操作的行为取决于您在客户端数据库还是在 Web 数据库中调用该操作。</span><span class="sxs-lookup"><span data-stu-id="c81db-110">The behavior of this macro action depends on whether you are calling it in a client database or a web database.</span></span>

## <a name="client-database"></a><span data-ttu-id="c81db-111">客户端数据库</span><span class="sxs-lookup"><span data-stu-id="c81db-111">Client database</span></span>

<span data-ttu-id="c81db-p102">在客户端数据库中，您可以使用 **RefreshRecord** 操作更新活动窗体或数据表的基础记录源，以反映对当前集合中的数据所做的更改。这些更改包括当前用户或多用户环境中的其他用户所做的更改。该操作与 **[Refresh](https://msdn.microsoft.com/library/ff836021\(v=office.15\))** 方法等效。</span><span class="sxs-lookup"><span data-stu-id="c81db-p102">In a client database, you can use the **RefreshRecord** action to update the underlying record source for the active form or datasheet to reflect changes made to the data in the current set. Changes include those made by the current user or by other users in a multiuser environment. It is equivalent to the **[Refresh](https://msdn.microsoft.com/library/ff836021\(v=office.15\))** method.</span></span>

<span data-ttu-id="c81db-115">**RefreshRecord** 宏操作可在客户端数据库中执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c81db-115">The **RefreshRecord** macro action does the following in a client database:</span></span>

1.  <span data-ttu-id="c81db-p103">更新活动窗体或数据表的记录源，以反映对当前集合中的行所做的更改。对于 ODBC 链接表，则从数据源中检索对当前集合中的记录所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c81db-p103">Updates the record source for the active form or datasheet to reflect the changes made to rows in the current set. For ODBC linked tables, retrieves changes to records in the current set from the data source.</span></span>

2.  <span data-ttu-id="c81db-118">更新当前集合，以反映更改。</span><span class="sxs-lookup"><span data-stu-id="c81db-118">Updates the current set to reflect the changes.</span></span> <span data-ttu-id="c81db-119">如果已被删除的记录源中的行，则会更改显示\#已删除。</span><span class="sxs-lookup"><span data-stu-id="c81db-119">If a row in the record source has been deleted, it is changed to show \#Deleted.</span></span>

3.  <span data-ttu-id="c81db-120">刷新活动或数据表，以显示任何更改的记录和任何\#已删除的记录，当前集合中的。</span><span class="sxs-lookup"><span data-stu-id="c81db-120">Refreshes the active or datasheet to display any changed records and any \#Deleted records, in the current set.</span></span>

4.  <span data-ttu-id="c81db-121">再次查询活动窗体或数据表上的任何子窗体和子报表。</span><span class="sxs-lookup"><span data-stu-id="c81db-121">Requeries any subforms and subreports on the active form or datasheet.</span></span>

## <a name="web-database"></a><span data-ttu-id="c81db-122">Web 数据库</span><span class="sxs-lookup"><span data-stu-id="c81db-122">Web database</span></span>

<span data-ttu-id="c81db-p105">在 Web 数据库中，您可以使用 **RefreshRecord** 操作更新活动窗体或数据表的基础记录源，以反映对当前集合中的记录所做的更改。这些更改包括当前用户或其他用户所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c81db-p105">In a web database, you can use the **RefreshRecord** action to update the underlying record source for the active form or datasheet to reflect changes made to the records in the current set. Changes include those made by the current user or other users.</span></span>

<span data-ttu-id="c81db-125">**RefreshRecord** 宏操作可在 Web 数据库中执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c81db-125">The **RefreshRecord** macro action does the following in a web database:</span></span>

1.  <span data-ttu-id="c81db-p106">从服务器中检索对当前集合中的任何基表的更改。对于 ODBC 链接表，则从数据源中检索对当前集合中的记录所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c81db-p106">Retrieves changes from the server for any base tables in the current set. For ODBC linked tables, retrieves changes to records in the current set from the data source.</span></span>

2.  <span data-ttu-id="c81db-128">更新当前集合，以反映更改。</span><span class="sxs-lookup"><span data-stu-id="c81db-128">Updates the current set to reflect the changes.</span></span> <span data-ttu-id="c81db-129">如果当前集合中的该行已被删除，则会更改显示\#已删除。</span><span class="sxs-lookup"><span data-stu-id="c81db-129">If a row in the current set has been deleted, it is changed to show \#Deleted.</span></span>

3.  <span data-ttu-id="c81db-130">刷新活动窗体或数据表，以显示任何更改的记录和任何\#已删除的记录，当前集合中的。</span><span class="sxs-lookup"><span data-stu-id="c81db-130">Refreshes the active form or datasheet to display any changed records and any \#Deleted records, in the current set.</span></span>

4.  <span data-ttu-id="c81db-131">再次查询活动窗体或数据表上的任何子窗体和子报表。</span><span class="sxs-lookup"><span data-stu-id="c81db-131">Requeries any subforms and subreports on the active form or datasheet.</span></span>

