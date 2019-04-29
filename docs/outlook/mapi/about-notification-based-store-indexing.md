---
title: 关于基于通知的存储索引
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: b3685890-117c-9acc-e19f-cf22a349a088
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3dd551dd0c1ea229381e5dd01c5cf6fa04790c30
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409172"
---
# <a name="about-notification-based-store-indexing"></a><span data-ttu-id="393ca-103">关于基于通知的存储索引</span><span class="sxs-lookup"><span data-stu-id="393ca-103">About Notification-Based Store Indexing</span></span>

  
  
<span data-ttu-id="393ca-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="393ca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="393ca-105">mapi 存储提供程序可以指定 mapi 协议处理程序是在存储中对邮件进行爬网, 还是在有要编制索引的邮件时, 存储是否向索引器发送通知。</span><span class="sxs-lookup"><span data-stu-id="393ca-105">A MAPI store provider can specify whether the MAPI Protocol Handler crawls and indexes messages in the store, or whether the store sends notifications to the indexer when there are messages to be indexed.</span></span> <span data-ttu-id="393ca-106">后者称为基于通知的索引, 并且支持基于通知的索引的存储是一个称为 pusher 存储的存储。</span><span class="sxs-lookup"><span data-stu-id="393ca-106">The latter is known as notification-based indexing, and a store that supports notification-based indexing is a known as a pusher store.</span></span>
  
<span data-ttu-id="393ca-107">支持基于通知的索引的存储提供程序设置**[PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** 属性中的**STORE_PUSHER_OK**标志。</span><span class="sxs-lookup"><span data-stu-id="393ca-107">A store provider that supports notification-based indexing sets the **STORE_PUSHER_OK** flag in the **[PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** property.</span></span> <span data-ttu-id="393ca-108">MAPI 协议处理程序或客户端可以获取**PR_STORE_SUPPORT_MASK**属性来确定存储区的特征。</span><span class="sxs-lookup"><span data-stu-id="393ca-108">The MAPI Protocol Handler or a client can get the **PR_STORE_SUPPORT_MASK** property to determine the characteristics of the store.</span></span> 
  
<span data-ttu-id="393ca-109">只要有要编制索引的附件、文件夹或邮件, 存储提供程序就会生成一个 MAPI 统一资源定位器 (URL), 用于标识要编制索引的对象并将其发送到索引器。</span><span class="sxs-lookup"><span data-stu-id="393ca-109">Whenever there is an attachment, folder, or a message to be indexed, the store provider generates a MAPI Uniform Resource Locator (URL) identifying the object to be indexed and sends it to the indexer.</span></span> <span data-ttu-id="393ca-110">此 MAPI URL 采用 Unicode 编码, 并且必须唯一地将对象标识为 MAPI 协议处理程序。</span><span class="sxs-lookup"><span data-stu-id="393ca-110">This MAPI URL is encoded in Unicode and must uniquely identify the object to the MAPI Protocol Handler.</span></span> <span data-ttu-id="393ca-111">有关 mapi url 的详细信息, 请参阅[关于基于通知的索引的 mapi url](about-mapi-urls-for-notification-based-indexing.md)。</span><span class="sxs-lookup"><span data-stu-id="393ca-111">For more information about MAPI URLs, see [About MAPI URLs for Notification-Based Indexing](about-mapi-urls-for-notification-based-indexing.md).</span></span>
  
<span data-ttu-id="393ca-112">由于索引器在 pusher 存储中发生关闭之前不能始终为所有内容编制索引, 因此 pusher 存储必须保留所需推送的内容。</span><span class="sxs-lookup"><span data-stu-id="393ca-112">Because an indexer cannot always index everything before a shutdown occurs in a pusher store, the pusher store must persist what needs to be pushed.</span></span> <span data-ttu-id="393ca-113">当存储提供程序发送有关需要编制索引的对象的通知时, 它会在**[通知](notification.md)** 结构的**ulEventType**成员中指定通知类型**fnevIndexing** 。</span><span class="sxs-lookup"><span data-stu-id="393ca-113">When a store provider sends a notification about an object that needs to be indexed, it specifies the notification type **fnevIndexing** in the **ulEventType** member of the **[NOTIFICATION](notification.md)** structure.</span></span> <span data-ttu-id="393ca-114">**通知**结构的 **info** 成员包含 **[EXTENDED_NOTIFICATION](extended_notification.md)** 结构。</span><span class="sxs-lookup"><span data-stu-id="393ca-114">The **info** member of the **NOTIFICATION** structure contains an **[EXTENDED_NOTIFICATION](extended_notification.md)** structure.</span></span> <span data-ttu-id="393ca-115">存储提供程序在**[PR_SEARCH_OWNER_ID](pidtagsearchownerid-canonical-property.md)** 属性中标识进程。</span><span class="sxs-lookup"><span data-stu-id="393ca-115">The store provider identifies the process in the **[PR_SEARCH_OWNER_ID](pidtagsearchownerid-canonical-property.md)** property.</span></span> <span data-ttu-id="393ca-116">它还标识[INDEX_SEARCH_PUSHER_PROCESS](index_search_pusher_process.md)结构中的进程, 并将此信息作为**EXTENDED_NOTIFICATION**结构的**pbEventParameters**成员的一部分传递。</span><span class="sxs-lookup"><span data-stu-id="393ca-116">It also identifies the process in the [INDEX_SEARCH_PUSHER_PROCESS](index_search_pusher_process.md) structure, and passes this information as part of the **pbEventParameters** member of the **EXTENDED_NOTIFICATION** structure.</span></span> <span data-ttu-id="393ca-117">如果进程关闭或崩溃, MAPI 协议处理程序将能够立即检测到该进程并停止对 pusher 存储库进行索引。</span><span class="sxs-lookup"><span data-stu-id="393ca-117">If the process is shut down or crashes, the MAPI Protocol Handler will be able to immediately detect that and stop indexing the pusher store.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="393ca-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="393ca-118">See also</span></span>



[<span data-ttu-id="393ca-119">关于存储 API</span><span class="sxs-lookup"><span data-stu-id="393ca-119">About the Store API</span></span>](about-the-store-api.md)
  
[<span data-ttu-id="393ca-120">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="393ca-120">MAPI Constants</span></span>](mapi-constants.md)

