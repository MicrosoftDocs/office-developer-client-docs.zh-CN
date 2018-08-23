---
title: 默认邮件存储区
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: efa178eb-feb2-443f-8f6b-2ea53a456bf2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3f7bf720f9105f6a81b832233cc648bc1d9ac91d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576909"
---
# <a name="default-message-stores"></a><span data-ttu-id="83696-103">默认邮件存储区</span><span class="sxs-lookup"><span data-stu-id="83696-103">Default Message Stores</span></span>

  
  
<span data-ttu-id="83696-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="83696-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="83696-105">默认邮件存储区是一种客户端应用程序可用于通用消息任务。</span><span class="sxs-lookup"><span data-stu-id="83696-105">A default message store is one that client applications can use for general purpose messaging tasks.</span></span> <span data-ttu-id="83696-106">有大量的消息存储提供程序用作默认的邮件存储的消息存储提供程序是否成为所需的可选功能。</span><span class="sxs-lookup"><span data-stu-id="83696-106">There are a number of optional features for message store providers that become required if the message store provider is to be used as the default message store.</span></span> <span data-ttu-id="83696-107">他们如下所示：</span><span class="sxs-lookup"><span data-stu-id="83696-107">They are as follows:</span></span>
  
- <span data-ttu-id="83696-108">实现的特殊文件夹： 收件箱、 发件箱和搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="83696-108">Implementing the special folders: the Inbox, Outbox, and search-results folders.</span></span>
    
- <span data-ttu-id="83696-109">提供读取和 nonread 报告。</span><span class="sxs-lookup"><span data-stu-id="83696-109">Providing read and nonread reports.</span></span>
    
- <span data-ttu-id="83696-110">允许传入和传出邮件提交。</span><span class="sxs-lookup"><span data-stu-id="83696-110">Allowing incoming and outgoing message submissions.</span></span>
    
- <span data-ttu-id="83696-111">允许与任意邮件类的消息的创建。</span><span class="sxs-lookup"><span data-stu-id="83696-111">Allowing the creation of messages with arbitrary message classes.</span></span>
    
- <span data-ttu-id="83696-112">支持的名为和多值属性。</span><span class="sxs-lookup"><span data-stu-id="83696-112">Supporting named and multiple-value properties.</span></span>
    
- <span data-ttu-id="83696-113">即使与传输提供程序紧密耦合的消息存储提供程序支持的[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)方法。</span><span class="sxs-lookup"><span data-stu-id="83696-113">Supporting the [IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md) method, even if the message store provider is tightly coupled with a transport provider.</span></span> 
    
- <span data-ttu-id="83696-114">支持表关联的内容。</span><span class="sxs-lookup"><span data-stu-id="83696-114">Supporting associated contents tables.</span></span> <span data-ttu-id="83696-115">有关详细信息，请参阅[内容表](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="83696-115">For more information, see [Contents Tables](contents-tables.md).</span></span>
    
- <span data-ttu-id="83696-116">传出的邮件队列中邮件时，支持 MAPI 后台处理程序的通知。</span><span class="sxs-lookup"><span data-stu-id="83696-116">Supporting notification of the MAPI spooler when there are messages in the outgoing message queue.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="83696-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83696-117">See also</span></span>



[<span data-ttu-id="83696-118">开发 MAPI 邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="83696-118">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

