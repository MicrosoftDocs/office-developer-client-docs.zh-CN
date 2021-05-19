---
title: 关于表通知
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
# <a name="about-table-notifications"></a><span data-ttu-id="cab78-103">关于表通知</span><span class="sxs-lookup"><span data-stu-id="cab78-103">About Table Notifications</span></span>

  
  
<span data-ttu-id="cab78-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cab78-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cab78-105">客户端通常依赖表通知来了解对对象的更改，而不是注册以直接从对象接收通知。</span><span class="sxs-lookup"><span data-stu-id="cab78-105">Clients often rely on table notifications to learn of changes to objects instead of registering to receive notifications directly from the objects.</span></span> <span data-ttu-id="cab78-106">导致发送通知的典型更改包括添加、删除或修改行以及任何关键错误。</span><span class="sxs-lookup"><span data-stu-id="cab78-106">Typical changes that cause notifications to be sent include the addition, deletion, or modification of a row and any critical error.</span></span> <span data-ttu-id="cab78-107">通知到达后，客户端可以确定是否进行其他调用以重新加载表。</span><span class="sxs-lookup"><span data-stu-id="cab78-107">When notifications arrive, clients can determine whether to make another call to reload the table.</span></span> 
  
<span data-ttu-id="cab78-108">由于表通知是异步的，因此存在一些问题，这些问题会使处理通知不如简单：</span><span class="sxs-lookup"><span data-stu-id="cab78-108">Because table notifications are asynchronous, there are a few issues that can make handling notifications less than straightforward:</span></span>
  
- <span data-ttu-id="cab78-109">在数据 [TABLE_NOTIFICATION中传递](table_notification.md) 的数据可能并不代表表的最近状态。</span><span class="sxs-lookup"><span data-stu-id="cab78-109">The data passed in the [TABLE_NOTIFICATION](table_notification.md) structure might not represent the table's most current state.</span></span> <span data-ttu-id="cab78-110">例如，客户端可能会更改邮件，然后决定将其删除。</span><span class="sxs-lookup"><span data-stu-id="cab78-110">For example, a client might make a change to a message and then decide to delete it.</span></span> <span data-ttu-id="cab78-111">实现包含邮件的内容表的邮件存储提供程序发送两个通知：一个 TABLE_ROW_MODIFIED 事件，后跟一个 TABLE_ROW_DELETED 事件。</span><span class="sxs-lookup"><span data-stu-id="cab78-111">The message store provider implementing the contents table that included the message sends two notifications: a TABLE_ROW_MODIFIED event followed by a TABLE_ROW_DELETED event.</span></span> <span data-ttu-id="cab78-112">根据邮件存储提供程序通知时间，客户端在删除行TABLE_ROW_MODIFIED可能会收到通知。</span><span class="sxs-lookup"><span data-stu-id="cab78-112">Depending on how the message store provider times notifications, the client might receive the TABLE_ROW_MODIFIED notification after the deletion of the row.</span></span> 
    
- <span data-ttu-id="cab78-113">通知中包含的列集可能不同于表的当前列集。</span><span class="sxs-lookup"><span data-stu-id="cab78-113">The column set included with a notification might be different from the table's current column set.</span></span> <span data-ttu-id="cab78-114">MAPI 要求通知列集与生成通知时生效的列集匹配。</span><span class="sxs-lookup"><span data-stu-id="cab78-114">MAPI requires that the notification column set match the column set that was in effect at the time that the notification was generated.</span></span> <span data-ttu-id="cab78-115">由于客户端可能随时（包括通知后）调用 [IMAPITable：：SetColumns](imapitable-setcolumns.md) 来更改列集，因此这两个列集可能不会同步。</span><span class="sxs-lookup"><span data-stu-id="cab78-115">Because it is possible for a client to call [IMAPITable::SetColumns](imapitable-setcolumns.md) to alter the column set at any time — including after a notification — the two column sets may not be synchronized.</span></span> 
    
- <span data-ttu-id="cab78-116">仅对属于视图的行发送表通知。</span><span class="sxs-lookup"><span data-stu-id="cab78-116">Table notifications are only sent for rows that are part of the view.</span></span> <span data-ttu-id="cab78-117">也就是说，如果由于限制或表为折叠状态而从视图中排除行，则该行更改时不会发送通知。</span><span class="sxs-lookup"><span data-stu-id="cab78-117">That is, if a row is excluded from the view due to a restriction or because the table is in a collapsed state, no notification will be sent if that row changes.</span></span> <span data-ttu-id="cab78-118">此外，不会发送通知来通知客户端类别状态的变化。</span><span class="sxs-lookup"><span data-stu-id="cab78-118">Also, no notifications are sent to inform a client about a change in category state.</span></span>
    
<span data-ttu-id="cab78-119">客户端应注意，并非所有表都支持TABLE_SORT_DONE通知，并且应准备通过以下操作来处理此情况：</span><span class="sxs-lookup"><span data-stu-id="cab78-119">Clients should be aware that not all tables support the TABLE_SORT_DONE notification and should be prepared to handle this condition by:</span></span>
  
1. <span data-ttu-id="cab78-120">强制排序为同步。</span><span class="sxs-lookup"><span data-stu-id="cab78-120">Forcing the sort to be synchronous.</span></span>
    
2. <span data-ttu-id="cab78-121">当 [IMAPITable：：SortTable 返回时重新加载表的](imapitable-sorttable.md) 行。</span><span class="sxs-lookup"><span data-stu-id="cab78-121">Reloading the rows of the table when [IMAPITable::SortTable](imapitable-sorttable.md) returns.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="cab78-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cab78-122">See also</span></span>



[<span data-ttu-id="cab78-123">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="cab78-123">MAPI Tables</span></span>](mapi-tables.md)

