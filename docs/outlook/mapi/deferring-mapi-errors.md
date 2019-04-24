---
title: 延迟 MAPI 错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 93ae6d54-41cd-433c-8124-eb07d71baa57
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0cf56a92190acfab1a941bc8d3ad0acc1f3e1f89
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338701"
---
# <a name="deferring-mapi-errors"></a><span data-ttu-id="a1b72-103">延迟 MAPI 错误</span><span class="sxs-lookup"><span data-stu-id="a1b72-103">Deferring MAPI Errors</span></span>

  
  
<span data-ttu-id="a1b72-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a1b72-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a1b72-105">某些接口方法接受 MAPI_DEFERRED_ERRORS 标志作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="a1b72-105">Some interface methods accept the MAPI_DEFERRED_ERRORS flag as an input parameter.</span></span> <span data-ttu-id="a1b72-106">设置此标志后, 方法不必立即返回值;它可以让呼叫者在以后某个时候知道该呼叫的结果。</span><span class="sxs-lookup"><span data-stu-id="a1b72-106">When this flag is set, the method does not have to return immediately with a value; it can let the caller know the result of the call at some later time.</span></span>
  
<span data-ttu-id="a1b72-107">延迟错误有助于服务提供程序实现复杂方法, 使处理速度更快。</span><span class="sxs-lookup"><span data-stu-id="a1b72-107">Deferring errors helps service providers in their implementation of complex methods, making processing faster.</span></span> <span data-ttu-id="a1b72-108">延迟错误可以将呼叫捆绑到服务提供商中, 而不是处理多个请求并为每个请求返回一个值。</span><span class="sxs-lookup"><span data-stu-id="a1b72-108">Rather than handling many requests and returning a value for each, deferring errors allows the calls to be bundled within the service provider.</span></span> <span data-ttu-id="a1b72-109">同时处理多个请求会减少网络流量, 从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="a1b72-109">Processing many requests at once cuts down on network traffic, thereby improving performance.</span></span> <span data-ttu-id="a1b72-110">在对删除或复制属性的调用中, 延迟错误尤其有用, 这可能是非常耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="a1b72-110">Deferring errors is especially useful in calls to delete or copy properties, which can be very time-consuming operations.</span></span> 
  
<span data-ttu-id="a1b72-111">当客户端在未设置只能以延迟方式处理的 MAPI_DEFERRED_ERRORS 标志的情况下进行呼叫时, 服务提供程序可以在不考虑或返回 MAPI_E_TOO_COMPLEX 的情况下延迟这些错误。</span><span class="sxs-lookup"><span data-stu-id="a1b72-111">When a client makes a call without setting the MAPI_DEFERRED_ERRORS flag that can only be handled in a deferred manner, service providers can either defer the errors regardless or return MAPI_E_TOO_COMPLEX.</span></span> <span data-ttu-id="a1b72-112">大多数客户端应将错误推迟为使呼叫失败的首选策略。</span><span class="sxs-lookup"><span data-stu-id="a1b72-112">Most clients should defer errors as a preferable strategy to failing the call.</span></span> 
  
<span data-ttu-id="a1b72-113">设置 MAPI_DEFERRED_ERRORS 标志将更改客户端的错误处理实现, 因为可以在任何时间 (而不是在计划时间) 传递返回的信息。</span><span class="sxs-lookup"><span data-stu-id="a1b72-113">Setting the MAPI_DEFERRED_ERRORS flag changes a client's error handling implementation in that the returned information can be delivered at any time rather than at a planned time.</span></span> <span data-ttu-id="a1b72-114">如果要执行的操作太晚, 或者有关原始请求的数据已不再可用, 则可能会返回错误。</span><span class="sxs-lookup"><span data-stu-id="a1b72-114">It is possible for an error to be returned when it is too late to do anything about it or after data about the original request is no longer available.</span></span> <span data-ttu-id="a1b72-115">例如, 如果客户端调用**IMsgStore:: OpenEntry**以打开具有 MAPI_DEFERRED_ERRORS 集的已删除文件夹, 则客户端将不会知道该问题, 直到调用**IMAPIProp:: GetProps**调用以检索其中一个文件夹属性。</span><span class="sxs-lookup"><span data-stu-id="a1b72-115">For example, if a client calls **IMsgStore::OpenEntry** to open a deleted folder with MAPI_DEFERRED_ERRORS set, the client will not know of the problem until an **IMAPIProp::GetProps** call is made to retrieve one of the folder's properties.</span></span> <span data-ttu-id="a1b72-116">然后, **GetProps**将返回 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="a1b72-116">**GetProps** will then return MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a1b72-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1b72-117">See also</span></span>



[<span data-ttu-id="a1b72-118">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="a1b72-118">IMsgStore::OpenEntry</span></span>](imsgstore-openentry.md)
  
[<span data-ttu-id="a1b72-119">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="a1b72-119">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)

