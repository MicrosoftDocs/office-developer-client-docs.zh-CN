---
title: 默认邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: efa178eb-feb2-443f-8f6b-2ea53a456bf2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3f7bf720f9105f6a81b832233cc648bc1d9ac91d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576909"
---
# <a name="default-message-stores"></a><span data-ttu-id="8e076-103">默认邮件存储</span><span class="sxs-lookup"><span data-stu-id="8e076-103">Default Message Stores</span></span>

  
  
<span data-ttu-id="8e076-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8e076-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8e076-105">默认邮件存储是客户端应用程序可将其用于通用邮件任务的存储。</span><span class="sxs-lookup"><span data-stu-id="8e076-105">A default message store is one that client applications can use for general purpose messaging tasks.</span></span> <span data-ttu-id="8e076-106">如果要将邮件存储提供程序用作默认邮件存储，则邮件存储提供程序的许多可选功能将变为必需功能。</span><span class="sxs-lookup"><span data-stu-id="8e076-106">There are a number of optional features for message store providers that become required if the message store provider is to be used as the default message store.</span></span> <span data-ttu-id="8e076-107">它们是：</span><span class="sxs-lookup"><span data-stu-id="8e076-107">They are as follows:</span></span>
  
- <span data-ttu-id="8e076-108">实现特殊文件夹：收件箱、发件箱和搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="8e076-108">Implementing the special folders: the Inbox, Outbox, and search-results folders.</span></span>
    
- <span data-ttu-id="8e076-109">提供已读和未读报表。</span><span class="sxs-lookup"><span data-stu-id="8e076-109">Providing read and nonread reports for message store providers</span></span>
    
- <span data-ttu-id="8e076-110">允许提交传入和待发邮件。</span><span class="sxs-lookup"><span data-stu-id="8e076-110">Allowing incoming and outgoing message submissions.</span></span>
    
- <span data-ttu-id="8e076-111">允许创建任意邮件类别的邮件。</span><span class="sxs-lookup"><span data-stu-id="8e076-111">Allowing the creation of messages with arbitrary message classes.</span></span>
    
- <span data-ttu-id="8e076-112">支持命名和多值属性。</span><span class="sxs-lookup"><span data-stu-id="8e076-112">Supporting named and multiple-value properties.</span></span>
    
- <span data-ttu-id="8e076-113">支持 [IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md) 方法，即使邮件存储提供程序与传输提供程序紧密耦合。</span><span class="sxs-lookup"><span data-stu-id="8e076-113">Supporting the [IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md) method, even if the message store provider is tightly coupled with a transport provider.</span></span> 
    
- <span data-ttu-id="8e076-114">支持相关的内容表。</span><span class="sxs-lookup"><span data-stu-id="8e076-114">Supporting associated contents tables.</span></span> <span data-ttu-id="8e076-115">有关详细信息，请参阅[内容表](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="8e076-115">For more information, see [Contents Tables](contents-tables.md).</span></span>
    
- <span data-ttu-id="8e076-116">当待发邮件队列中有邮件时，支持 MAPI 后台处理程序通知。</span><span class="sxs-lookup"><span data-stu-id="8e076-116">Supporting notification of the MAPI spooler when there are messages in the outgoing message queue.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8e076-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e076-117">See also</span></span>



[<span data-ttu-id="8e076-118">开发 MAPI 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="8e076-118">Developing a MAPI message store provider</span></span>](developing-a-mapi-message-store-provider.md)

