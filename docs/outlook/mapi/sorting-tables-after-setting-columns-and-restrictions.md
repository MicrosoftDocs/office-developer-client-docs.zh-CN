---
title: 设置列和限制后对表进行排序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 57db0314-1df0-4fd2-b443-223b0512f1ad
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 62220794f325165e67db5397da2795d49959ef60
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409879"
---
# <a name="sorting-tables-after-setting-columns-and-restrictions"></a><span data-ttu-id="431b1-103">设置列和限制后对表进行排序</span><span class="sxs-lookup"><span data-stu-id="431b1-103">Sorting Tables After Setting Columns and Restrictions</span></span>

  
  
<span data-ttu-id="431b1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="431b1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="431b1-105">当需要限制已排序表的视图时，请始终按以下顺序进行 **以下 IMAPITable** 调用：</span><span class="sxs-lookup"><span data-stu-id="431b1-105">When you need to limit the view of a sorted table, always make the following **IMAPITable** calls in the following order:</span></span> 
  
1. <span data-ttu-id="431b1-106">[用于定义列集的 IMAPITable：：SetColumns。](imapitable-setcolumns.md)</span><span class="sxs-lookup"><span data-stu-id="431b1-106">[IMAPITable::SetColumns](imapitable-setcolumns.md) to define the column set.</span></span> 
    
2. <span data-ttu-id="431b1-107">[IMAPITable：：Restrict](imapitable-restrict.md) 施加限制。</span><span class="sxs-lookup"><span data-stu-id="431b1-107">[IMAPITable::Restrict](imapitable-restrict.md) to impose the restriction.</span></span> 
    
3. <span data-ttu-id="431b1-108">[IMAPITable：：SortTable](imapitable-sorttable.md) 以执行排序。</span><span class="sxs-lookup"><span data-stu-id="431b1-108">[IMAPITable::SortTable](imapitable-sorttable.md) to perform the sort.</span></span> 
    
<span data-ttu-id="431b1-109">如果已排序表已分类，则在必要时在 **SortTable** 调用后调用 [IMAPITable：：SetCollapseState。](imapitable-setcollapsestate.md)</span><span class="sxs-lookup"><span data-stu-id="431b1-109">If the sorted table is categorized, make a call to [IMAPITable::SetCollapseState](imapitable-setcollapsestate.md), if necessary, after the **SortTable** call.</span></span> <span data-ttu-id="431b1-110">这种调用顺序非常重要，因为大多数服务提供商将表排序为实现最佳性能的最后一项任务。</span><span class="sxs-lookup"><span data-stu-id="431b1-110">This ordering of calls is important because most service providers sort a table as the last task to achieve the best performance.</span></span> <span data-ttu-id="431b1-111">例如，如果邮件存储提供程序必须对文件夹内容表进行分类，然后才能施加限制，则在处理限制期间将移除此分类。</span><span class="sxs-lookup"><span data-stu-id="431b1-111">If, for example, a message store provider must categorize a folder contents table before a restriction can be imposed, this categorization will be removed during the processing of the restriction.</span></span> <span data-ttu-id="431b1-112">需要第二个分类。</span><span class="sxs-lookup"><span data-stu-id="431b1-112">A second categorization will be necessary.</span></span> 
  

