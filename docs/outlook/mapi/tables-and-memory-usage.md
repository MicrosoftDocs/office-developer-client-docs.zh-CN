---
title: 表和内存使用
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7ac11e60-6b2c-4241-96e2-20219f84d949
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: afd69f5a3fff69f670d6be78ba4957307cdb6995
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436858"
---
# <a name="tables-and-memory-usage"></a><span data-ttu-id="46c7f-103">表和内存使用</span><span class="sxs-lookup"><span data-stu-id="46c7f-103">Tables and memory usage</span></span>

<span data-ttu-id="46c7f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="46c7f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="46c7f-105">通过从表检索数据而连接的一个重要问题是内存使用率。</span><span class="sxs-lookup"><span data-stu-id="46c7f-105">An important issue connected with retrieving data from a table is memory usage.</span></span> <span data-ttu-id="46c7f-106">缺少可用内存会导致[IMAPITable:: QueryRows](imapitable-queryrows.md)和[HrQueryAllRows](hrqueryallrows.md)失败, 返回的行数小于所需的行数。</span><span class="sxs-lookup"><span data-stu-id="46c7f-106">Lack of available memory can cause [IMAPITable::QueryRows](imapitable-queryrows.md) and [HrQueryAllRows](hrqueryallrows.md) to fail, returning less than the desired number of rows.</span></span> <span data-ttu-id="46c7f-107">确定用于检索表数据的方法或函数取决于表是否可以在内存中使用, 如果故障是可接受的, 则是如此。</span><span class="sxs-lookup"><span data-stu-id="46c7f-107">Deciding which method or function to use to retrieve table data depends on whether the table can be expected to fit in memory, and if it cannot, if failure is acceptable.</span></span> 
  
<span data-ttu-id="46c7f-108">由于很难确定一次内存中适合的数据量, 因此 MAPI 提供了有关要遵循的客户端应用程序或服务提供商的一些基本准则。</span><span class="sxs-lookup"><span data-stu-id="46c7f-108">Because it is not always easy to determine the amount of data that will fit into memory at one time, MAPI provides some basic guidelines for a client application or service provider to follow.</span></span> <span data-ttu-id="46c7f-109">请注意, 始终有一些异常, 这取决于特定的表实现以及基础数据的存储方式。</span><span class="sxs-lookup"><span data-stu-id="46c7f-109">Remember that there are always exceptions, based on the particular table implementation and how the underlying data is stored.</span></span>
  
<span data-ttu-id="46c7f-110">以下准则可用于评估表内存使用率:</span><span class="sxs-lookup"><span data-stu-id="46c7f-110">The following guidelines can be used to evaluate table memory usage:</span></span>
  
- <span data-ttu-id="46c7f-111">可以容忍 mb 范围内的偶尔工作集内存使用率的客户端, 并可假定它们在将整个表读取到内存中不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="46c7f-111">Clients that can tolerate occasional working set memory usage in the megabyte range and can assume they will have no problems reading an entire table into memory.</span></span> 
    
- <span data-ttu-id="46c7f-112">限制会对表的内存使用产生影响。</span><span class="sxs-lookup"><span data-stu-id="46c7f-112">Restrictions have an affect on a table's usage of memory.</span></span> <span data-ttu-id="46c7f-113">具有大量行 (如内容表) 的严格受限制的表可能会在内存中显示, 而不受限制的大表通常不能装入。</span><span class="sxs-lookup"><span data-stu-id="46c7f-113">A severely restricted table with an extensive number of rows, such as a contents table, can be expected to fit into memory while an unrestricted large table usually cannot.</span></span> 
    
- <span data-ttu-id="46c7f-114">MAPI (如状态、配置文件、邮件服务、提供程序和邮件存储表) 所拥有的几个表通常会放入内存中。</span><span class="sxs-lookup"><span data-stu-id="46c7f-114">Several of the tables owned by MAPI such as the status, profile, message service, provider, and message store tables, will usually fit in memory.</span></span> <span data-ttu-id="46c7f-115">这些通常是小型表格。</span><span class="sxs-lookup"><span data-stu-id="46c7f-115">These are generally small tables.</span></span> <span data-ttu-id="46c7f-116">不过, 也有一些例外情况。</span><span class="sxs-lookup"><span data-stu-id="46c7f-116">However, there are exceptions.</span></span> <span data-ttu-id="46c7f-117">例如, 基于服务器的配置文件提供程序可能会生成一个较大的配置文件表, 该表将无法合适。</span><span class="sxs-lookup"><span data-stu-id="46c7f-117">For example, a server-based profile provider might generate a larger profile table that will not be able to fit.</span></span>
    
<span data-ttu-id="46c7f-118">若要检索表中的所有行, 这些行将适合不出现任何问题的内存, 请调用[HrQueryAllRows](hrqueryallrows.md), 将最大行数设置为零。</span><span class="sxs-lookup"><span data-stu-id="46c7f-118">To retrieve all of the rows from a table that will fit into memory with no problems, call [HrQueryAllRows](hrqueryallrows.md), setting the maximum number of rows to zero.</span></span>
  
<span data-ttu-id="46c7f-119">若要检索表中可能有也可能不符合内存的所有行, 请生成错误, 请调用**HrQueryAllRows**指定最大行数。</span><span class="sxs-lookup"><span data-stu-id="46c7f-119">To retrieve all of the rows from a table that might or might not fit into memory, generating an error, call **HrQueryAllRows** specifying a maximum number of rows.</span></span> <span data-ttu-id="46c7f-120">最大行数应设置为大于所需的最小行数的数字。</span><span class="sxs-lookup"><span data-stu-id="46c7f-120">The maximum number of rows should be set to a number greater than the minimum number of rows that are needed.</span></span> <span data-ttu-id="46c7f-121">如果客户端必须从300行表访问至少50行, 则最多应将最大行数至少设置为51。</span><span class="sxs-lookup"><span data-stu-id="46c7f-121">If a client must access at least 50 rows from a 300 row table, the maximum number of rows should be set to at least 51.</span></span> 
  
<span data-ttu-id="46c7f-122">若要检索表中不符合预期内存的所有行, 请调用[IMAPITable:: QueryRows](imapitable-queryrows.md)在相对较小的行计数的循环中, 如以下代码示例所示:</span><span class="sxs-lookup"><span data-stu-id="46c7f-122">To retrieve all of the rows from a table that is not expected to fit into memory, call [IMAPITable::QueryRows](imapitable-queryrows.md) in a loop with a relatively small row count, as the following code sample illustrates:</span></span> 
  
```cpp
HRESULT     hr;
LPSRowSet   pRows = NULL;
LONG        irow;
LONG            cAsk = 50;                  // adjust this value
while ((hr = pTable->QueryRows(cAsk, 0, &pRows)) == hrSuccess
        && pRows->cRows != 0)
{
    for (irow = 0; irow < prows->cRows; ++irow)
    {
        // process the row...
    }
    FreeProws(pRows);
    pRows = NULL;
}
if (hr)
{
    // handle the error...
}
 
```

<span data-ttu-id="46c7f-123">当此循环完成且表中的所有行均已处理且_cRows_为0时, 光标的位置通常位于表的底部。</span><span class="sxs-lookup"><span data-stu-id="46c7f-123">When this loop completes and all the rows in the table have been processed and  _cRows_ is zero, the position of the cursor will usually be at the bottom of the table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="46c7f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46c7f-124">See also</span></span>

- [<span data-ttu-id="46c7f-125">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="46c7f-125">MAPI Tables</span></span>](mapi-tables.md)

