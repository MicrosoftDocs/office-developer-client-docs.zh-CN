---
title: 设置列和限制后排序表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57db0314-1df0-4fd2-b443-223b0512f1ad
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9e75143cb59e782993b9a7f9937432f0b4894d5f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778857"
---
# <a name="sorting-tables-after-setting-columns-and-restrictions"></a><span data-ttu-id="63ab8-103">设置列和限制后排序表</span><span class="sxs-lookup"><span data-stu-id="63ab8-103">Sorting Tables After Setting Columns and Restrictions</span></span>

  
  
<span data-ttu-id="63ab8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="63ab8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="63ab8-105">当您需要限制排序的表的视图时，请始终按以下顺序进行以下**IMAPITable**呼叫：</span><span class="sxs-lookup"><span data-stu-id="63ab8-105">When you need to limit the view of a sorted table, always make the following **IMAPITable** calls in the following order:</span></span> 
  
1. <span data-ttu-id="63ab8-106">[IMAPITable::SetColumns](imapitable-setcolumns.md)定义列设置。</span><span class="sxs-lookup"><span data-stu-id="63ab8-106">[IMAPITable::SetColumns](imapitable-setcolumns.md) to define the column set.</span></span> 
    
2. <span data-ttu-id="63ab8-107">[IMAPITable::Restrict](imapitable-restrict.md)施加限制。</span><span class="sxs-lookup"><span data-stu-id="63ab8-107">[IMAPITable::Restrict](imapitable-restrict.md) to impose the restriction.</span></span> 
    
3. <span data-ttu-id="63ab8-108">[IMAPITable::SortTable](imapitable-sorttable.md)执行排序。</span><span class="sxs-lookup"><span data-stu-id="63ab8-108">[IMAPITable::SortTable](imapitable-sorttable.md) to perform the sort.</span></span> 
    
<span data-ttu-id="63ab8-109">如果归类排序的表，向发起呼叫[IMAPITable::SetCollapseState](imapitable-setcollapsestate.md)，如有必要之后**SortTable**呼叫。</span><span class="sxs-lookup"><span data-stu-id="63ab8-109">If the sorted table is categorized, make a call to [IMAPITable::SetCollapseState](imapitable-setcollapsestate.md), if necessary, after the **SortTable** call.</span></span> <span data-ttu-id="63ab8-110">此呼叫的顺序很重要，因为大多数服务提供商表格进行排序作为最后一项任务以实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="63ab8-110">This ordering of calls is important because most service providers sort a table as the last task to achieve the best performance.</span></span> <span data-ttu-id="63ab8-111">如果，例如，消息存储提供程序必须分类文件夹内容表之前可以施加限制，将该限制的处理过程中删除此分类。</span><span class="sxs-lookup"><span data-stu-id="63ab8-111">If, for example, a message store provider must categorize a folder contents table before a restriction can be imposed, this categorization will be removed during the processing of the restriction.</span></span> <span data-ttu-id="63ab8-112">第二个分类是必需的。</span><span class="sxs-lookup"><span data-stu-id="63ab8-112">A second categorization will be necessary.</span></span> 
  

