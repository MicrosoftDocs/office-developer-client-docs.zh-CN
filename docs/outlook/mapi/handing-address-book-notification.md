---
title: 向通讯簿通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0dc4bb48-c8a1-447f-9e38-1c234a358fca
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f198be78dd36a6d0c9439da68ab322cd8cfa4172
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775037"
---
# <a name="handing-address-book-notification"></a><span data-ttu-id="974a6-103">向通讯簿通知</span><span class="sxs-lookup"><span data-stu-id="974a6-103">Handing address book notification</span></span>
  
<span data-ttu-id="974a6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="974a6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="974a6-105">地址簿通知允许客户端若要了解到任何通讯簿条目或特定项所发生的事件。</span><span class="sxs-lookup"><span data-stu-id="974a6-105">Address book notifications allow a client to learn of events that occur to any address book entry or to a particular entry.</span></span> <span data-ttu-id="974a6-106">您可以通过调用[IMAPITable::Advise](imapitable-advise.md)注册这些通知通过 MAPI 通讯簿通过调用[IAddrBook::Advise](iaddrbook-advise.md)或通过通讯簿容器层次结构或内容表。</span><span class="sxs-lookup"><span data-stu-id="974a6-106">You can register for these notifications either through the MAPI address book by calling [IAddrBook::Advise](iaddrbook-advise.md) or through an address book container's hierarchy or contents table by calling [IMAPITable::Advise](imapitable-advise.md).</span></span> 
  
<span data-ttu-id="974a6-107">如果要在特定的条目和 NULL 上的通知注册的如果注册整个通讯簿上的通知，请指定通讯簿容器、 通讯组列表或消息的用户的项标识符。</span><span class="sxs-lookup"><span data-stu-id="974a6-107">Specify the entry identifier of an address book container, distribution list, or messaging user if you are registering for notifications on a particular entry and NULL if registering for notifications on the entire address book.</span></span> <span data-ttu-id="974a6-108">消息的用户或通讯簿容器中的通讯组列表，则必须表示的项标识符。</span><span class="sxs-lookup"><span data-stu-id="974a6-108">The entry identifier must represent a messaging user or distribution list in an address book container.</span></span> <span data-ttu-id="974a6-109">**IAddrBook::Advise**检查此条目标识符来确定哪个地址簿提供程序负责为相应的对象，并将转发对相应的通讯簿提供程序的[IABLogon::Advise](iablogon-advise.md)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="974a6-109">**IAddrBook::Advise** examines this entry identifier to determine which address book provider is responsible for the corresponding object and forwards the call to the appropriate address book provider's [IABLogon::Advise](iablogon-advise.md) method.</span></span> 
  
<span data-ttu-id="974a6-110">客户端可以注册以下类型的通讯簿条目上的事件：</span><span class="sxs-lookup"><span data-stu-id="974a6-110">Clients can register for the following types of events on address book entries:</span></span>
  
- <span data-ttu-id="974a6-111">严重错误</span><span class="sxs-lookup"><span data-stu-id="974a6-111">Critical error</span></span>
    
- <span data-ttu-id="974a6-112">任何对象事件 （创建、 修改、 删除、 移动或复制）</span><span class="sxs-lookup"><span data-stu-id="974a6-112">Any of the object events (created, modified, deleted, moved, or copied)</span></span>
    
- <span data-ttu-id="974a6-113">修改的表</span><span class="sxs-lookup"><span data-stu-id="974a6-113">Table modified</span></span>
    
<span data-ttu-id="974a6-114">通常，注册才会出现通讯簿容器内容和层次结构表。</span><span class="sxs-lookup"><span data-stu-id="974a6-114">Typically, registration occurs only on address book container contents and hierarchy tables.</span></span> <span data-ttu-id="974a6-115">很少客户端注册消息用户和通讯组列表对象的较低级别。</span><span class="sxs-lookup"><span data-stu-id="974a6-115">It is rare that clients register with the lower level messaging user and distribution list objects.</span></span> <span data-ttu-id="974a6-116">这是因为：</span><span class="sxs-lookup"><span data-stu-id="974a6-116">This is because:</span></span>
  
- <span data-ttu-id="974a6-117">许多通讯簿提供程序不支持针对其消息的用户和通讯组列表的通知。</span><span class="sxs-lookup"><span data-stu-id="974a6-117">Many address book providers do not support notifications on their messaging users and distribution lists.</span></span>
    
- <span data-ttu-id="974a6-118">表通知是足以跟踪的更改并向他们报告给用户。</span><span class="sxs-lookup"><span data-stu-id="974a6-118">Table notifications are sufficient for tracking changes and reporting them to users.</span></span>
    

