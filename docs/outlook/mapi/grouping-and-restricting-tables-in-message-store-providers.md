---
title: 分组和限制消息存储提供程序中的表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01df4be4-98a1-4159-a06d-9ccf4337198f
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 33c76cdd0e7850f82949349ac2e5bb0dd4e056ef
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775041"
---
# <a name="grouping-and-restricting-tables-in-message-store-providers"></a><span data-ttu-id="e5005-103">分组和限制消息存储提供程序中的表</span><span class="sxs-lookup"><span data-stu-id="e5005-103">Grouping and Restricting Tables in Message Store Providers</span></span>

  
  
<span data-ttu-id="e5005-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e5005-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e5005-105">客户端应用程序经常允许用户一些控制文件夹的内容的显示方式。</span><span class="sxs-lookup"><span data-stu-id="e5005-105">Client applications frequently allow users some control over how the contents of a folder are displayed.</span></span> <span data-ttu-id="e5005-106">通常情况下，用户可以选择一个或多个邮件属性的值根据分组的邮件，或者可以选择要排除匹配特定条件的邮件。</span><span class="sxs-lookup"><span data-stu-id="e5005-106">Typically, a user can choose to have messages grouped according to the value of one or more message properties, or can choose to exclude messages that match certain criteria.</span></span> <span data-ttu-id="e5005-107">这通过使用[IMAPITable: IUnknown](imapitableiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e5005-107">This is done by using the [IMAPITable : IUnknown](imapitableiunknown.md) interface.</span></span> <span data-ttu-id="e5005-108">客户端应用程序可以限制用户指定任何条件返回从表的行。</span><span class="sxs-lookup"><span data-stu-id="e5005-108">Client applications can restrict the rows returned from the table to whatever criteria the user specifies.</span></span> <span data-ttu-id="e5005-109">因此，一条消息存储提供程序需要实现以下**IMAPITable**方法。</span><span class="sxs-lookup"><span data-stu-id="e5005-109">Therefore, a message store provider needs to implement the following **IMAPITable** methods.</span></span> 
  
|<span data-ttu-id="e5005-110">IMAPITable * * 方法 * *</span><span class="sxs-lookup"><span data-stu-id="e5005-110">****IMAPITable** method**</span></span>|<span data-ttu-id="e5005-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="e5005-111">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e5005-112">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="e5005-112">IMAPITable::FindRow</span></span>](imapitable-findrow.md) <br/> |<span data-ttu-id="e5005-113">返回表格符合指定的条件的行。</span><span class="sxs-lookup"><span data-stu-id="e5005-113">Returns table rows that match the specified criteria.</span></span>  <br/> |
|[<span data-ttu-id="e5005-114">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="e5005-114">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md) <br/> |<span data-ttu-id="e5005-115">返回表或当前使用的列组中的列集。</span><span class="sxs-lookup"><span data-stu-id="e5005-115">Returns the set of columns in a table or the set of currently used columns.</span></span>  <br/> |
|[<span data-ttu-id="e5005-116">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="e5005-116">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md) <br/> |<span data-ttu-id="e5005-117">从表中，从给定位置开始返回一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="e5005-117">Returns one or more rows from a table, starting from a given position.</span></span>  <br/> |
|[<span data-ttu-id="e5005-118">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="e5005-118">IMAPITable::Restrict</span></span>](imapitable-restrict.md) <br/> |<span data-ttu-id="e5005-119">应用限制到表中，以便对**FindRow**后续调用返回仅与限制匹配的行。</span><span class="sxs-lookup"><span data-stu-id="e5005-119">Applies a restriction to a table so that subsequent calls to **FindRow** return only rows that match the restriction.</span></span>  <br/> |
|[<span data-ttu-id="e5005-120">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="e5005-120">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md) <br/> |<span data-ttu-id="e5005-121">指定表中检索行时应返回的列。</span><span class="sxs-lookup"><span data-stu-id="e5005-121">Specifies which columns should be returned when rows are retrieved from the table.</span></span>  <br/> |
   
<span data-ttu-id="e5005-122">限制可能会很复杂实现;有关详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="e5005-122">Restrictions can be complex to implement; for more information, see [About Restrictions](about-restrictions.md).</span></span> <span data-ttu-id="e5005-123">有关实现表的详细信息，请参阅[MAPI 表](mapi-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="e5005-123">For more information about implementing tables, see [MAPI Tables](mapi-tables.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e5005-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5005-124">See also</span></span>



[<span data-ttu-id="e5005-125">消息存储功能</span><span class="sxs-lookup"><span data-stu-id="e5005-125">Message Store Features</span></span>](message-store-features.md)
