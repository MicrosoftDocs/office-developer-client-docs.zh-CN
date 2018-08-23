---
title: 关于基于通知的存储区索引
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: b3685890-117c-9acc-e19f-cf22a349a088
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 125147ed7d6cd90c1069aa5cc1c759abe752dfe2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564519"
---
# <a name="about-notification-based-store-indexing"></a><span data-ttu-id="91ac8-103">关于基于通知的存储区索引</span><span class="sxs-lookup"><span data-stu-id="91ac8-103">About Notification-Based Store Indexing</span></span>

  
  
<span data-ttu-id="91ac8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="91ac8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="91ac8-105">MAPI 存储提供程序可以指定的 MAPI 协议处理程序爬网和索引是否消息在存储中，或存储是否要编制索引的邮件时将通知发送到索引器。</span><span class="sxs-lookup"><span data-stu-id="91ac8-105">A MAPI store provider can specify whether the MAPI Protocol Handler crawls and indexes messages in the store, or whether the store sends notifications to the indexer when there are messages to be indexed.</span></span> <span data-ttu-id="91ac8-106">后者称为基于通知的索引，并且支持基于通知的索引的存储，称为 pusher 存储区。</span><span class="sxs-lookup"><span data-stu-id="91ac8-106">The latter is known as notification-based indexing, and a store that supports notification-based indexing is a known as a pusher store.</span></span>
  
<span data-ttu-id="91ac8-107">支持基于通知的索引集**STORE_PUSHER_OK**标志**[PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** 属性中存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="91ac8-107">A store provider that supports notification-based indexing sets the **STORE_PUSHER_OK** flag in the **[PR_STORE_SUPPORT_MASK](pidtagstoresupportmask-canonical-property.md)** property.</span></span> <span data-ttu-id="91ac8-108">MAPI 协议处理程序或客户端可以获取**PR_STORE_SUPPORT_MASK**属性，以确定存储的特征。</span><span class="sxs-lookup"><span data-stu-id="91ac8-108">The MAPI Protocol Handler or a client can get the **PR_STORE_SUPPORT_MASK** property to determine the characteristics of the store.</span></span> 
  
<span data-ttu-id="91ac8-109">每当附件、 文件夹或要编制索引的消息，存储提供程序生成 MAPI 统一资源定位器 (URL) 标识对象编制索引，并将其发送到索引器。</span><span class="sxs-lookup"><span data-stu-id="91ac8-109">Whenever there is an attachment, folder, or a message to be indexed, the store provider generates a MAPI Uniform Resource Locator (URL) identifying the object to be indexed and sends it to the indexer.</span></span> <span data-ttu-id="91ac8-110">此 MAPI URL 以 Unicode 编码，必须唯一标识到 MAPI 协议处理程序的对象。</span><span class="sxs-lookup"><span data-stu-id="91ac8-110">This MAPI URL is encoded in Unicode and must uniquely identify the object to the MAPI Protocol Handler.</span></span> <span data-ttu-id="91ac8-111">有关 MAPI Url 的详细信息，请参阅[有关基于通知索引 MAPI Url](about-mapi-urls-for-notification-based-indexing.md)。</span><span class="sxs-lookup"><span data-stu-id="91ac8-111">For more information about MAPI URLs, see [About MAPI URLs for Notification-Based Indexing](about-mapi-urls-for-notification-based-indexing.md).</span></span>
  
<span data-ttu-id="91ac8-112">索引器始终不能索引所有内容之前关闭发生 pusher 存储区中，因为 pusher 存储必须保留需要推送。</span><span class="sxs-lookup"><span data-stu-id="91ac8-112">Because an indexer cannot always index everything before a shutdown occurs in a pusher store, the pusher store must persist what needs to be pushed.</span></span> <span data-ttu-id="91ac8-113">存储提供程序发送通知有关需要编制索引的对象，它在**[通知](notification.md)** 结构的**ulEventType**成员指定通知类型**fnevIndexing** 。</span><span class="sxs-lookup"><span data-stu-id="91ac8-113">When a store provider sends a notification about an object that needs to be indexed, it specifies the notification type **fnevIndexing** in the **ulEventType** member of the **[NOTIFICATION](notification.md)** structure.</span></span> <span data-ttu-id="91ac8-114">**通知**结构的**信息**成员包含**[EXTENDED_NOTIFICATION](extended_notification.md)** 结构。</span><span class="sxs-lookup"><span data-stu-id="91ac8-114">The **info** member of the **NOTIFICATION** structure contains an **[EXTENDED_NOTIFICATION](extended_notification.md)** structure.</span></span> <span data-ttu-id="91ac8-115">存储提供程序标识的**[PR_SEARCH_OWNER_ID](pidtagsearchownerid-canonical-property.md)** 属性中的过程。</span><span class="sxs-lookup"><span data-stu-id="91ac8-115">The store provider identifies the process in the **[PR_SEARCH_OWNER_ID](pidtagsearchownerid-canonical-property.md)** property.</span></span> <span data-ttu-id="91ac8-116">它还标识[INDEX_SEARCH_PUSHER_PROCESS](index_search_pusher_process.md)结构中的过程，并将此信息传递的**pbEventParameters**成员**EXTENDED_NOTIFICATION**结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="91ac8-116">It also identifies the process in the [INDEX_SEARCH_PUSHER_PROCESS](index_search_pusher_process.md) structure, and passes this information as part of the **pbEventParameters** member of the **EXTENDED_NOTIFICATION** structure.</span></span> <span data-ttu-id="91ac8-117">如果进程关闭或崩溃时，将能够立即检测，并停止索引 pusher 存储 MAPI 协议处理程序。</span><span class="sxs-lookup"><span data-stu-id="91ac8-117">If the process is shut down or crashes, the MAPI Protocol Handler will be able to immediately detect that and stop indexing the pusher store.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="91ac8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91ac8-118">See also</span></span>



[<span data-ttu-id="91ac8-119">关于存储区 API</span><span class="sxs-lookup"><span data-stu-id="91ac8-119">About the Store API</span></span>](about-the-store-api.md)
  
[<span data-ttu-id="91ac8-120">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="91ac8-120">MAPI Constants</span></span>](mapi-constants.md)

