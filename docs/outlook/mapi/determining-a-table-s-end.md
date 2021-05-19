---
title: 确定表的结束
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
# <a name="determining-a-tables-end"></a><span data-ttu-id="8132f-103">确定表的结束</span><span class="sxs-lookup"><span data-stu-id="8132f-103">Determining a Table's End</span></span>

  
  
<span data-ttu-id="8132f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8132f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="8132f-105">一个常见错误是假定在出现以下错误时已到达表的末尾：</span><span class="sxs-lookup"><span data-stu-id="8132f-105">A common error is to assume that the end of the table has been reached when:</span></span> 
  
- <span data-ttu-id="8132f-106">[IMAPITable：：QueryRows](imapitable-queryrows.md) 已在循环中调用，循环的结束由 [IMAPITable：：GetRowCount](imapitable-getrowcount.md)返回的行数确定。</span><span class="sxs-lookup"><span data-stu-id="8132f-106">[IMAPITable::QueryRows](imapitable-queryrows.md) has been called in a loop, with the end of the loop determined by the row count returned by [IMAPITable::GetRowCount](imapitable-getrowcount.md).</span></span> <span data-ttu-id="8132f-107">**GetRowCount** 返回的计数并不总是表示表格中确切的行数;它是近似计数。</span><span class="sxs-lookup"><span data-stu-id="8132f-107">The count that **GetRowCount** returns does not always represent the exact number of rows in the table; it is an approximate count.</span></span> 
    
- <span data-ttu-id="8132f-108">**QueryRows** 的行数已固定，返回的行数较少。</span><span class="sxs-lookup"><span data-stu-id="8132f-108">**QueryRows** has been called with a fixed number of rows and fewer rows are returned.</span></span> <span data-ttu-id="8132f-109">直到 **QueryRows** 返回行计数等于零的行集，才没有要检索的行。</span><span class="sxs-lookup"><span data-stu-id="8132f-109">It is not until **QueryRows** returns a row set with a row count equal to zero that there are no more rows to retrieve.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="8132f-110">调用方只能假定游标位于表末尾的正行数或负行数的表的开头时返回值 S_OK 和零行。</span><span class="sxs-lookup"><span data-stu-id="8132f-110">The only time that a caller can assume that the cursor is positioned at the end of the table for a positive row count or at the beginning of the table for a negative row count is when the value S_OK and zero rows are returned.</span></span> <span data-ttu-id="8132f-111">绝不会MAPI_E_NOT_FOUND值。</span><span class="sxs-lookup"><span data-stu-id="8132f-111">The value MAPI_E_NOT_FOUND is never returned.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8132f-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8132f-112">See also</span></span>



[<span data-ttu-id="8132f-113">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="8132f-113">MAPI Tables</span></span>](mapi-tables.md)

