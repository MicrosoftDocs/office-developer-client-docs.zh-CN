---
title: 表性能提升提示
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ac82f7e8-6453-4b4f-8223-3c23d09ca4c6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 82be33090a63f24c430007d9759045c365961f5d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327795"
---
# <a name="tips-for-better-table-performance"></a><span data-ttu-id="cacf6-103">表性能提升提示</span><span class="sxs-lookup"><span data-stu-id="cacf6-103">Tips for better table performance</span></span>
  
<span data-ttu-id="cacf6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cacf6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cacf6-105">由于许多表操作可能非常耗时且无法指示进度, 因此使用以下技术来提高性能有助于提高性能:</span><span class="sxs-lookup"><span data-stu-id="cacf6-105">Because many of the table operations can be time-consuming and there is no way to indicate progress, it is helpful to use the following techniques for improving performance:</span></span>
  
- <span data-ttu-id="cacf6-106">**使[IMAPITable: IUnknown](imapitableiunknown.md)按正确的顺序呼叫**</span><span class="sxs-lookup"><span data-stu-id="cacf6-106">**Make [IMAPITable : IUnknown](imapitableiunknown.md) calls in the correct order**</span></span>
    
   <span data-ttu-id="cacf6-107">客户端和服务提供程序可以通过多种方式使用表。</span><span class="sxs-lookup"><span data-stu-id="cacf6-107">Clients and service providers can work with tables in a variety of ways.</span></span> <span data-ttu-id="cacf6-108">他们可以打开表, 并使用默认列集和排序顺序检索所有行的数据。</span><span class="sxs-lookup"><span data-stu-id="cacf6-108">They can open the table and retrieve the data for all of the rows using the default column set and sort order.</span></span> <span data-ttu-id="cacf6-109">此外, 他们还可以通过更改列集、更改排序顺序或建立限制以缩小表的范围来修改此表的默认视图。</span><span class="sxs-lookup"><span data-stu-id="cacf6-109">Alternatively, they can modify this default view of the table by changing the column set, changing the sort order, or establishing a restriction to narrow the table's scope.</span></span> <span data-ttu-id="cacf6-110">要在检索任何数据之前执行这些操作中的一个或多个操作的表用户应按以下顺序执行这些操作:</span><span class="sxs-lookup"><span data-stu-id="cacf6-110">Table users that intend to perform one or more of these operations before retrieving any data should perform them in the following order:</span></span>
    
    1. <span data-ttu-id="cacf6-111">使用[IMAPITable:: SetColumns](imapitable-setcolumns.md)定义列集。</span><span class="sxs-lookup"><span data-stu-id="cacf6-111">Define a column set with [IMAPITable::SetColumns](imapitable-setcolumns.md).</span></span>
        
    2. <span data-ttu-id="cacf6-112">使用[IMAPITable:: Restrict](imapitable-restrict.md)建立限制。</span><span class="sxs-lookup"><span data-stu-id="cacf6-112">Establish a restriction with [IMAPITable::Restrict](imapitable-restrict.md).</span></span>
        
    3. <span data-ttu-id="cacf6-113">使用[IMAPITable:: SortTable](imapitable-sorttable.md)定义排序顺序。</span><span class="sxs-lookup"><span data-stu-id="cacf6-113">Define a sort order with [IMAPITable::SortTable](imapitable-sorttable.md).</span></span>
    
    <span data-ttu-id="cacf6-114">按此顺序执行这些任务将对要排序的行和列的数量进行限制, 从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="cacf6-114">Performing these tasks in this order limits the number of rows and columns that will be sorted, thereby improving performance.</span></span>
    
- <span data-ttu-id="cacf6-115">**如果可能, 请使用 TBL_BATCH 标志延迟操作**</span><span class="sxs-lookup"><span data-stu-id="cacf6-115">**Delay an operation using the TBL_BATCH flag if possible**</span></span>
    
    <span data-ttu-id="cacf6-116">通过在方法\_上设置 TBL 批处理标志, 表实施者可以在操作任何一个调用之前收集多个调用。</span><span class="sxs-lookup"><span data-stu-id="cacf6-116">Setting the TBL\_BATCH flag on a method allows the table implementer to collect several calls before acting on any one of them.</span></span> <span data-ttu-id="cacf6-117">而不是对远程服务器进行可能的多个调用; 而是表实施者可以创建一个, 一次执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="cacf6-117">Instead of make potentially many calls to a remote server; a table implementer can make one, performing all the operations at one time.</span></span> <span data-ttu-id="cacf6-118">在需要时才会评估操作的结果。</span><span class="sxs-lookup"><span data-stu-id="cacf6-118">The results of the operations are not evaluated until they are needed.</span></span> 
    
    <span data-ttu-id="cacf6-119">例如, 当客户端调用[imapitable:: Restrict](imapitable-restrict.md)来指定设置了 TBL\_批处理标志的限制时, 在客户端调用[IMAPITable:: QueryRows](imapitable-queryrows.md)检索数据时, 限制不会生效。</span><span class="sxs-lookup"><span data-stu-id="cacf6-119">For example, when a client calls [IMAPITable::Restrict](imapitable-restrict.md) to specify a restriction with the TBL\_BATCH flag set, the restriction do not have to go into effect until the client calls [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve the data.</span></span> <span data-ttu-id="cacf6-120">这使表实施者能够将两个调用的工作合并成一个。</span><span class="sxs-lookup"><span data-stu-id="cacf6-120">This allows the table implementer to combine the work of two calls into one.</span></span> <span data-ttu-id="cacf6-121">利用 TBL\_批处理标志的表用户应注意, 在这些情况下的错误处理可能更复杂。</span><span class="sxs-lookup"><span data-stu-id="cacf6-121">Table users that take advantage of the TBL\_BATCH flag should be aware that error handling under these conditions can be more complex.</span></span> 
    
    <span data-ttu-id="cacf6-122">由于处理延迟操作中的错误与在设置 MAPI\_DEFERRED_ERRORS 标记时处理错误类似, 因此请参阅[延迟 mapi 错误](deferring-mapi-errors.md)以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="cacf6-122">Because handling the errors from a delayed operation is similar to handling the errors when the MAPI\_DEFERRED_ERRORS flag is set, see [Deferring MAPI Errors](deferring-mapi-errors.md) for more information.</span></span> 
    
- <span data-ttu-id="cacf6-123">**保留常用属性的缓存**</span><span class="sxs-lookup"><span data-stu-id="cacf6-123">**Keep a cache of commonly used properties**</span></span>
    
    <span data-ttu-id="cacf6-124">服务提供程序实现表可通过缓存常用对象属性的副本来减少创建视图所需的时间。</span><span class="sxs-lookup"><span data-stu-id="cacf6-124">Service providers implementing tables can lessen the time it takes to create a view by caching copies of commonly used object properties.</span></span> <span data-ttu-id="cacf6-125">在内存中保存这些属性的副本时, 必须在每次重新生成视图时从对象中检索这些属性。</span><span class="sxs-lookup"><span data-stu-id="cacf6-125">Keeping a copy of these properties in memory saves having to retrieve them from the object each time the view must be rebuilt.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cacf6-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cacf6-126">See also</span></span>

- [<span data-ttu-id="cacf6-127">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="cacf6-127">MAPI Tables</span></span>](mapi-tables.md)

