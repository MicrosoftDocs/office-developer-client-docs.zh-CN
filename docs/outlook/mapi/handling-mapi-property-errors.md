---
title: 处理 MAPI 属性错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 23d68d8b-b0b6-4c32-8404-6acd23802db0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 82f37e2a6f6834c7a8553a3d9d364f7e657d81da
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579506"
---
# <a name="handling-mapi-property-errors"></a><span data-ttu-id="d44f0-103">处理 MAPI 属性错误</span><span class="sxs-lookup"><span data-stu-id="d44f0-103">Handling MAPI property errors</span></span>

<span data-ttu-id="d44f0-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d44f0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d44f0-105">而不是完整故障或成功时，以下**IMAPIProp**方法报告部分成功：</span><span class="sxs-lookup"><span data-stu-id="d44f0-105">Instead of complete failure or success, the following **IMAPIProp** methods report partial success:</span></span> 
  
[<span data-ttu-id="d44f0-106">GetProps</span><span class="sxs-lookup"><span data-stu-id="d44f0-106">GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="d44f0-107">SetProps</span><span class="sxs-lookup"><span data-stu-id="d44f0-107">SetProps</span></span>](imapiprop-setprops.md)
  
[<span data-ttu-id="d44f0-108">DeleteProps</span><span class="sxs-lookup"><span data-stu-id="d44f0-108">DeleteProps</span></span>](imapiprop-deleteprops.md)
  
[<span data-ttu-id="d44f0-109">CopyTo</span><span class="sxs-lookup"><span data-stu-id="d44f0-109">CopyTo</span></span>](imapiprop-copyto.md)
  
[<span data-ttu-id="d44f0-110">CopyProps</span><span class="sxs-lookup"><span data-stu-id="d44f0-110">CopyProps</span></span>](imapiprop-copyprops.md)
  
<span data-ttu-id="d44f0-111">**GetProps**报告部分成功时能够检索在至少一个对象的请求属性。</span><span class="sxs-lookup"><span data-stu-id="d44f0-111">**GetProps** reports partial success when it can retrieve at least one of the requested properties for an object.</span></span> <span data-ttu-id="d44f0-112">**GetProps**指示部分成功返回警告 MAPI_W_ERRORS_RETURNED 和**lppPropArray**参数指向属性值数组中发出有关不可用的属性的信息。</span><span class="sxs-lookup"><span data-stu-id="d44f0-112">**GetProps** indicates partial success by returning the warning MAPI_W_ERRORS_RETURNED and placing information about the unavailable properties in the property value array pointed to by the **lppPropArray** parameter.</span></span> <span data-ttu-id="d44f0-113">该数组中的不可用属性条目包含 PT_ERROR **ulPropTag**成员和 MAPI_E_NOT_FOUND 或另一个相应的错误值中的属性类型的**值**成员。</span><span class="sxs-lookup"><span data-stu-id="d44f0-113">An unavailable property's entry in this array contains PT_ERROR for the property type in the **ulPropTag** member and MAPI_E_NOT_FOUND or another appropriate error value for the **Value** member.</span></span> <span data-ttu-id="d44f0-114">例如，如果要检索三个属性的某个文件夹的**GetProps**方法在客户端调用和第三个不可用，消息存储提供程序 PT_ERROR 中放置属性值数组中的第三个属性类型和在第三 MAPI_E_NOT_FOUND属性值。</span><span class="sxs-lookup"><span data-stu-id="d44f0-114">For example, if a client calls a folder's **GetProps** method to retrieve three properties and the third is unavailable, the message store provider places PT_ERROR in the third property type in the property value array and MAPI_E_NOT_FOUND in the third property value.</span></span> 
  
<span data-ttu-id="d44f0-115">其他**IMAPIProp**方法报告部分成功各不相同。</span><span class="sxs-lookup"><span data-stu-id="d44f0-115">The other **IMAPIProp** methods report partial success differently.</span></span> <span data-ttu-id="d44f0-116">这些方法通过返回 S_OK 和[SPropProblemArray](spropproblemarray.md)结构中发出错误信息报告部分成功。</span><span class="sxs-lookup"><span data-stu-id="d44f0-116">These methods report partial success by returning S_OK and placing error information in an [SPropProblemArray](spropproblemarray.md) structure.</span></span> <span data-ttu-id="d44f0-117">与**GetProps**包含数据，而不管方法成功还是失败，这些方法中的属性问题数组才会存在错误和仅当呼叫者已注册的兴趣了解中的属性值数组不同出现错误。</span><span class="sxs-lookup"><span data-stu-id="d44f0-117">Unlike the property value array in **GetProps** that contains data regardless of whether the method succeeded or failed, the property problem array in these methods exists only if there are errors and only if the caller has registered interest in learning about the errors.</span></span> <span data-ttu-id="d44f0-118">呼叫者必须指定一个有效的**SPropProblemArray**指针注册错误信息。</span><span class="sxs-lookup"><span data-stu-id="d44f0-118">Callers must specify a valid **SPropProblemArray** pointer to register for error information.</span></span> 
  
<span data-ttu-id="d44f0-119">从**SetProps**、 **DeleteProps**、 **CopyTo**或**CopyProps**返回错误值时，这表明失败而不是部分成功。</span><span class="sxs-lookup"><span data-stu-id="d44f0-119">When an error value is returned from **SetProps**, **DeleteProps**, **CopyTo**, or **CopyProps**, this indicates failure instead of partial success.</span></span> <span data-ttu-id="d44f0-120">属性问题数组，如果可用，无效。</span><span class="sxs-lookup"><span data-stu-id="d44f0-120">The property problem array, if available, is not valid.</span></span> <span data-ttu-id="d44f0-121">客户端不应尝试访问数据结构中保留也应尝试忙结构本身。</span><span class="sxs-lookup"><span data-stu-id="d44f0-121">Clients should not try to access data held in the structure nor should they try to free the structure itself.</span></span> <span data-ttu-id="d44f0-122">相应的响应是调用[IMAPIProp::GetLastError](imapiprop-getlasterror.md)。</span><span class="sxs-lookup"><span data-stu-id="d44f0-122">The appropriate response is to call [IMAPIProp::GetLastError](imapiprop-getlasterror.md).</span></span> 
  
<span data-ttu-id="d44f0-123">类似于 Windows SDK 中提供的相同名称的函数**时出错**。</span><span class="sxs-lookup"><span data-stu-id="d44f0-123">**GetLastError** is similar to the function of the same name provided in the Windows SDK.</span></span> <span data-ttu-id="d44f0-124">同时提供更详细的有关错误的信息比可用的返回值。</span><span class="sxs-lookup"><span data-stu-id="d44f0-124">Both provide more detailed information about an error than is available with the return value.</span></span> <span data-ttu-id="d44f0-125">都返回前面发生的错误有关的信息。</span><span class="sxs-lookup"><span data-stu-id="d44f0-125">They both return information about the previous error that has occurred.</span></span> <span data-ttu-id="d44f0-126">区别在于 Win32 **GetLastError**函数的调用线程生成错误报告和**IMAPIProp::GetLastError**方法报告当前对象生成一个错误。</span><span class="sxs-lookup"><span data-stu-id="d44f0-126">The difference is that the Win32 **GetLastError** function reports on an error generated by the calling thread and the **IMAPIProp::GetLastError** method reports on an error generated by the current object.</span></span> <span data-ttu-id="d44f0-127">也就是说，如果客户端上的邮件和 MAPI_E_NO_ACCESS 调用**DeleteProps**返回以指示邮件是只读的**GetLastError**返回提供的邮件数据。</span><span class="sxs-lookup"><span data-stu-id="d44f0-127">That is, if a client calls **DeleteProps** on a message and MAPI_E_NO_ACCESS is returned to indicate that the message is read-only, **GetLastError** returns data provided by the message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d44f0-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d44f0-128">See also</span></span>

- [<span data-ttu-id="d44f0-129">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="d44f0-129">MAPI Property Overview</span></span>](mapi-property-overview.md)

