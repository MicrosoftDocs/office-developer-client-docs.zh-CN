---
title: 确定表末尾
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c879e972-05f4-4716-8fc2-db5b22f34ca8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7cbf11f16948d582ba36a0b4d20411549b723b38
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774779"
---
# <a name="determining-a-tables-end"></a><span data-ttu-id="33814-103">确定表末尾</span><span class="sxs-lookup"><span data-stu-id="33814-103">Determining a Table's End</span></span>

  
  
<span data-ttu-id="33814-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="33814-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="33814-105">常见错误是表的假定末尾已达到时：</span><span class="sxs-lookup"><span data-stu-id="33814-105">A common error is to assume that the end of the table has been reached when:</span></span> 
  
- <span data-ttu-id="33814-106">已在循环中，使用由[IMAPITable::GetRowCount](imapitable-getrowcount.md)返回的行计数循环结束调用[IMAPITable::QueryRows](imapitable-queryrows.md) 。</span><span class="sxs-lookup"><span data-stu-id="33814-106">[IMAPITable::QueryRows](imapitable-queryrows.md) has been called in a loop, with the end of the loop determined by the row count returned by [IMAPITable::GetRowCount](imapitable-getrowcount.md).</span></span> <span data-ttu-id="33814-107">**GetRowCount**返回的计数不始终表示确切的表; 中的行数它是一个大概计数。</span><span class="sxs-lookup"><span data-stu-id="33814-107">The count that **GetRowCount** returns does not always represent the exact number of rows in the table; it is an approximate count.</span></span> 
    
- <span data-ttu-id="33814-108">已使用固定数量的行调用**QueryRows**和返回更少的行。</span><span class="sxs-lookup"><span data-stu-id="33814-108">**QueryRows** has been called with a fixed number of rows and fewer rows are returned.</span></span> <span data-ttu-id="33814-109">它是不是直到**QueryRows**返回的行集与等于零，没有要检索的多个行的行数。</span><span class="sxs-lookup"><span data-stu-id="33814-109">It is not until **QueryRows** returns a row set with a row count equal to zero that there are no more rows to retrieve.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="33814-110">返回 S_OK 的值和零行时，呼叫者可以假定将光标定位末尾的正行计数的表或负数的行数的表的开头的唯一时间。</span><span class="sxs-lookup"><span data-stu-id="33814-110">The only time that a caller can assume that the cursor is positioned at the end of the table for a positive row count or at the beginning of the table for a negative row count is when the value S_OK and zero rows are returned.</span></span> <span data-ttu-id="33814-111">将 MAPI_E_NOT_FOUND 永远不会返回值。</span><span class="sxs-lookup"><span data-stu-id="33814-111">The value MAPI_E_NOT_FOUND is never returned.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="33814-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33814-112">See also</span></span>



[<span data-ttu-id="33814-113">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="33814-113">MAPI Tables</span></span>](mapi-tables.md)

