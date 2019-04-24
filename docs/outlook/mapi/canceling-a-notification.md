---
title: 取消通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: decd5d7d-1f47-47c2-b9c4-be0e652c99dd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fb0972638fdd062c99040694222724566281024f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326402"
---
# <a name="canceling-a-notification"></a><span data-ttu-id="c92be-103">取消通知</span><span class="sxs-lookup"><span data-stu-id="c92be-103">Canceling a Notification</span></span>

  
  
<span data-ttu-id="c92be-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c92be-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c92be-105">若要取消通知, 客户端需要调用建议源的**Unadvise**方法。</span><span class="sxs-lookup"><span data-stu-id="c92be-105">To cancel a notification, clients call an advise source's **Unadvise** method.</span></span> <span data-ttu-id="c92be-106">调用**Unadvise**非常重要, 因为它会导致服务提供程序释放其对您的通知接收器的引用。</span><span class="sxs-lookup"><span data-stu-id="c92be-106">Calling **Unadvise** is important because it causes the service provider to release its reference to your advise sink.</span></span> <span data-ttu-id="c92be-107">只要服务提供商维护对通知接收器的引用, 通知接收器就可以继续接收[IMAPIAdviseSink:: OnNotify](imapiadvisesink-onnotify.md) calls。</span><span class="sxs-lookup"><span data-stu-id="c92be-107">As long as a service provider maintains a reference to an advise sink, the advise sink can continue to receive [IMAPIAdviseSink::OnNotify](imapiadvisesink-onnotify.md) calls.</span></span> <span data-ttu-id="c92be-108">事实上, 由于事件通知的异步特性, 即使在成功的**Unadvise**调用之后, 也可以通知客户端。</span><span class="sxs-lookup"><span data-stu-id="c92be-108">In fact, because of the asynchronous nature of event notification, clients can be notified even after a successful **Unadvise** call.</span></span> <span data-ttu-id="c92be-109">客户端必须能够随时处理通知回执。</span><span class="sxs-lookup"><span data-stu-id="c92be-109">Clients must be able to handle the receipt of notifications at any time.</span></span> 
  
<span data-ttu-id="c92be-110">由于服务提供程序实现不同, 无法调用**Unadvise**以取消通知的客户端无法假定提供程序释放其通知接收器的引用时的任何信息。</span><span class="sxs-lookup"><span data-stu-id="c92be-110">Because service provider implementations differ, clients that fail to call **Unadvise** to cancel a notification cannot assume anything about when a provider will release its reference to their advise sink.</span></span> <span data-ttu-id="c92be-111">某些服务提供商释放他们的参考, 以在发布其建议来源时通知接收器。</span><span class="sxs-lookup"><span data-stu-id="c92be-111">Some service providers release their references to advise sinks when they release their advise sources.</span></span> <span data-ttu-id="c92be-112">有些服务提供商不会。</span><span class="sxs-lookup"><span data-stu-id="c92be-112">Some service providers do not.</span></span> <span data-ttu-id="c92be-113">只要服务提供商维护对通知接收器的引用, 该通知接收器即可继续接收通知。</span><span class="sxs-lookup"><span data-stu-id="c92be-113">As long as a service provider maintains a reference to an advise sink, that advise sink can continue to receive notifications.</span></span> 
  

