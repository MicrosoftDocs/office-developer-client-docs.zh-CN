---
title: 关于表通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 00c9c6c2-fc21-4b9c-91fa-629450a22d37
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d6fd49e1a004202e0de02e262f6977ca8a07019d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571939"
---
# <a name="about-table-notifications"></a><span data-ttu-id="594f5-103">关于表通知</span><span class="sxs-lookup"><span data-stu-id="594f5-103">About Table Notifications</span></span>

  
  
<span data-ttu-id="594f5-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="594f5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="594f5-105">客户端通常依靠表通知，若要了解的而不是注册直接从对象接收通知的对象更改。</span><span class="sxs-lookup"><span data-stu-id="594f5-105">Clients often rely on table notifications to learn of changes to objects instead of registering to receive notifications directly from the objects.</span></span> <span data-ttu-id="594f5-106">导致发送通知的典型更改包括添加、 删除或修改的行和任何错误。</span><span class="sxs-lookup"><span data-stu-id="594f5-106">Typical changes that cause notifications to be sent include the addition, deletion, or modification of a row and any critical error.</span></span> <span data-ttu-id="594f5-107">当到达通知时，客户端可以确定是进行重新加载表的另一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="594f5-107">When notifications arrive, clients can determine whether to make another call to reload the table.</span></span> 
  
<span data-ttu-id="594f5-108">表通知是异步的因为有可以处理通知小于变得非常简单的几个问题：</span><span class="sxs-lookup"><span data-stu-id="594f5-108">Because table notifications are asynchronous, there are a few issues that can make handling notifications less than straightforward:</span></span>
  
- <span data-ttu-id="594f5-109">传递[TABLE_NOTIFICATION](table_notification.md)结构中的数据不能表示表的最新状态。</span><span class="sxs-lookup"><span data-stu-id="594f5-109">The data passed in the [TABLE_NOTIFICATION](table_notification.md) structure might not represent the table's most current state.</span></span> <span data-ttu-id="594f5-110">例如，客户端可能更改了一条消息，然后确定可将其删除。</span><span class="sxs-lookup"><span data-stu-id="594f5-110">For example, a client might make a change to a message and then decide to delete it.</span></span> <span data-ttu-id="594f5-111">消息存储提供程序实现的内容表包含邮件的发送两个通知： TABLE_ROW_MODIFIED 事件后跟 TABLE_ROW_DELETED 事件。</span><span class="sxs-lookup"><span data-stu-id="594f5-111">The message store provider implementing the contents table that included the message sends two notifications: a TABLE_ROW_MODIFIED event followed by a TABLE_ROW_DELETED event.</span></span> <span data-ttu-id="594f5-112">如何消息存储提供程序时间通知，根据客户端可能会收到 TABLE_ROW_MODIFIED 通知后删除的行。</span><span class="sxs-lookup"><span data-stu-id="594f5-112">Depending on how the message store provider times notifications, the client might receive the TABLE_ROW_MODIFIED notification after the deletion of the row.</span></span> 
    
- <span data-ttu-id="594f5-113">设置包含在通知的列可能不同于表的当前列组。</span><span class="sxs-lookup"><span data-stu-id="594f5-113">The column set included with a notification might be different from the table's current column set.</span></span> <span data-ttu-id="594f5-114">MAPI 需要通知列组匹配列集已在生成通知的时间起作用。</span><span class="sxs-lookup"><span data-stu-id="594f5-114">MAPI requires that the notification column set match the column set that was in effect at the time that the notification was generated.</span></span> <span data-ttu-id="594f5-115">因为可能为客户端调用[IMAPITable::SetColumns](imapitable-setcolumns.md)更改随时设置列 — 包括通知之后 — 可能不同步的两列集。</span><span class="sxs-lookup"><span data-stu-id="594f5-115">Because it is possible for a client to call [IMAPITable::SetColumns](imapitable-setcolumns.md) to alter the column set at any time — including after a notification — the two column sets may not be synchronized.</span></span> 
    
- <span data-ttu-id="594f5-116">表通知仅发送是视图的一部分的行。</span><span class="sxs-lookup"><span data-stu-id="594f5-116">Table notifications are only sent for rows that are part of the view.</span></span> <span data-ttu-id="594f5-117">即如果由于限制视图从排除行或表处于折叠状态，因此，如果该行更改将会不发送任何通知。</span><span class="sxs-lookup"><span data-stu-id="594f5-117">That is, if a row is excluded from the view due to a restriction or because the table is in a collapsed state, no notification will be sent if that row changes.</span></span> <span data-ttu-id="594f5-118">此外，不发送任何通知类别状态更改通知客户端。</span><span class="sxs-lookup"><span data-stu-id="594f5-118">Also, no notifications are sent to inform a client about a change in category state.</span></span>
    
<span data-ttu-id="594f5-119">客户端应请注意，不是所有表支持 TABLE_SORT_DONE 通知，应做好处理通过这种情况：</span><span class="sxs-lookup"><span data-stu-id="594f5-119">Clients should be aware that not all tables support the TABLE_SORT_DONE notification and should be prepared to handle this condition by:</span></span>
  
1. <span data-ttu-id="594f5-120">强制要同步的排序。</span><span class="sxs-lookup"><span data-stu-id="594f5-120">Forcing the sort to be synchronous.</span></span>
    
2. <span data-ttu-id="594f5-121">[IMAPITable::SortTable](imapitable-sorttable.md)返回时，重新加载 table 的行。</span><span class="sxs-lookup"><span data-stu-id="594f5-121">Reloading the rows of the table when [IMAPITable::SortTable](imapitable-sorttable.md) returns.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="594f5-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="594f5-122">See also</span></span>



[<span data-ttu-id="594f5-123">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="594f5-123">MAPI Tables</span></span>](mapi-tables.md)

