---
title: 处理 MAPI 属性错误
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 23d68d8b-b0b6-4c32-8404-6acd23802db0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1dc676101d4c39544c9dd1fae94000db9963ea02
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299384"
---
# <a name="handling-mapi-property-errors"></a><span data-ttu-id="d5a73-103">处理 MAPI 属性错误</span><span class="sxs-lookup"><span data-stu-id="d5a73-103">Handling MAPI property errors</span></span>

<span data-ttu-id="d5a73-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d5a73-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d5a73-105">以下**IMAPIProp**方法报告部分成功, 而不是完全失败或成功:</span><span class="sxs-lookup"><span data-stu-id="d5a73-105">Instead of complete failure or success, the following **IMAPIProp** methods report partial success:</span></span> 
  
[<span data-ttu-id="d5a73-106">GetProps</span><span class="sxs-lookup"><span data-stu-id="d5a73-106">GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="d5a73-107">SetProps</span><span class="sxs-lookup"><span data-stu-id="d5a73-107">SetProps</span></span>](imapiprop-setprops.md)
  
[<span data-ttu-id="d5a73-108">DeleteProps</span><span class="sxs-lookup"><span data-stu-id="d5a73-108">DeleteProps</span></span>](imapiprop-deleteprops.md)
  
[<span data-ttu-id="d5a73-109">CopyTo</span><span class="sxs-lookup"><span data-stu-id="d5a73-109">CopyTo</span></span>](imapiprop-copyto.md)
  
[<span data-ttu-id="d5a73-110">CopyProps</span><span class="sxs-lookup"><span data-stu-id="d5a73-110">CopyProps</span></span>](imapiprop-copyprops.md)
  
<span data-ttu-id="d5a73-111">**GetProps**报告在至少能够检索到某个对象的请求属性之一时, 这是完全成功的。</span><span class="sxs-lookup"><span data-stu-id="d5a73-111">**GetProps** reports partial success when it can retrieve at least one of the requested properties for an object.</span></span> <span data-ttu-id="d5a73-112">**GetProps**通过返回警告 MAPI_W_ERRORS_RETURNED 并在由**lppPropArray**参数指向的属性值数组中放置有关不可用属性的信息, 来指示部分成功。</span><span class="sxs-lookup"><span data-stu-id="d5a73-112">**GetProps** indicates partial success by returning the warning MAPI_W_ERRORS_RETURNED and placing information about the unavailable properties in the property value array pointed to by the **lppPropArray** parameter.</span></span> <span data-ttu-id="d5a73-113">此数组中不可用的属性条目包含**ulPropTag**成员中的属性类型的 PT_ERROR, 以及**值**成员的其他适当的错误值。</span><span class="sxs-lookup"><span data-stu-id="d5a73-113">An unavailable property's entry in this array contains PT_ERROR for the property type in the **ulPropTag** member and MAPI_E_NOT_FOUND or another appropriate error value for the **Value** member.</span></span> <span data-ttu-id="d5a73-114">例如, 如果客户端调用文件夹的**GetProps**方法来检索三个属性, 而第三个属性不可用, 则邮件存储提供程序会将 PT_ERROR 放在属性值数组中的第三个属性类型中, 并在第三个属性中放置 MAPI_E_NOT_FOUND属性值。</span><span class="sxs-lookup"><span data-stu-id="d5a73-114">For example, if a client calls a folder's **GetProps** method to retrieve three properties and the third is unavailable, the message store provider places PT_ERROR in the third property type in the property value array and MAPI_E_NOT_FOUND in the third property value.</span></span> 
  
<span data-ttu-id="d5a73-115">其他**IMAPIProp**方法以不同的方式报告部分成功。</span><span class="sxs-lookup"><span data-stu-id="d5a73-115">The other **IMAPIProp** methods report partial success differently.</span></span> <span data-ttu-id="d5a73-116">这些方法通过返回 S_OK 并将错误信息放在[SPropProblemArray](spropproblemarray.md)结构中来报告部分成功。</span><span class="sxs-lookup"><span data-stu-id="d5a73-116">These methods report partial success by returning S_OK and placing error information in an [SPropProblemArray](spropproblemarray.md) structure.</span></span> <span data-ttu-id="d5a73-117">与包含数据的**GetProps**中的属性值数组 (无论方法是成功还是失败) 不同, 这些方法中的属性问题数组仅在出现错误时才存在, 并且只有当调用方已注册相关知识时才存在。错误。</span><span class="sxs-lookup"><span data-stu-id="d5a73-117">Unlike the property value array in **GetProps** that contains data regardless of whether the method succeeded or failed, the property problem array in these methods exists only if there are errors and only if the caller has registered interest in learning about the errors.</span></span> <span data-ttu-id="d5a73-118">调用方必须指定有效的**SPropProblemArray**指针以注册错误消息。</span><span class="sxs-lookup"><span data-stu-id="d5a73-118">Callers must specify a valid **SPropProblemArray** pointer to register for error information.</span></span> 
  
<span data-ttu-id="d5a73-119">当**SetProps**、 **DeleteProps**、 **CopyTo**或**CopyProps**返回错误值时, 这表示失败而不是部分成功。</span><span class="sxs-lookup"><span data-stu-id="d5a73-119">When an error value is returned from **SetProps**, **DeleteProps**, **CopyTo**, or **CopyProps**, this indicates failure instead of partial success.</span></span> <span data-ttu-id="d5a73-120">属性问题数组 (如果可用) 无效。</span><span class="sxs-lookup"><span data-stu-id="d5a73-120">The property problem array, if available, is not valid.</span></span> <span data-ttu-id="d5a73-121">客户端不应尝试访问结构中保留的数据, 也不应尝试释放结构本身。</span><span class="sxs-lookup"><span data-stu-id="d5a73-121">Clients should not try to access data held in the structure nor should they try to free the structure itself.</span></span> <span data-ttu-id="d5a73-122">相应的响应是调用[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)。</span><span class="sxs-lookup"><span data-stu-id="d5a73-122">The appropriate response is to call [IMAPIProp::GetLastError](imapiprop-getlasterror.md).</span></span> 
  
<span data-ttu-id="d5a73-123">**GetLastError**类似于 Windows SDK 中提供的相同名称的函数。</span><span class="sxs-lookup"><span data-stu-id="d5a73-123">**GetLastError** is similar to the function of the same name provided in the Windows SDK.</span></span> <span data-ttu-id="d5a73-124">同时提供了有关错误的详细信息, 而不是返回值中提供的值。</span><span class="sxs-lookup"><span data-stu-id="d5a73-124">Both provide more detailed information about an error than is available with the return value.</span></span> <span data-ttu-id="d5a73-125">它们都返回有关以前发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d5a73-125">They both return information about the previous error that has occurred.</span></span> <span data-ttu-id="d5a73-126">区别在于, Win32 **GetLastError**函数报告由调用线程生成的错误和**IMAPIProp:: GetLastError**方法报告由当前对象生成的错误。</span><span class="sxs-lookup"><span data-stu-id="d5a73-126">The difference is that the Win32 **GetLastError** function reports on an error generated by the calling thread and the **IMAPIProp::GetLastError** method reports on an error generated by the current object.</span></span> <span data-ttu-id="d5a73-127">也就是说, 如果客户端对邮件调用**DeleteProps** , 并返回 MAPI_E_NO_ACCESS 以指示该邮件是只读的, 则**GetLastError**将返回该邮件提供的数据。</span><span class="sxs-lookup"><span data-stu-id="d5a73-127">That is, if a client calls **DeleteProps** on a message and MAPI_E_NO_ACCESS is returned to indicate that the message is read-only, **GetLastError** returns data provided by the message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d5a73-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5a73-128">See also</span></span>

- [<span data-ttu-id="d5a73-129">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="d5a73-129">MAPI Property Overview</span></span>](mapi-property-overview.md)

