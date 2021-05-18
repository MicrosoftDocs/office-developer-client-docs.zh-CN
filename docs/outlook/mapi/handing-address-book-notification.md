---
title: 处理通讯簿通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0dc4bb48-c8a1-447f-9e38-1c234a358fca
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 122e50328272a4009e5a129233d449613817dfc8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413533"
---
# <a name="handing-address-book-notification"></a><span data-ttu-id="b1a32-103">处理通讯簿通知</span><span class="sxs-lookup"><span data-stu-id="b1a32-103">Handing address book notification</span></span>
  
<span data-ttu-id="b1a32-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b1a32-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b1a32-105">通讯簿通知允许客户端了解任何通讯簿条目或特定条目所发生事件。</span><span class="sxs-lookup"><span data-stu-id="b1a32-105">Address book notifications allow a client to learn of events that occur to any address book entry or to a particular entry.</span></span> <span data-ttu-id="b1a32-106">可以通过调用 [IAddrBook：：Advise，](iaddrbook-advise.md) 或者通过通讯簿容器的层次结构或内容表（通过 [调用 IMAPITable：：Advise）通过 MAPI](imapitable-advise.md)通讯簿注册这些通知。</span><span class="sxs-lookup"><span data-stu-id="b1a32-106">You can register for these notifications either through the MAPI address book by calling [IAddrBook::Advise](iaddrbook-advise.md) or through an address book container's hierarchy or contents table by calling [IMAPITable::Advise](imapitable-advise.md).</span></span> 
  
<span data-ttu-id="b1a32-107">如果要注册特定条目上的通知，请指定通讯簿容器、通讯组列表或邮件用户的条目标识符;如果注册整个通讯簿上的通知，则指定 NULL。</span><span class="sxs-lookup"><span data-stu-id="b1a32-107">Specify the entry identifier of an address book container, distribution list, or messaging user if you are registering for notifications on a particular entry and NULL if registering for notifications on the entire address book.</span></span> <span data-ttu-id="b1a32-108">条目标识符必须表示通讯簿容器中的邮件用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b1a32-108">The entry identifier must represent a messaging user or distribution list in an address book container.</span></span> <span data-ttu-id="b1a32-109">**IAddrBook：：Advise** 检查此条目标识符，以确定哪个通讯簿提供程序负责相应的对象，并转发对相应通讯簿提供程序 [的 IABLogon：：Advise](iablogon-advise.md) 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="b1a32-109">**IAddrBook::Advise** examines this entry identifier to determine which address book provider is responsible for the corresponding object and forwards the call to the appropriate address book provider's [IABLogon::Advise](iablogon-advise.md) method.</span></span> 
  
<span data-ttu-id="b1a32-110">客户端可以注册通讯簿条目上的以下类型的事件：</span><span class="sxs-lookup"><span data-stu-id="b1a32-110">Clients can register for the following types of events on address book entries:</span></span>
  
- <span data-ttu-id="b1a32-111">严重错误</span><span class="sxs-lookup"><span data-stu-id="b1a32-111">Critical error</span></span>
    
- <span data-ttu-id="b1a32-112">创建、修改、 (、移动或复制的任何对象) </span><span class="sxs-lookup"><span data-stu-id="b1a32-112">Any of the object events (created, modified, deleted, moved, or copied)</span></span>
    
- <span data-ttu-id="b1a32-113">已修改表</span><span class="sxs-lookup"><span data-stu-id="b1a32-113">Table modified</span></span>
    
<span data-ttu-id="b1a32-114">通常，仅对通讯簿容器内容和层次结构表进行注册。</span><span class="sxs-lookup"><span data-stu-id="b1a32-114">Typically, registration occurs only on address book container contents and hierarchy tables.</span></span> <span data-ttu-id="b1a32-115">客户端很少向较低级别的邮件用户和通讯组列表对象注册。</span><span class="sxs-lookup"><span data-stu-id="b1a32-115">It is rare that clients register with the lower level messaging user and distribution list objects.</span></span> <span data-ttu-id="b1a32-116">这是因为：</span><span class="sxs-lookup"><span data-stu-id="b1a32-116">This is because:</span></span>
  
- <span data-ttu-id="b1a32-117">许多通讯簿提供程序不支持有关其邮件用户和通讯组列表的通知。</span><span class="sxs-lookup"><span data-stu-id="b1a32-117">Many address book providers do not support notifications on their messaging users and distribution lists.</span></span>
    
- <span data-ttu-id="b1a32-118">表通知足以跟踪更改并报告给用户。</span><span class="sxs-lookup"><span data-stu-id="b1a32-118">Table notifications are sufficient for tracking changes and reporting them to users.</span></span>
    

