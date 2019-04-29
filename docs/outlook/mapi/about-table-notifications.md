---
title: 关于表格通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 00c9c6c2-fc21-4b9c-91fa-629450a22d37
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9a42ed1e196e8ac498ab5889b4419ff407db4748
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417950"
---
# <a name="about-table-notifications"></a><span data-ttu-id="ca704-103">关于表格通知</span><span class="sxs-lookup"><span data-stu-id="ca704-103">About Table Notifications</span></span>

  
  
<span data-ttu-id="ca704-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca704-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca704-105">客户端通常依靠表通知来了解对对象的更改, 而不是注册以直接从对象接收通知。</span><span class="sxs-lookup"><span data-stu-id="ca704-105">Clients often rely on table notifications to learn of changes to objects instead of registering to receive notifications directly from the objects.</span></span> <span data-ttu-id="ca704-106">导致发送通知的典型更改包括添加、删除或修改行和任何严重错误。</span><span class="sxs-lookup"><span data-stu-id="ca704-106">Typical changes that cause notifications to be sent include the addition, deletion, or modification of a row and any critical error.</span></span> <span data-ttu-id="ca704-107">当通知到达时, 客户端可以确定是否执行另一个调用来重新加载表。</span><span class="sxs-lookup"><span data-stu-id="ca704-107">When notifications arrive, clients can determine whether to make another call to reload the table.</span></span> 
  
<span data-ttu-id="ca704-108">由于表通知是异步的, 因此有几个问题会导致处理通知不是很简单:</span><span class="sxs-lookup"><span data-stu-id="ca704-108">Because table notifications are asynchronous, there are a few issues that can make handling notifications less than straightforward:</span></span>
  
- <span data-ttu-id="ca704-109">[TABLE_NOTIFICATION](table_notification.md)结构中传递的数据可能不表示表的最新状态。</span><span class="sxs-lookup"><span data-stu-id="ca704-109">The data passed in the [TABLE_NOTIFICATION](table_notification.md) structure might not represent the table's most current state.</span></span> <span data-ttu-id="ca704-110">例如, 客户端可能会对邮件进行更改, 然后决定将其删除。</span><span class="sxs-lookup"><span data-stu-id="ca704-110">For example, a client might make a change to a message and then decide to delete it.</span></span> <span data-ttu-id="ca704-111">实现包含邮件的内容表格的邮件存储提供程序发送两个通知: 一个 TABLE_ROW_MODIFIED 事件, 后跟 TABLE_ROW_DELETED 事件。</span><span class="sxs-lookup"><span data-stu-id="ca704-111">The message store provider implementing the contents table that included the message sends two notifications: a TABLE_ROW_MODIFIED event followed by a TABLE_ROW_DELETED event.</span></span> <span data-ttu-id="ca704-112">根据邮件存储提供程序时间通知的方式, 客户端可能会在删除行后收到 TABLE_ROW_MODIFIED 通知。</span><span class="sxs-lookup"><span data-stu-id="ca704-112">Depending on how the message store provider times notifications, the client might receive the TABLE_ROW_MODIFIED notification after the deletion of the row.</span></span> 
    
- <span data-ttu-id="ca704-113">通知附带的列集可能与表的当前列集不同。</span><span class="sxs-lookup"><span data-stu-id="ca704-113">The column set included with a notification might be different from the table's current column set.</span></span> <span data-ttu-id="ca704-114">MAPI 要求通知列设置与生成通知时有效的列集相匹配。</span><span class="sxs-lookup"><span data-stu-id="ca704-114">MAPI requires that the notification column set match the column set that was in effect at the time that the notification was generated.</span></span> <span data-ttu-id="ca704-115">由于客户端可以调用[IMAPITable:: SetColumns](imapitable-setcolumns.md)以随时更改列集 (包括在通知之后), 因此两列集可能不会同步。</span><span class="sxs-lookup"><span data-stu-id="ca704-115">Because it is possible for a client to call [IMAPITable::SetColumns](imapitable-setcolumns.md) to alter the column set at any time — including after a notification — the two column sets may not be synchronized.</span></span> 
    
- <span data-ttu-id="ca704-116">仅对作为视图一部分的行发送表通知。</span><span class="sxs-lookup"><span data-stu-id="ca704-116">Table notifications are only sent for rows that are part of the view.</span></span> <span data-ttu-id="ca704-117">也就是说, 如果由于限制而从视图中排除某行, 或者表处于折叠状态, 则在该行发生更改时不会发送任何通知。</span><span class="sxs-lookup"><span data-stu-id="ca704-117">That is, if a row is excluded from the view due to a restriction or because the table is in a collapsed state, no notification will be sent if that row changes.</span></span> <span data-ttu-id="ca704-118">此外, 不会发送任何通知, 以通知客户端有关类别状态的更改。</span><span class="sxs-lookup"><span data-stu-id="ca704-118">Also, no notifications are sent to inform a client about a change in category state.</span></span>
    
<span data-ttu-id="ca704-119">客户端应注意, 并非所有表都支持 TABLE_SORT_DONE 通知, 应通过以下方式准备处理此条件:</span><span class="sxs-lookup"><span data-stu-id="ca704-119">Clients should be aware that not all tables support the TABLE_SORT_DONE notification and should be prepared to handle this condition by:</span></span>
  
1. <span data-ttu-id="ca704-120">强制进行排序以进行同步。</span><span class="sxs-lookup"><span data-stu-id="ca704-120">Forcing the sort to be synchronous.</span></span>
    
2. <span data-ttu-id="ca704-121">在[IMAPITable:: SortTable](imapitable-sorttable.md)返回时重新加载表的行。</span><span class="sxs-lookup"><span data-stu-id="ca704-121">Reloading the rows of the table when [IMAPITable::SortTable](imapitable-sorttable.md) returns.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="ca704-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca704-122">See also</span></span>



[<span data-ttu-id="ca704-123">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="ca704-123">MAPI Tables</span></span>](mapi-tables.md)

