---
title: RefreshRecord 宏操作
TOCTitle: RefreshRecord macro action
ms:assetid: 68c90d7d-f59c-9e83-bc30-8f37cf5a3696
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195261(v=office.15)
ms:contentKeyID: 48545396
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm62122
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: d8682c19686650ab193536658c6b56961f289174
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307072"
---
# <a name="refreshrecord-macro-action"></a><span data-ttu-id="a6146-102">RefreshRecord 宏操作</span><span class="sxs-lookup"><span data-stu-id="a6146-102">RefreshRecord macro action</span></span>


<span data-ttu-id="a6146-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="a6146-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a6146-104">您可以使用 **RefreshRecord** 操作更新活动窗体或数据表的基础记录源，以反映对当前集合中的记录所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a6146-104">You can use the **RefreshRecord** action to update the underlying record source for the active form or datasheet to reflect changes made to the records in the current set.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6146-105">注解</span><span class="sxs-lookup"><span data-stu-id="a6146-105">Remarks</span></span>

<span data-ttu-id="a6146-p101">**RefreshRecord** 操作只显示对当前集合中的记录所做的更改。由于 **RefreshRecord** 操作实际上并不再次查询数据库，因此当前集合将不包括自上次再次查询数据库以来添加的记录，也不排除这段时间内删除的记录；当前集合也不排除不再满足查询或筛选条件的记录。若要再次查询数据库，请使用 **[Requery](requery-macro-action.md)** 方法。再次查询窗体的记录源时，当前记录集将准确反映该记录源中的所有数据。</span><span class="sxs-lookup"><span data-stu-id="a6146-p101">the **RefreshRecord** action shows only changes made to records in the current set. Because the **RefreshRecord** action does not actually requery the database, the current set will not include records that have been added or exclude records that have been deleted since the database was last requeried; Nor will it exclude records that no longer satisfy the criteria of the query or filter. To requery the database, use the **[Requery](requery-macro-action.md)** method. When the record source for a form is requeried, the current set of records will accurately reflect all data in the record source.</span></span>

<span data-ttu-id="a6146-110">此宏操作的行为取决于您在客户端数据库还是在 Web 数据库中调用该操作。</span><span class="sxs-lookup"><span data-stu-id="a6146-110">The behavior of this macro action depends on whether you are calling it in a client database or a web database.</span></span>

## <a name="client-database"></a><span data-ttu-id="a6146-111">客户端数据库</span><span class="sxs-lookup"><span data-stu-id="a6146-111">Client database</span></span>

<span data-ttu-id="a6146-p102">在客户端数据库中，您可以使用 **RefreshRecord** 操作更新活动窗体或数据表的基础记录源，以反映对当前集合中的数据所做的更改。这些更改包括当前用户或多用户环境中的其他用户所做的更改。该操作与 **[Refresh](https://docs.microsoft.com/office/vba/api/Access.Form.Refresh)** 方法等效。</span><span class="sxs-lookup"><span data-stu-id="a6146-p102">In a client database, you can use the **RefreshRecord** action to update the underlying record source for the active form or datasheet to reflect changes made to the data in the current set. Changes include those made by the current user or by other users in a multiuser environment. It is equivalent to the **[Refresh](https://docs.microsoft.com/office/vba/api/Access.Form.Refresh)** method.</span></span>

<span data-ttu-id="a6146-115">**RefreshRecord** 宏操作可在客户端数据库中执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a6146-115">The **RefreshRecord** macro action does the following in a client database:</span></span>

1.  <span data-ttu-id="a6146-p103">更新活动窗体或数据表的记录源，以反映对当前集合中的行所做的更改。对于 ODBC 链接表，则从数据源中检索对当前集合中的记录所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a6146-p103">Updates the record source for the active form or datasheet to reflect the changes made to rows in the current set. For ODBC linked tables, retrieves changes to records in the current set from the data source.</span></span>

2.  <span data-ttu-id="a6146-118">更新当前集合，以反映更改。</span><span class="sxs-lookup"><span data-stu-id="a6146-118">Updates the current set to reflect the changes.</span></span> <span data-ttu-id="a6146-119">如果已删除记录源中的某行, 则会将其更改为\#显示 "已删除"。</span><span class="sxs-lookup"><span data-stu-id="a6146-119">If a row in the record source has been deleted, it is changed to show \#Deleted.</span></span>

3.  <span data-ttu-id="a6146-120">刷新活动或数据表, 以显示当前集合中任何已\#更改的记录和任何已删除的记录。</span><span class="sxs-lookup"><span data-stu-id="a6146-120">Refreshes the active or datasheet to display any changed records and any \#Deleted records, in the current set.</span></span>

4.  <span data-ttu-id="a6146-121">再次查询活动窗体或数据表上的任何子窗体和子报表。</span><span class="sxs-lookup"><span data-stu-id="a6146-121">Requeries any subforms and subreports on the active form or datasheet.</span></span>

## <a name="web-database"></a><span data-ttu-id="a6146-122">Web 数据库</span><span class="sxs-lookup"><span data-stu-id="a6146-122">Web database</span></span>

<span data-ttu-id="a6146-p105">在 Web 数据库中，您可以使用 **RefreshRecord** 操作更新活动窗体或数据表的基础记录源，以反映对当前集合中的记录所做的更改。这些更改包括当前用户或其他用户所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a6146-p105">In a web database, you can use the **RefreshRecord** action to update the underlying record source for the active form or datasheet to reflect changes made to the records in the current set. Changes include those made by the current user or other users.</span></span>

<span data-ttu-id="a6146-125">**RefreshRecord** 宏操作可在 Web 数据库中执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a6146-125">The **RefreshRecord** macro action does the following in a web database:</span></span>

1.  <span data-ttu-id="a6146-p106">从服务器中检索对当前集合中的任何基表的更改。对于 ODBC 链接表，则从数据源中检索对当前集合中的记录所做的更改。</span><span class="sxs-lookup"><span data-stu-id="a6146-p106">Retrieves changes from the server for any base tables in the current set. For ODBC linked tables, retrieves changes to records in the current set from the data source.</span></span>

2.  <span data-ttu-id="a6146-128">更新当前集合，以反映更改。</span><span class="sxs-lookup"><span data-stu-id="a6146-128">Updates the current set to reflect the changes.</span></span> <span data-ttu-id="a6146-129">如果当前集合中的行已被删除, 则会将其更改为\#显示已删除。</span><span class="sxs-lookup"><span data-stu-id="a6146-129">If a row in the current set has been deleted, it is changed to show \#Deleted.</span></span>

3.  <span data-ttu-id="a6146-130">刷新活动窗体或数据表, 以显示当前集合中任何\#已更改的记录和任何已删除的记录。</span><span class="sxs-lookup"><span data-stu-id="a6146-130">Refreshes the active form or datasheet to display any changed records and any \#Deleted records, in the current set.</span></span>

4.  <span data-ttu-id="a6146-131">再次查询活动窗体或数据表上的任何子窗体和子报表。</span><span class="sxs-lookup"><span data-stu-id="a6146-131">Requeries any subforms and subreports on the active form or datasheet.</span></span>

