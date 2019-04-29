---
title: 确定表的结尾
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c879e972-05f4-4716-8fc2-db5b22f34ca8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 28892e2d351b8dc9aa864c9eff52c94bb0f20e8f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420085"
---
# <a name="determining-a-tables-end"></a><span data-ttu-id="64eae-103">确定表的结尾</span><span class="sxs-lookup"><span data-stu-id="64eae-103">Determining a Table's End</span></span>

  
  
<span data-ttu-id="64eae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="64eae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="64eae-105">一个常见错误是, 在以下情况时, 假定已到达表的末尾:</span><span class="sxs-lookup"><span data-stu-id="64eae-105">A common error is to assume that the end of the table has been reached when:</span></span> 
  
- <span data-ttu-id="64eae-106">[imapitable:: QueryRows](imapitable-queryrows.md)已在循环中调用, 并在循环结束时由[IMAPITable:: GetRowCount](imapitable-getrowcount.md)返回的行数确定。</span><span class="sxs-lookup"><span data-stu-id="64eae-106">[IMAPITable::QueryRows](imapitable-queryrows.md) has been called in a loop, with the end of the loop determined by the row count returned by [IMAPITable::GetRowCount](imapitable-getrowcount.md).</span></span> <span data-ttu-id="64eae-107">**GetRowCount**返回的计数并不总是表示表中的确切行数;它是一个大概数。</span><span class="sxs-lookup"><span data-stu-id="64eae-107">The count that **GetRowCount** returns does not always represent the exact number of rows in the table; it is an approximate count.</span></span> 
    
- <span data-ttu-id="64eae-108">已使用固定的行数调用**QueryRows** , 并且返回的行数较少。</span><span class="sxs-lookup"><span data-stu-id="64eae-108">**QueryRows** has been called with a fixed number of rows and fewer rows are returned.</span></span> <span data-ttu-id="64eae-109">直到**QueryRows**返回行数等于零的行集时, 没有更多的行可供检索。</span><span class="sxs-lookup"><span data-stu-id="64eae-109">It is not until **QueryRows** returns a row set with a row count equal to zero that there are no more rows to retrieve.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="64eae-110">呼叫者唯一的时间是将游标放置在表的末尾, 对于正数行计数或在表的开头, 如果返回值 S_OK 和零行, 则会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="64eae-110">The only time that a caller can assume that the cursor is positioned at the end of the table for a positive row count or at the beginning of the table for a negative row count is when the value S_OK and zero rows are returned.</span></span> <span data-ttu-id="64eae-111">从不返回值 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="64eae-111">The value MAPI_E_NOT_FOUND is never returned.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="64eae-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64eae-112">See also</span></span>



[<span data-ttu-id="64eae-113">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="64eae-113">MAPI Tables</span></span>](mapi-tables.md)

