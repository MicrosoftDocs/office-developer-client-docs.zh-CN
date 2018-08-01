---
title: 更好的表性能的提示
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ac82f7e8-6453-4b4f-8223-3c23d09ca4c6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2b14c4fe8cbbadb2ccdd6a2f7870a07d2f96a3c9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778976"
---
# <a name="tips-for-better-table-performance"></a><span data-ttu-id="ecf7b-103">更好的表性能的提示</span><span class="sxs-lookup"><span data-stu-id="ecf7b-103">Tips for better table performance</span></span>
  
<span data-ttu-id="ecf7b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ecf7b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ecf7b-105">因为许多表操作可以非常耗时并且没有方法以指示进度，非常有用用于提高性能的以下技术：</span><span class="sxs-lookup"><span data-stu-id="ecf7b-105">Because many of the table operations can be time-consuming and there is no way to indicate progress, it is helpful to use the following techniques for improving performance:</span></span>
  
- <span data-ttu-id="ecf7b-106">**进行[IMAPITable: IUnknown](imapitableiunknown.md)调用以正确的顺序**</span><span class="sxs-lookup"><span data-stu-id="ecf7b-106">**Make [IMAPITable : IUnknown](imapitableiunknown.md) calls in the correct order**</span></span>
    
   <span data-ttu-id="ecf7b-107">客户端和服务提供商可以使用表中的各种方式。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-107">Clients and service providers can work with tables in a variety of ways.</span></span> <span data-ttu-id="ecf7b-108">它们可以打开的表格并检索所有使用默认列集的行的数据排序顺序。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-108">They can open the table and retrieve the data for all of the rows using the default column set and sort order.</span></span> <span data-ttu-id="ecf7b-109">此外，他们可以通过更改列集，更改排序次序，或建立缩小表的范围限制修改表的此默认视图。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-109">Alternatively, they can modify this default view of the table by changing the column set, changing the sort order, or establishing a restriction to narrow the table's scope.</span></span> <span data-ttu-id="ecf7b-110">要检索任何数据之前执行一个或多个这些操作的表用户应执行这些顺序如下：</span><span class="sxs-lookup"><span data-stu-id="ecf7b-110">Table users that intend to perform one or more of these operations before retrieving any data should perform them in the following order:</span></span>
    
    1. <span data-ttu-id="ecf7b-111">定义与[IMAPITable::SetColumns](imapitable-setcolumns.md)设置的列。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-111">Define a column set with [IMAPITable::SetColumns](imapitable-setcolumns.md).</span></span>
        
    2. <span data-ttu-id="ecf7b-112">建立与[IMAPITable::Restrict](imapitable-restrict.md)限制。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-112">Establish a restriction with [IMAPITable::Restrict](imapitable-restrict.md).</span></span>
        
    3. <span data-ttu-id="ecf7b-113">定义与[IMAPITable::SortTable](imapitable-sorttable.md)排序顺序。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-113">Define a sort order with [IMAPITable::SortTable](imapitable-sorttable.md).</span></span>
    
    <span data-ttu-id="ecf7b-114">按此顺序执行这些任务限制的行和列将进行排序，从而提高性能的数量。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-114">Performing these tasks in this order limits the number of rows and columns that will be sorted, thereby improving performance.</span></span>
    
- <span data-ttu-id="ecf7b-115">**延迟尽可能使用 TBL_BATCH 标志操作**</span><span class="sxs-lookup"><span data-stu-id="ecf7b-115">**Delay an operation using the TBL_BATCH flag if possible**</span></span>
    
    <span data-ttu-id="ecf7b-116">设置 TBL\_方法的批处理标志允许表实施者可以在任意一上收集执行之前的多个呼叫。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-116">Setting the TBL\_BATCH flag on a method allows the table implementer to collect several calls before acting on any one of them.</span></span> <span data-ttu-id="ecf7b-117">而不是使可能很多呼叫到远程服务器;表实施可以先创建一个，一次执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-117">Instead of make potentially many calls to a remote server; a table implementer can make one, performing all the operations at one time.</span></span> <span data-ttu-id="ecf7b-118">在需要时才不计算操作的结果。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-118">The results of the operations are not evaluated until they are needed.</span></span> 
    
    <span data-ttu-id="ecf7b-119">例如，当客户端调用[IMAPITable::Restrict](imapitable-restrict.md) TBL 指定限制\_批处理标志设置限制不必进入效果，直到客户端调用[IMAPITable::QueryRows](imapitable-queryrows.md)检索数据。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-119">For example, when a client calls [IMAPITable::Restrict](imapitable-restrict.md) to specify a restriction with the TBL\_BATCH flag set, the restriction do not have to go into effect until the client calls [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve the data.</span></span> <span data-ttu-id="ecf7b-120">这样，若要合并的两个呼叫到一个工作表实施。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-120">This allows the table implementer to combine the work of two calls into one.</span></span> <span data-ttu-id="ecf7b-121">表用户充分利用 TBL 的\_可能更复杂的错误处理在这些情况下应注意批次标志。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-121">Table users that take advantage of the TBL\_BATCH flag should be aware that error handling under these conditions can be more complex.</span></span> 
    
    <span data-ttu-id="ecf7b-122">因为处理从延迟的请求操作错误是类似于处理错误时 MAPI\_设置 DEFERRED_ERRORS 标志、 详细信息，请参阅[推迟 MAPI 错误](deferring-mapi-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-122">Because handling the errors from a delayed operation is similar to handling the errors when the MAPI\_DEFERRED_ERRORS flag is set, see [Deferring MAPI Errors](deferring-mapi-errors.md) for more information.</span></span> 
    
- <span data-ttu-id="ecf7b-123">**保留缓存的常用属性**</span><span class="sxs-lookup"><span data-stu-id="ecf7b-123">**Keep a cache of commonly used properties**</span></span>
    
    <span data-ttu-id="ecf7b-124">服务提供商实现表可以减少缓存副本的常用的对象属性创建视图所需的时间。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-124">Service providers implementing tables can lessen the time it takes to create a view by caching copies of commonly used object properties.</span></span> <span data-ttu-id="ecf7b-125">必须重建视图中无需每次都从对象中检索它们的内存保存保留一份这些属性。</span><span class="sxs-lookup"><span data-stu-id="ecf7b-125">Keeping a copy of these properties in memory saves having to retrieve them from the object each time the view must be rebuilt.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ecf7b-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ecf7b-126">See also</span></span>

- [<span data-ttu-id="ecf7b-127">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="ecf7b-127">MAPI Tables</span></span>](mapi-tables.md)

