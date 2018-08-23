---
title: 推迟 MAPI 错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 93ae6d54-41cd-433c-8124-eb07d71baa57
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3d2a46be04f235ba55aa5f2feef222ea7372b211
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569860"
---
# <a name="deferring-mapi-errors"></a><span data-ttu-id="4b288-103">推迟 MAPI 错误</span><span class="sxs-lookup"><span data-stu-id="4b288-103">Deferring MAPI Errors</span></span>

  
  
<span data-ttu-id="4b288-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4b288-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4b288-105">一些接口方法接受 MAPI_DEFERRED_ERRORS 标志作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="4b288-105">Some interface methods accept the MAPI_DEFERRED_ERRORS flag as an input parameter.</span></span> <span data-ttu-id="4b288-106">当此标志设置时，该方法不需要立即返回值;它可以让呼叫者了解在某些更高版本时调用的结果。</span><span class="sxs-lookup"><span data-stu-id="4b288-106">When this flag is set, the method does not have to return immediately with a value; it can let the caller know the result of the call at some later time.</span></span>
  
<span data-ttu-id="4b288-107">推迟错误帮助他们实现复杂方法中的服务提供商进行处理速度更快。</span><span class="sxs-lookup"><span data-stu-id="4b288-107">Deferring errors helps service providers in their implementation of complex methods, making processing faster.</span></span> <span data-ttu-id="4b288-108">而不是处理大量请求和每个返回一个值，推迟错误允许无法捆绑的服务提供程序内的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4b288-108">Rather than handling many requests and returning a value for each, deferring errors allows the calls to be bundled within the service provider.</span></span> <span data-ttu-id="4b288-109">同时处理大量请求可以减少网络流量，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="4b288-109">Processing many requests at once cuts down on network traffic, thereby improving performance.</span></span> <span data-ttu-id="4b288-110">推迟错误是要删除的呼叫或复制属性，可以是非常耗时的操作特别有用。</span><span class="sxs-lookup"><span data-stu-id="4b288-110">Deferring errors is especially useful in calls to delete or copy properties, which can be very time-consuming operations.</span></span> 
  
<span data-ttu-id="4b288-111">服务提供商时没有设置 MAPI_DEFERRED_ERRORS 标志只能处理延迟的方式，客户端发出呼叫，可以将无论错误也推迟或返回 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="4b288-111">When a client makes a call without setting the MAPI_DEFERRED_ERRORS flag that can only be handled in a deferred manner, service providers can either defer the errors regardless or return MAPI_E_TOO_COMPLEX.</span></span> <span data-ttu-id="4b288-112">大多数客户端应作为对失败的呼叫的首选策略推迟错误。</span><span class="sxs-lookup"><span data-stu-id="4b288-112">Most clients should defer errors as a preferable strategy to failing the call.</span></span> 
  
<span data-ttu-id="4b288-113">设置 MAPI_DEFERRED_ERRORS 标志更改客户端的错误处理实现中，可以传递返回的信息，在任何时候，而不是计划的时间。</span><span class="sxs-lookup"><span data-stu-id="4b288-113">Setting the MAPI_DEFERRED_ERRORS flag changes a client's error handling implementation in that the returned information can be delivered at any time rather than at a planned time.</span></span> <span data-ttu-id="4b288-114">很可能会晚有关该产品，或有关原始请求的数据不再可用后执行任何操作时要返回的错误。</span><span class="sxs-lookup"><span data-stu-id="4b288-114">It is possible for an error to be returned when it is too late to do anything about it or after data about the original request is no longer available.</span></span> <span data-ttu-id="4b288-115">例如，如果客户端调用**IMsgStore::OpenEntry** MAPI_DEFERRED_ERRORS 设置打开已删除的文件夹，客户端将不知道问题的直到**IMAPIProp::GetProps**调用来检索文件夹的属性之一。</span><span class="sxs-lookup"><span data-stu-id="4b288-115">For example, if a client calls **IMsgStore::OpenEntry** to open a deleted folder with MAPI_DEFERRED_ERRORS set, the client will not know of the problem until an **IMAPIProp::GetProps** call is made to retrieve one of the folder's properties.</span></span> <span data-ttu-id="4b288-116">**GetProps**然后将返回 MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="4b288-116">**GetProps** will then return MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4b288-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b288-117">See also</span></span>



[<span data-ttu-id="4b288-118">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="4b288-118">IMsgStore::OpenEntry</span></span>](imsgstore-openentry.md)
  
[<span data-ttu-id="4b288-119">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="4b288-119">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)

