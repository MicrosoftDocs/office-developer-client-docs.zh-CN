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
# <a name="tables-and-memory-usage"></a><span data-ttu-id="56a6a-103">表和内存使用</span><span class="sxs-lookup"><span data-stu-id="56a6a-103">Tables and memory usage</span></span>

<span data-ttu-id="56a6a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="56a6a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="56a6a-105">从表中检索数据时，一个重要的问题是内存使用量。</span><span class="sxs-lookup"><span data-stu-id="56a6a-105">An important issue connected with retrieving data from a table is memory usage.</span></span> <span data-ttu-id="56a6a-106">缺少可用内存会导致 [IMAPITable：：QueryRows](imapitable-queryrows.md) 和 [HrQueryAllRows](hrqueryallrows.md) 失败，返回的行数少于所需的行数。</span><span class="sxs-lookup"><span data-stu-id="56a6a-106">Lack of available memory can cause [IMAPITable::QueryRows](imapitable-queryrows.md) and [HrQueryAllRows](hrqueryallrows.md) to fail, returning less than the desired number of rows.</span></span> <span data-ttu-id="56a6a-107">确定用于检索表数据的方法或函数取决于表是否可以容纳在内存中，如果失败是可接受的，则确定表是否可以容纳在内存中。</span><span class="sxs-lookup"><span data-stu-id="56a6a-107">Deciding which method or function to use to retrieve table data depends on whether the table can be expected to fit in memory, and if it cannot, if failure is acceptable.</span></span> 
  
<span data-ttu-id="56a6a-108">由于一次确定适合内存中的数据量并不总是一件容易的事情，MAPI 提供了一些基本准则，以便客户端应用程序或服务提供商遵循这些准则。</span><span class="sxs-lookup"><span data-stu-id="56a6a-108">Because it is not always easy to determine the amount of data that will fit into memory at one time, MAPI provides some basic guidelines for a client application or service provider to follow.</span></span> <span data-ttu-id="56a6a-109">请记住，根据特定的表实现和基础数据的存储方法，始终存在例外。</span><span class="sxs-lookup"><span data-stu-id="56a6a-109">Remember that there are always exceptions, based on the particular table implementation and how the underlying data is stored.</span></span>
  
<span data-ttu-id="56a6a-110">以下指南可用于评估表内存使用情况：</span><span class="sxs-lookup"><span data-stu-id="56a6a-110">The following guidelines can be used to evaluate table memory usage:</span></span>
  
- <span data-ttu-id="56a6a-111">可以容忍在兆字节范围内偶尔工作集内存使用量的客户端，并可以假定他们在将整个表读取到内存中时没有问题。</span><span class="sxs-lookup"><span data-stu-id="56a6a-111">Clients that can tolerate occasional working set memory usage in the megabyte range and can assume they will have no problems reading an entire table into memory.</span></span> 
    
- <span data-ttu-id="56a6a-112">限制会影响表的内存使用率。</span><span class="sxs-lookup"><span data-stu-id="56a6a-112">Restrictions have an affect on a table's usage of memory.</span></span> <span data-ttu-id="56a6a-113">具有大量行（如内容表）的严格限制表可以容纳在内存中，而不受限制的大型表通常不能容纳。</span><span class="sxs-lookup"><span data-stu-id="56a6a-113">A severely restricted table with an extensive number of rows, such as a contents table, can be expected to fit into memory while an unrestricted large table usually cannot.</span></span> 
    
- <span data-ttu-id="56a6a-114">MAPI 拥有的几个表（如状态表、配置文件表、邮件服务表、提供程序表和邮件存储表）通常适合内存中。</span><span class="sxs-lookup"><span data-stu-id="56a6a-114">Several of the tables owned by MAPI such as the status, profile, message service, provider, and message store tables, will usually fit in memory.</span></span> <span data-ttu-id="56a6a-115">这些表通常是小表。</span><span class="sxs-lookup"><span data-stu-id="56a6a-115">These are generally small tables.</span></span> <span data-ttu-id="56a6a-116">但是，存在例外情况。</span><span class="sxs-lookup"><span data-stu-id="56a6a-116">However, there are exceptions.</span></span> <span data-ttu-id="56a6a-117">例如，基于服务器的配置文件提供程序可能会生成一个无法容纳的较大配置文件表。</span><span class="sxs-lookup"><span data-stu-id="56a6a-117">For example, a server-based profile provider might generate a larger profile table that will not be able to fit.</span></span>
    
<span data-ttu-id="56a6a-118">若要检索表中适合内存的所有行，而没有任何问题，请调用 [HrQueryAllRows，](hrqueryallrows.md)将最大行数设置为 0。</span><span class="sxs-lookup"><span data-stu-id="56a6a-118">To retrieve all of the rows from a table that will fit into memory with no problems, call [HrQueryAllRows](hrqueryallrows.md), setting the maximum number of rows to zero.</span></span>
  
<span data-ttu-id="56a6a-119">若要从表中检索可能适合或不适合内存的所有行，从而生成错误，请调用指定最大行数的 **HrQueryAllRows。**</span><span class="sxs-lookup"><span data-stu-id="56a6a-119">To retrieve all of the rows from a table that might or might not fit into memory, generating an error, call **HrQueryAllRows** specifying a maximum number of rows.</span></span> <span data-ttu-id="56a6a-120">最大行数应设置为大于所需最小行数的行数。</span><span class="sxs-lookup"><span data-stu-id="56a6a-120">The maximum number of rows should be set to a number greater than the minimum number of rows that are needed.</span></span> <span data-ttu-id="56a6a-121">如果客户端必须至少从 300 行表中访问 50 行，则最大行数应设置为至少 51 行。</span><span class="sxs-lookup"><span data-stu-id="56a6a-121">If a client must access at least 50 rows from a 300 row table, the maximum number of rows should be set to at least 51.</span></span> 
  
<span data-ttu-id="56a6a-122">若要从表中检索不应放入内存的所有行，请调用具有相对较小行数的循环中的 [IMAPITable：：QueryRows，](imapitable-queryrows.md) 如以下代码示例所示：</span><span class="sxs-lookup"><span data-stu-id="56a6a-122">To retrieve all of the rows from a table that is not expected to fit into memory, call [IMAPITable::QueryRows](imapitable-queryrows.md) in a loop with a relatively small row count, as the following code sample illustrates:</span></span> 
  
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

<span data-ttu-id="56a6a-123">当此循环完成并且已处理表中的所有行且  _cRows_ 为零时，游标的位置通常位于表的底部。</span><span class="sxs-lookup"><span data-stu-id="56a6a-123">When this loop completes and all the rows in the table have been processed and  _cRows_ is zero, the position of the cursor will usually be at the bottom of the table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="56a6a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56a6a-124">See also</span></span>

- [<span data-ttu-id="56a6a-125">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="56a6a-125">MAPI Tables</span></span>](mapi-tables.md)

