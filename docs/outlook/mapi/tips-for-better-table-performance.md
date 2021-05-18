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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412511"
---
# <a name="tips-for-better-table-performance"></a><span data-ttu-id="ce5de-103">表性能提升提示</span><span class="sxs-lookup"><span data-stu-id="ce5de-103">Tips for better table performance</span></span>
  
<span data-ttu-id="ce5de-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ce5de-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ce5de-105">由于许多表操作可能非常耗时且无法指示进度，因此使用以下技术提高性能会很有帮助：</span><span class="sxs-lookup"><span data-stu-id="ce5de-105">Because many of the table operations can be time-consuming and there is no way to indicate progress, it is helpful to use the following techniques for improving performance:</span></span>
  
- <span data-ttu-id="ce5de-106">**按 [正确顺序进行 IMAPITable ： IUnknown](imapitableiunknown.md) 调用**</span><span class="sxs-lookup"><span data-stu-id="ce5de-106">**Make [IMAPITable : IUnknown](imapitableiunknown.md) calls in the correct order**</span></span>
    
   <span data-ttu-id="ce5de-107">客户端和服务提供商可以通过多种方式使用表。</span><span class="sxs-lookup"><span data-stu-id="ce5de-107">Clients and service providers can work with tables in a variety of ways.</span></span> <span data-ttu-id="ce5de-108">他们可以使用默认列集和排序顺序打开表并检索所有行的数据。</span><span class="sxs-lookup"><span data-stu-id="ce5de-108">They can open the table and retrieve the data for all of the rows using the default column set and sort order.</span></span> <span data-ttu-id="ce5de-109">或者，他们可以通过更改列集、更改排序顺序或建立限制来缩小表的范围来修改表的此默认视图。</span><span class="sxs-lookup"><span data-stu-id="ce5de-109">Alternatively, they can modify this default view of the table by changing the column set, changing the sort order, or establishing a restriction to narrow the table's scope.</span></span> <span data-ttu-id="ce5de-110">在检索任何数据之前打算执行一个或多个这些操作的用户应按以下顺序执行这些操作：</span><span class="sxs-lookup"><span data-stu-id="ce5de-110">Table users that intend to perform one or more of these operations before retrieving any data should perform them in the following order:</span></span>
    
    1. <span data-ttu-id="ce5de-111">使用 [IMAPITable：：SetColumns 定义列集](imapitable-setcolumns.md)。</span><span class="sxs-lookup"><span data-stu-id="ce5de-111">Define a column set with [IMAPITable::SetColumns](imapitable-setcolumns.md).</span></span>
        
    2. <span data-ttu-id="ce5de-112">与 [IMAPITable：：Restrict 建立限制](imapitable-restrict.md)。</span><span class="sxs-lookup"><span data-stu-id="ce5de-112">Establish a restriction with [IMAPITable::Restrict](imapitable-restrict.md).</span></span>
        
    3. <span data-ttu-id="ce5de-113">使用 [IMAPITable：：SortTable 定义排序顺序](imapitable-sorttable.md)。</span><span class="sxs-lookup"><span data-stu-id="ce5de-113">Define a sort order with [IMAPITable::SortTable](imapitable-sorttable.md).</span></span>
    
    <span data-ttu-id="ce5de-114">按此顺序执行这些任务将限制排序的行数和列数，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="ce5de-114">Performing these tasks in this order limits the number of rows and columns that will be sorted, thereby improving performance.</span></span>
    
- <span data-ttu-id="ce5de-115">**如果可能，使用 TBL_BATCH 标志延迟操作**</span><span class="sxs-lookup"><span data-stu-id="ce5de-115">**Delay an operation using the TBL_BATCH flag if possible**</span></span>
    
    <span data-ttu-id="ce5de-116">通过设置方法上的 TBL BATCH 标志，表实施者可以在处理其中任何一个调用之前 \_ 收集多个调用。</span><span class="sxs-lookup"><span data-stu-id="ce5de-116">Setting the TBL\_BATCH flag on a method allows the table implementer to collect several calls before acting on any one of them.</span></span> <span data-ttu-id="ce5de-117">不要对远程服务器进行潜在的多次调用;表实施者可以创建一个表，一次执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="ce5de-117">Instead of make potentially many calls to a remote server; a table implementer can make one, performing all the operations at one time.</span></span> <span data-ttu-id="ce5de-118">在需要操作结果之前，不会评估它们。</span><span class="sxs-lookup"><span data-stu-id="ce5de-118">The results of the operations are not evaluated until they are needed.</span></span> 
    
    <span data-ttu-id="ce5de-119">例如，当客户端调用 [IMAPITable：：Restrict](imapitable-restrict.md) 以指定设置了 TBL 批处理标志的限制时，在客户端调用 \_ [IMAPITable：：QueryRows](imapitable-queryrows.md) 检索数据之前，该限制不一定生效。</span><span class="sxs-lookup"><span data-stu-id="ce5de-119">For example, when a client calls [IMAPITable::Restrict](imapitable-restrict.md) to specify a restriction with the TBL\_BATCH flag set, the restriction do not have to go into effect until the client calls [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve the data.</span></span> <span data-ttu-id="ce5de-120">这允许表实施者将两个调用的工作合并为一个。</span><span class="sxs-lookup"><span data-stu-id="ce5de-120">This allows the table implementer to combine the work of two calls into one.</span></span> <span data-ttu-id="ce5de-121">利用 TBL 批处理标志的表用户应注意，在这些条件下的错误处理 \_ 可能更加复杂。</span><span class="sxs-lookup"><span data-stu-id="ce5de-121">Table users that take advantage of the TBL\_BATCH flag should be aware that error handling under these conditions can be more complex.</span></span> 
    
    <span data-ttu-id="ce5de-122">由于处理延迟操作中的错误与设置 MAPI DEFERRED_ERRORS 标志时处理错误类似，有关详细信息，请参阅 \_ [Deferring MAPI Errors。](deferring-mapi-errors.md)</span><span class="sxs-lookup"><span data-stu-id="ce5de-122">Because handling the errors from a delayed operation is similar to handling the errors when the MAPI\_DEFERRED_ERRORS flag is set, see [Deferring MAPI Errors](deferring-mapi-errors.md) for more information.</span></span> 
    
- <span data-ttu-id="ce5de-123">**保留常用属性的缓存**</span><span class="sxs-lookup"><span data-stu-id="ce5de-123">**Keep a cache of commonly used properties**</span></span>
    
    <span data-ttu-id="ce5de-124">通过缓存常用对象属性的副本，实现表的服务提供商可以减少创建视图所花的时间。</span><span class="sxs-lookup"><span data-stu-id="ce5de-124">Service providers implementing tables can lessen the time it takes to create a view by caching copies of commonly used object properties.</span></span> <span data-ttu-id="ce5de-125">将这些属性的副本保存在内存中可节省每次必须重新生成视图时从对象中检索这些属性。</span><span class="sxs-lookup"><span data-stu-id="ce5de-125">Keeping a copy of these properties in memory saves having to retrieve them from the object each time the view must be rebuilt.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ce5de-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce5de-126">See also</span></span>

- [<span data-ttu-id="ce5de-127">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="ce5de-127">MAPI Tables</span></span>](mapi-tables.md)

