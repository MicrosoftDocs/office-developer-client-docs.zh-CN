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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427337"
---
# <a name="deferring-mapi-errors"></a><span data-ttu-id="281ff-103">延迟 MAPI 错误</span><span class="sxs-lookup"><span data-stu-id="281ff-103">Deferring MAPI Errors</span></span>

  
  
<span data-ttu-id="281ff-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="281ff-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="281ff-105">某些接口方法接受 MAPI_DEFERRED_ERRORS 标志作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="281ff-105">Some interface methods accept the MAPI_DEFERRED_ERRORS flag as an input parameter.</span></span> <span data-ttu-id="281ff-106">设置此标志时，该方法无需立即返回值;它可以让呼叫者稍后知道呼叫结果。</span><span class="sxs-lookup"><span data-stu-id="281ff-106">When this flag is set, the method does not have to return immediately with a value; it can let the caller know the result of the call at some later time.</span></span>
  
<span data-ttu-id="281ff-107">延迟错误可帮助服务提供商实现复杂方法，从而加快处理速度。</span><span class="sxs-lookup"><span data-stu-id="281ff-107">Deferring errors helps service providers in their implementation of complex methods, making processing faster.</span></span> <span data-ttu-id="281ff-108">延迟错误允许调用捆绑在服务提供商中，而不是处理许多请求并返回每个请求的值。</span><span class="sxs-lookup"><span data-stu-id="281ff-108">Rather than handling many requests and returning a value for each, deferring errors allows the calls to be bundled within the service provider.</span></span> <span data-ttu-id="281ff-109">一次处理多个请求将减少网络流量，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="281ff-109">Processing many requests at once cuts down on network traffic, thereby improving performance.</span></span> <span data-ttu-id="281ff-110">延迟错误在调用删除或复制属性时尤其有用，这非常耗时的操作。</span><span class="sxs-lookup"><span data-stu-id="281ff-110">Deferring errors is especially useful in calls to delete or copy properties, which can be very time-consuming operations.</span></span> 
  
<span data-ttu-id="281ff-111">当客户端在未设置 MAPI_DEFERRED_ERRORS 标志的情况下进行调用时，服务提供商可以延迟错误而不考虑，也可以返回MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="281ff-111">When a client makes a call without setting the MAPI_DEFERRED_ERRORS flag that can only be handled in a deferred manner, service providers can either defer the errors regardless or return MAPI_E_TOO_COMPLEX.</span></span> <span data-ttu-id="281ff-112">大多数客户端应延迟错误作为一种首选策略来使调用失败。</span><span class="sxs-lookup"><span data-stu-id="281ff-112">Most clients should defer errors as a preferable strategy to failing the call.</span></span> 
  
<span data-ttu-id="281ff-113">设置 MAPI_DEFERRED_ERRORS 标志将更改客户端的错误处理实现，因为返回的信息可以随时传递，而不是在计划的时间传递。</span><span class="sxs-lookup"><span data-stu-id="281ff-113">Setting the MAPI_DEFERRED_ERRORS flag changes a client's error handling implementation in that the returned information can be delivered at any time rather than at a planned time.</span></span> <span data-ttu-id="281ff-114">如果对错误执行任何操作太晚，或者原始请求的数据不再可用，可能会返回错误。</span><span class="sxs-lookup"><span data-stu-id="281ff-114">It is possible for an error to be returned when it is too late to do anything about it or after data about the original request is no longer available.</span></span> <span data-ttu-id="281ff-115">例如，如果客户端调用 **IMsgStore：：OpenEntry** 打开设置了 MAPI_DEFERRED_ERRORS 的已删除文件夹，则客户端将不知道该问题，除非进行 **IMAPIProp：：GetProps** 调用以检索文件夹的属性之一。</span><span class="sxs-lookup"><span data-stu-id="281ff-115">For example, if a client calls **IMsgStore::OpenEntry** to open a deleted folder with MAPI_DEFERRED_ERRORS set, the client will not know of the problem until an **IMAPIProp::GetProps** call is made to retrieve one of the folder's properties.</span></span> <span data-ttu-id="281ff-116">**GetProps** 随后将返回MAPI_E_NOT_FOUND。</span><span class="sxs-lookup"><span data-stu-id="281ff-116">**GetProps** will then return MAPI_E_NOT_FOUND.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="281ff-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="281ff-117">See also</span></span>



[<span data-ttu-id="281ff-118">IMsgStore::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="281ff-118">IMsgStore::OpenEntry</span></span>](imsgstore-openentry.md)
  
[<span data-ttu-id="281ff-119">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="281ff-119">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)

