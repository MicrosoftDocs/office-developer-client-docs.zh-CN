---
title: 表和内存使用情况
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7ac11e60-6b2c-4241-96e2-20219f84d949
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 390cec0cc59f189f83af2c5339512d82e125771e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778964"
---
# <a name="tables-and-memory-usage"></a><span data-ttu-id="58cd9-103">表和内存使用情况</span><span class="sxs-lookup"><span data-stu-id="58cd9-103">Tables and memory usage</span></span>

<span data-ttu-id="58cd9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="58cd9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="58cd9-105">与表中检索数据连接的重要问题是内存使用率。</span><span class="sxs-lookup"><span data-stu-id="58cd9-105">An important issue connected with retrieving data from a table is memory usage.</span></span> <span data-ttu-id="58cd9-106">可用内存不足可能导致[IMAPITable::QueryRows](imapitable-queryrows.md)和[HrQueryAllRows](hrqueryallrows.md)失败，返回所需的行数小于。</span><span class="sxs-lookup"><span data-stu-id="58cd9-106">Lack of available memory can cause [IMAPITable::QueryRows](imapitable-queryrows.md) and [HrQueryAllRows](hrqueryallrows.md) to fail, returning less than the desired number of rows.</span></span> <span data-ttu-id="58cd9-107">决定哪些方法或函数用于检索表数据取决于是否可以预期表以适合在内存中，并不能转换，如果是可接受的失败。</span><span class="sxs-lookup"><span data-stu-id="58cd9-107">Deciding which method or function to use to retrieve table data depends on whether the table can be expected to fit in memory, and if it cannot, if failure is acceptable.</span></span> 
  
<span data-ttu-id="58cd9-108">因为并非始终容易地确定将一次适合内存的数据量，MAPI 提供了客户端应用程序或服务提供商，若要遵循一些基本的原则。</span><span class="sxs-lookup"><span data-stu-id="58cd9-108">Because it is not always easy to determine the amount of data that will fit into memory at one time, MAPI provides some basic guidelines for a client application or service provider to follow.</span></span> <span data-ttu-id="58cd9-109">请记住都始终例外，基于特定的表实现和如何存储基础数据。</span><span class="sxs-lookup"><span data-stu-id="58cd9-109">Remember that there are always exceptions, based on the particular table implementation and how the underlying data is stored.</span></span>
  
<span data-ttu-id="58cd9-110">以下准则可用于评估表内存使用情况：</span><span class="sxs-lookup"><span data-stu-id="58cd9-110">The following guidelines can be used to evaluate table memory usage:</span></span>
  
- <span data-ttu-id="58cd9-111">可以容忍偶尔兆字节范围中的工作集内存使用率，并可以假定它们的客户端会读取到内存整个表没有问题。</span><span class="sxs-lookup"><span data-stu-id="58cd9-111">Clients that can tolerate occasional working set memory usage in the megabyte range and can assume they will have no problems reading an entire table into memory.</span></span> 
    
- <span data-ttu-id="58cd9-112">限制会影响的内存表的使用情况。</span><span class="sxs-lookup"><span data-stu-id="58cd9-112">Restrictions have an affect on a table's usage of memory.</span></span> <span data-ttu-id="58cd9-113">预计严格限制的表与广泛的行数，如内容目录，而不受限制的大型表通常不能适合内存。</span><span class="sxs-lookup"><span data-stu-id="58cd9-113">A severely restricted table with an extensive number of rows, such as a contents table, can be expected to fit into memory while an unrestricted large table usually cannot.</span></span> 
    
- <span data-ttu-id="58cd9-114">有几个 MAPI 拥有如状态、 配置文件、 消息服务、 提供商和邮件存储表的表通常适合内存中。</span><span class="sxs-lookup"><span data-stu-id="58cd9-114">Several of the tables owned by MAPI such as the status, profile, message service, provider, and message store tables, will usually fit in memory.</span></span> <span data-ttu-id="58cd9-115">这些是通常小表。</span><span class="sxs-lookup"><span data-stu-id="58cd9-115">These are generally small tables.</span></span> <span data-ttu-id="58cd9-116">但是，有一些例外。</span><span class="sxs-lookup"><span data-stu-id="58cd9-116">However, there are exceptions.</span></span> <span data-ttu-id="58cd9-117">例如，基于服务器的配置文件提供程序可能会生成不能以适应较大的配置文件表。</span><span class="sxs-lookup"><span data-stu-id="58cd9-117">For example, a server-based profile provider might generate a larger profile table that will not be able to fit.</span></span>
    
<span data-ttu-id="58cd9-118">若要从将适合与没有问题的内存表中检索的所有行，调用[HrQueryAllRows](hrqueryallrows.md)，将最大行数设置为零。</span><span class="sxs-lookup"><span data-stu-id="58cd9-118">To retrieve all of the rows from a table that will fit into memory with no problems, call [HrQueryAllRows](hrqueryallrows.md), setting the maximum number of rows to zero.</span></span>
  
<span data-ttu-id="58cd9-119">若要检索的所有行从一个表，可能是也可能不适合内存，生成一个错误，调用**HrQueryAllRows**指定最大行数。</span><span class="sxs-lookup"><span data-stu-id="58cd9-119">To retrieve all of the rows from a table that might or might not fit into memory, generating an error, call **HrQueryAllRows** specifying a maximum number of rows.</span></span> <span data-ttu-id="58cd9-120">最大行数应设置为数大于的最小所需的行数。</span><span class="sxs-lookup"><span data-stu-id="58cd9-120">The maximum number of rows should be set to a number greater than the minimum number of rows that are needed.</span></span> <span data-ttu-id="58cd9-121">如果客户端必须访问 300 行表中至少 50 行，最大行数应设置为至少 51。</span><span class="sxs-lookup"><span data-stu-id="58cd9-121">If a client must access at least 50 rows from a 300 row table, the maximum number of rows should be set to at least 51.</span></span> 
  
<span data-ttu-id="58cd9-122">若要检索的表中不应适合内存中的所有行，调用[IMAPITable::QueryRows](imapitable-queryrows.md)循环与相对较小的行数，如下面的代码示例所示：</span><span class="sxs-lookup"><span data-stu-id="58cd9-122">To retrieve all of the rows from a table that is not expected to fit into memory, call [IMAPITable::QueryRows](imapitable-queryrows.md) in a loop with a relatively small row count, as the following code sample illustrates:</span></span> 
  
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

<span data-ttu-id="58cd9-123">此循环完成和已处理表中的所有行，并且_cRows_为零，光标位置通常会在表的底部。</span><span class="sxs-lookup"><span data-stu-id="58cd9-123">When this loop completes and all the rows in the table have been processed and  _cRows_ is zero, the position of the cursor will usually be at the bottom of the table.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="58cd9-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58cd9-124">See also</span></span>

- [<span data-ttu-id="58cd9-125">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="58cd9-125">MAPI Tables</span></span>](mapi-tables.md)

